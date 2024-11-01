# ([Desktop Entry Specification](https://specifications.freedesktop.org/desktop-entry-spec/latest/index.html)) `*.desktop` files:

| Directory for<br/>`*.desktop` files | For     |
|-------------------------------------|---------|
| /usr/share/applications/            | all     | 
| ~/.local/share/applications         | ${USER} |

The structure is complicated, so see the link!

## `Category` value

See the [Categories](desktop-entry-categories.ods) Spreadsheet for a list or categories,
and their often ambiguous-hierarchy. This has sort headers, so that you can see this ambiguity.

Beware:
- The Categories value is a sequence of zero or more ; delimited category names.
- A Category value can contain multiple category clauses.
  - Categories are delimited by 
  - Each clause can be a sequence of 1 to 3 categories, some similar.
  - Categories can be more like another kind of `keyword`, with often fuzzy associates.
    - Many more specific categories as not sub-categories of just one more general category. 
    - Grouping some categories under only one category can be mistaken; multiple associations may apply. 
    - Some more specific categories have no specified association with a more general category.
