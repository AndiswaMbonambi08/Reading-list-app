\# Sprint 1 — Technical Prep Notes



\## Story: See a board representing my whole shelf

\- `BoardScreen` widget renders 3 fixed columns as `Column` widgets inside a horizontally scrollable `Row` (or `PageView` if columns should be swipeable on mobile): Want to Read, Currently Reading, Finished

\- Each column is a `ListView.builder` that filters the card list by `column` value and maps to `BookCard` widgets

\- Empty state: if a column's filtered list is empty, render a placeholder `Text` widget (e.g. "No books yet") instead of an empty `ListView`

\- Card list held in a `List<Book>` in a state management solution (start simple: `StatefulWidget` + `setState`, revisit `Provider`/`Riverpod` later if state gets shared across screens)



\## Story: Add a book card with a title and author

\- `Book` data class: `{ String id, String title, String author, String column }`

\- New cards default to `column: "Want to Read"`

\- Add form: a `Dialog` or bottom sheet with two `TextField`s (title, author) and a submit `ElevatedButton`

\- Title field validated with a `TextFormField` validator, empty title blocks submission and shows an inline error, no snackbar-only failure

\- On submit, generate an id (`uuid` package or `DateTime.now().millisecondsSinceEpoch` for now), call `setState` to add the new `Book` to the in-memory list (no persistence yet, no SQLite, per Iteration 1 scope, that's Iteration 2)

