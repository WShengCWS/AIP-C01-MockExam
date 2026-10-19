# AIP-C01 Practice Exam

A single-file, offline practice exam for the **AWS Certified Generative AI Developer – Professional (AIP-C01)** certification. 161 scenario-based questions with explanations, per-question tips, and progress tracking. No build step, no dependencies, no server.

## Quick start

1. Download `AIP-C01_Practice_Exam.html`.
2. Open it in any modern browser.

To host it, enable **GitHub Pages** (Settings → Pages) and serve the file, or rename it to `index.html`.

## Features

- **Browse**: filter by domain, status (wrong / bookmarked) and search, with optional answer reveal.
- **Quiz**: pick a domain, question count and order, then get instant feedback after each answer.
- **Exam**: timed mock exam (default 180 minutes) with question flagging and a final score report.
- **Wrong**: review and retry the questions you missed.
- **History**: past attempts, with per-domain breakdown, export and import.
- **Explanation dropdown**: correct answer plus rationale for every question, with an optional auto-open setting.
- **Tips dropdown**: one question-specific tip each, covering the clue words in the stem and the common trap.
- **Keyword highlighting**: AWS services, API names and key exam concepts are highlighted in explanations and tips. Toggle it with "Highlight keywords" on the quiz setup screen.
- Multi-select questions ("Select TWO/THREE"), bookmarks, and light, dark or auto theme.

## Data and privacy

Everything runs locally in your browser. Progress, bookmarks, history and settings are stored in `localStorage`, so nothing is sent anywhere. Clearing site data erases your progress, so use **History → Export backup** first and **Import backup** to restore it.

## Project structure

```
AIP-C01_Practice_Exam.html   # app, styles, and question data in one file
```

Inside the file:

| Element | Purpose |
| --- | --- |
| `<script id="qdata">` | Questions as JSON: `n` (number), `d` (domain index), `s` (stem), `o` (options), `a` (correct indexes), `e` (explanation paragraphs) |
| `<script id="tipdata">` | Tips as JSON, keyed by question number |
| `KW_RE` | Regex that controls which terms are highlighted |
| `TIPS` / `tipsHTML()` | Tip rendering. Questions without a tip fall back to generated generic tips |

### Editing content

- **Add or change a question:** edit the `qdata` JSON.
- **Add or change a tip:** edit the entry for that question number in `tipdata`.
- **Add highlight terms:** extend the alternation in `KW_RE`.

## Disclaimer

This is an unofficial study aid and is not affiliated with or endorsed by Amazon Web Services. Explanations and tips may contain errors, so verify against the [official AWS documentation](https://docs.aws.amazon.com/) and the official exam guide. Passing this practice exam does not guarantee a passing result on the real exam.
