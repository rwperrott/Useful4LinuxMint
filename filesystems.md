# Filesystem

## Filesystems
### Linux
- ext3
    - A journaling filesystem.
- ext4
    - A journaling filesystem.
- [BTRFS](filesystem/btrfs.md)
    - Probably an attempt to copy `ZFS`.
    - Less mature tools, including needless explicit setup needed before snapshots can be created!
    - It seemed slower than ZFS, e.g. for data transfer speed.
    - Apparently it has RAID data loss issues!
    - This may be reliably usable for data transfer with Windows, because https://github.com/maharmstone/btrfs exists is on chocolatey.

### Microsoft
- [FAT](https://en.wikipedia.org/wiki/File_Allocation_Table)
  - A family of primitive MSDOS filesystems
  - No support for extended/POSIX directory entry attributes
  - Not journaled.
  - FAT32 is often used to contain hold grub, to load Linux not used.
  - Otherwise, only useful for flash disks up to 32GB, or for trivial data disks.
- [exFAT](https://en.wikipedia.org/wiki/ExFAT)
  - An extension/adaption of FAT for use on portable flash cards and disks larger than 32GB,
  - Directory record structure optimised for limited flash card data transfer speeds.
  - No support for extended/POSIX directory entry attributes
  - Not journaled.
  - Only useful for data disk needing no integrity protection.
- [NTFS](https://en.wikipedia.org/wiki/NTFS)
  - A journaling filesystem, which has always seemed fussy about dirty directory state, even on Windows!
  - It gets really sluggish when a directory on a hard disk drive contains many thousands of files, 
possibly because of MFT file fragmentation!
  - Apparently, Paragon's [ntfs3](https://docs.kernel.org/filesystems/ntfs3.html) NTFS driver in the Linux Kernel,
and using an /etc/fstab mount entry with filesystem type `ntfs3`,
is preferable to allowing the `ntfs-3g` FUSE driver to be used by default.
  - Sadly I have had an NTFS drives under sustained and heavy IO load completely freeze Linux Mint machines,
so strongly suggest that BTRFS disk are used in preference to NTFS ones!
  - An NTFS drive can become unmountable or dirty after a such a freeze; 
the `Gnome Disks` partition repair seems a reliable fix so far.
  - I'm wary of Linux console tools for repairing NTFS partitions, because some did make things worse! 

### Sun/Oracle
- Open[ZFS](https://openzfs.org/wiki/Main_Page) - [GitHub](https://github.com/openzfs/zfs)
  - A superb filesystem, which demolishes most of the lazy arguments for journaling filesystems.
  - Robustly checksums all data, because data corrupting can also occur in drive connections too, as ZFS developers discovered!
  - Built-in support for multiple compression methods, encryption, extended RAID, etc., even de-dup!
  - Revealed how pointless and inferior RAID controllers are.
  - This may become reliably usable for data transfer with Windows, 
    when https://github.com/openzfsonwindows/openzfs is no longer beta.


## My Filesystem opinions
- Basic filesystems can't be trusted for data safety, and have no support for extended file attributes and ACLs;
  this is why they are no longer used to store operating systems files e.g. Window's default filesystem became NTFS.

- I also don't trust journaling filesystems much:
    - They may cope better that a basic filesystem for drive disconnection or power-off, but if being written to on-disk,
      or its in-memory state is out of sync with that on the disk;
      bad stuff can happen, which may not be even recognised as corruption by the operating system at the next boot!
    - If as a write operation fails part of the way through, for hardware or software reasons, tough,
      you may now have corrupt data; because it can't roll back the operation!
    - Filesystem snapshots cannot be done instantly, so requiring costly hacks, like the `Shadow Copy` service in Windows,
and the seriously flawed `Timeshift` in Linux, and storage of these copy-snapshots is both time and space costly.
    - I have seen stubborn boot fails suddenly occur in Windows and Linux, which I strongly suspect were caused by too-late disk flushing, 
even with my Samsung NVME flash disk, not hardware sector corruption.
      - I now use ZFS to hold Linux, so any hardware sector issues should not be missed! 


- I far prefer Transactional, copy-on-write filesystems, like ZFS and BTRFS:
    - They replace most of the need for partitions, because they support filesystem containers dataset/subvolumes,
which can be nested:
        - This can remove the need to run a disk defragmentation utility, run a disk partition utility, and reboot.
          - e.g. to resize some partitions to change their capacity.
        - They behave like directories, so can also replace directories,
          - e.g. a user's home directory.
        - Each inherits their parent's configuration.
    - All but the pool dataset inherits their parent's permissions, but these can be overridden, e.g.:
      - To restrict the maximum size of a user's home directory, logs or backups,
      to prevent a system out-of-space crisis.
    - They keep drive contents in-sync with the host disk.
    - They slash the risks of uncompleted state or corruption on disk.
    - Filesystem snapshots can be done instantly, with git-like storage efficiency, and many can be stored,
      and a snapshot will allow consistent backup to another storage device with no need for kludges-like Shadow Copy in
      Windows.

### NTFS Drives Are Risky to Use With Linux
- The ntfs-3g driver can make Linux become completely unresponsive while under a high load;
this doesn't happen with ZFS or BTRFS drives on Linux! 
- The Gnome Disks GUI can fit the resulting corruption, after reset and reboot from such an outage,
so that drive can mount again; this only just reinforced my opinion to no use journaling filesystems!
  - Fortunately all the files, recently saved were accessible afterwards.
  - I decided that the best approach was to backup all the data, between freezes, then reformat the drive with BTRFS!

### Ejecting/unmounting disks
- The reasons why you have to explicitly eject removable disks are:
    - To detect open files, which may cause a problem, or often needless disk, directory or file locks.
    - The OS tends to delay updating basic and transactional filesystems disks for modified metadata and written data,
      to maximise disk transfer speed, so eject probably forces and waits for a `sync` to complete before it will unmount the disk.

#### A Way to Maybe Safely Unplug/Disconnect A Dubiously not Unmountable/Ejectable Disk.
- Look for the mount point path or /dev/drive in-use by any process.
    - if found, decide if you want to close or plain kill the process, otherwise don't continue.
    - if none found, decide if it's worth the risk, otherwise don't continue.
- Run `sync` for the drive and wait until complete.
- If you can and want to risk it, unplug/disconnect the drive.
    
#### Dubious refusal of USB drive ejection, in or other disk unmount request
- I recently had `Gnome Disks` repeatedly refusing to unmount an internal disk, which I wanted to reformat.
  - Puzzlingly, I couldn't find any process using the drive!
  - I was astonished to discover that merely closing a specific, idling, mate-terminal window,
  allowed me to unmount the disk, wt*!
  - How was a mere idling mate-terminal able keep blocking a drive unmount!?
