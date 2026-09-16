# ECON20004 — Tutorial 1: Probability Revision

An interactive version of Tutorial 1. Students work through all six exercises and get
marked as they go: 27 questions covering expectation, variance, covariance, correlation
and the law of iterated expectations.

Everything is one file (`index.html`) with no build step, no server and no dependencies
beyond a web font. It works offline once loaded.

## Putting it on GitHub Pages

1. Create a new repository on GitHub (public, so students can reach it).
2. Upload `index.html` to the root of the repository — drag and drop works via
   **Add file → Upload files**.
3. Go to **Settings → Pages**.
4. Under **Source**, choose **Deploy from a branch**; set branch to `main` and folder
   to `/ (root)`. Save.
5. Wait about a minute, then your site is live at
   `https://<your-username>.github.io/<repository-name>/`

Send that link to your students. Nothing else is required.

## What students get

- **Instant marking.** Every answer is checked on submission, with the reasoning
  explained before they move on.
- **One free retry** on numeric and proof-ordering questions, worth fewer points, so a
  slip is not final.
- **Hints** on every question, at a small points cost.
- **Proof builder.** The three derivations (Q1, Q2, Q3) and the covariance result in Q5
  are assembled by putting scrambled lines in the right order, rather than picked from a
  list.
- **A live scatter plot** in exercise 5: students drag a slider to increase the variance
  of the error term and watch the correlation collapse while the slope stays put.
- **A performance report** — accuracy, first-time accuracy, hints used, and a breakdown
  by exercise that points to the weakest topic.
- **Worked solutions**, available at any time and printable.

Progress is saved in the browser's local storage, so students can close the tab and come
back. Nothing is transmitted anywhere. If you want their results, the report screen
produces a plain-text summary they can copy into an email or a Google Form.

## Editing the questions

All content sits in the `STAGES` array near the top of the `<script>` block. Each
question is an object with a type:

- `t:"mc"` — multiple choice. `opts` is the list; `a` is the index of the correct one.
  Options are shuffled for each student, so the answer is not always in the same place.
- `t:"num"` — numeric. `a` is the answer. Commas, currency symbols and fractions such as
  `1/4` are all accepted.
- `t:"order"` — proof builder. `steps` must be listed in the correct order; the app
  scrambles them.

Every question also takes a `hint` and a `why` (the explanation shown after answering).
Mathematical notation is written as plain HTML — `<i>X</i>` for a variable, with the
`m()`, `sq()` and `frac()` helpers for maths, square roots and fractions.
