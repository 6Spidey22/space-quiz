# Repository instructions

## Project structure and architecture

- This is a dependency-free static web app. `index.html` is the application: it contains the quiz markup, light/dark theme styles, question data, rendering, answer handling, scoring, and results.
- Quiz state is held in memory in the page script. `renderQuestion()` updates the current question and progress; `selectAnswer()` locks choices, updates the score, and displays feedback; `showResults()` displays the final score and score-based reaction.
- The question bank is the `questions` array in `index.html`. Each entry includes a category, question, four answer strings, a zero-based `correct` answer index, and an explanatory `fact`.
- The page is designed to open directly from `index.html` in a browser; it does not require a server or dependency installation.

## Build, test, and lint

- There are no build, test, or lint commands configured in this repository.
- To run the app, open `index.html` in a browser.
- For a manual smoke test, answer all ten questions, check that correct and incorrect answers show the appropriate feedback and score behavior, and confirm the results screen and restart action.

## Code conventions

- Keep the app self-contained in `index.html`; there is no module or asset pipeline.
- Add or edit quiz content in the `questions` array. `correct` is a zero-based index into that entry's `answers`; keep its `fact` aligned with the correct answer.
- Keep theme-dependent colors in the CSS custom properties under `:root` and `@media (prefers-color-scheme: dark)`, so both color schemes remain consistent.
- The page uses native buttons for answers and actions, an ARIA progress bar for quiz progress, and live regions for question, feedback, and results announcements. Preserve keyboard focus handling and reduced-motion support when changing the interaction or animations.
