# JavaScript Basics Quiz

CodeNova Internship Program, Batch 01 (Frontend Development), Task 2: Interactive Quiz Website.

**Live demo:** <ADD GITHUB PAGES LINK>

## Features
- Multiple-choice questions with a progress bar and live score
- Instant colour-coded feedback (green = correct, red = wrong) with an explanation
- Answers lock after the first choice, so a question cannot be submitted twice
- Final results screen and a Restart button that resets state without reloading the page
- Responsive, touch-friendly layout; light and dark theme follow the system setting
- Keyboard accessible with visible focus, `aria-live` updates and reduced-motion support

## Tech stack
HTML5, CSS3 (variables, Grid), vanilla JavaScript (ES6+). No build step, no paid tools.

## Question bank
`questions.json` holds 8 questions. Each item has: `q` (question), `o` (options), `a` (index of the correct option), `e` (explanation).

## State management
Three variables drive the app: `i` (current question index), `score`, and `answered` (lock flag).
- `render()` draws question `i` and clears the feedback.
- `pick(k)` returns immediately if `answered` is true; otherwise it locks the question, marks the right and wrong options, updates the score and shows the explanation.
- The Next button increments `i` and calls `render()`, or shows the results after the last question.
- `start()` resets `i` and `score` to 0, which implements the restart without a page reload.

## Setup
Hosted on GitHub Pages: no setup needed. To run locally, serve the folder (for example `python3 -m http.server`) and open `http://localhost:8000`. Opening `index.html` directly also works, using the embedded copy of the questions.

## Screenshots
Add images to a `screenshots/` folder and link them here:
- `screenshots/start.png`
- `screenshots/question.png`
- `screenshots/feedback.png`
- `screenshots/results.png`
