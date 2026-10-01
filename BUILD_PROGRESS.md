# BUILD_PROGRESS

Working file. Not imported by the Academy.

**Goal:** build "Knitting from Zero" — a 14-module, 66-lesson, principle-first knitting course for
complete beginners — in this repo, to the import contract in
`tals-academy/docs/new-course-instructions.md`, such that `npm run check-course` reports
`0 problems` and the first real import needs no edits.

**Plan of record:** `curriculum/plan.md`. **Binding rules:** the guidelines file (they win where
they disagree with the plan). **Course registration details:** `curriculum/course-details.md`.

## Current state

**Phase 2 — pilot lessons, awaiting Tal's review.** Foundations are complete. Three pilot lessons
(01.1, 02.1, 03.2) are written, plus 03.1 because 03.2 cannot be reviewed without it.

**Modules 4-14 are not written.** `_sidebar.md` therefore lists Modules 1-3 only. Do **not** add
modules to the sidebar until their lessons exist: every sidebar link must point to a real file, and
a missing one is an import error.

## Units

### Phase 1 — Foundations

- [x] `.gitignore`, `.gitattributes` (LF, UTF-8)
- [x] `README.md` — H1 is the course title, first paragraph is the catalog description
- [x] `glossary.md`
- [x] `references/abbreviations.md`
- [x] `references/yarn-weights-and-needles.md`
- [x] `references/fixing-mistakes.md`
- [x] `references/left-handed.md`
- [x] `templates/README.md`, `swatch-card.md`, `project-notes.md`, `sweater-worksheet.md`,
      `pattern-template.md`
- [x] `curriculum/diagram-style-guide.md` — the binding SVG style, for Tal's approval
- [x] `curriculum/video-library.md` — 35 verified YouTube videos
- [x] `assets/` — 6 sample diagrams
- [x] `labs/common/`, `labs/module-01/`, `labs/module-02/`, `labs/module-03/`
- [x] `BUILD_PROGRESS.md`, `TODO_FOR_TAL.md`

### Phase 2 — Pilot lessons (in progress)

- [x] `lessons/module-01/lesson-01.md` + `.quiz.yaml`
- [x] `lessons/module-02/lesson-01.md` + `.quiz.yaml`
- [x] `lessons/module-03/lesson-01.md` + `.quiz.yaml`
- [x] `lessons/module-03/lesson-02.md` + `.quiz.yaml`
- [x] `assessments/module-01-quiz.md` + `.quiz.yaml`
- [x] `assessments/module-02-quiz.md` + `.quiz.yaml`
- [x] `assessments/module-03-quiz.md` + `.quiz.yaml`
- [x] **`check-course` reports 0 problems** — verified 2026-10-01:
      `Knitting from Zero: 5 modules, 4 lessons, 7 quiz files, 40 questions (A-D 10/10/10/10), 0 problems`
- [ ] Tal's review of tone, depth and diagram style
- [ ] `BUILD_PROGRESS.md` updated with the review outcome

### Known deviations to fix when the modules are completed

These are tracked, not forgotten. None of them breaks the import.

1. **`assessments/module-01-quiz.quiz.yaml` tests lessons 01.2-01.5, which are not written yet.** The
   questions were written from the `curriculum/plan.md` §7 outlines, so whoever writes those four
   lessons has to land on the same conclusions: pale smooth worsted wool as the beginner default
   (q1), label reading — length, ply, fibre (q2), tension from the yarn path and not from grip
   (q3), a cast-on being only the first row and therefore redoable (q4), the right side showing
   `V`s (q6). Two further questions, on laddering a dropped stitch (q5) and on a needle being too
   large for the yarn (q7), belong to Modules 5 and 6. Tighten the quiz when 01.2-01.5 land.
2. **The Module 1 quiz page links only lesson 01.1.** Lessons 01.2-01.5 are named in plain text,
   because a link to a missing file is an import error. Re-link them once they exist.
3. **`lessons/module-02/lesson-01.md` has `prerequisites: ["01.1"]`** rather than `["01.5"]`, because
   01.5 does not exist. Change it to `["01.5"]` when Module 1 is complete, and add a sentence saying
   the cast-on from 01.5 is assumed.
4. **Lesson lengths.** 01.1 is 201 lines (~2,340 words, 11-12 minutes at 200 wpm) against a stated
   10. The four derived consequences and the "check your work" exercises were kept in preference to
   hitting the line count; either accept the longer reading time or cut content. Tal's call.

### Phase 3+ — the rest of the course (not started)

- [ ] `_sidebar.md` extended to all 14 modules, with running lesson numbers
- [ ] Modules 1-3 completed (lessons 01.2-01.5, 02.2-02.5, 03.3-03.5)
- [ ] Module 4 + `projects/p01-scarf.md`
- [ ] Module 5, 6, 7
- [ ] Module 8, 9 + `projects/p02-hat.md`
- [ ] Module 10
- [ ] Module 11, 12 + `projects/p03-sweater.md`
- [ ] Module 13 + `projects/p04-design-your-own.md`
- [ ] Module 14
- [ ] Glossary and reference cross-links converted to real links (they cite lesson numbers in plain
      text today, because the target lessons do not exist yet)
- [ ] Simulations: gauge calculator, hat designer, chart reader — **approved by Tal 2026-10-01**
- [ ] Final QA: `check-course` 0 problems, links, alt text, git clean

## Decisions taken (Tal, 2026-10-01)

| Question | Decision |
|---|---|
| Build scope this round | **Foundations + 3 pilot lessons only**, then review. Do not write all 14 modules yet. |
| Video | **Link verified YouTube videos.** 35 in `curriculum/video-library.md`, each confirmed via the oEmbed endpoint. Text and diagrams stay complete without them. |
| Simulations | **Build all three** (gauge calculator, hat designer, chart reader), in the simulations phase. |
| Printables | **Markdown + printable SVG.** No binary files in git. |
| Kit | One 5 mm (US 8) 80 cm circular needle for the whole course. |
| Left-handed support | A Continental/mirror subsection in every technique lesson + the `references/left-handed.md` translation table. No mirrored diagram files. |
| Other designers' patterns | Self-contained; link a short "further practice" list in 14.5 only. |

Open questions for Tal are in `TODO_FOR_TAL.md`.

## How to resume

1. Read this file and `curriculum/status/*.log` first. **Do not rewrite a finished lesson.**
2. Run the gate:

   ```bash
   cd C:/Users/TalGiladi/OneDrive/repos/tals-academy && npm run check-course -- ../course-creator/knitting-course
   ```

   It runs the real importer, changes nothing, and must print `0 problems`. Run it after every
   module, not only at the end.
3. Write **one lesson completely** — `lesson-MM.md`, `lesson-MM.quiz.yaml`, and a line appended to
   `curriculum/status/module-NN.log` — before starting the next.
4. Commit after every finished module.
5. At most **two writing agents at a time**, each on its own module, never the same file. Shared
   files (`_sidebar.md`, `glossary.md`, `README.md`, `labs/common/`, `templates/`) are edited only
   by the main session, between agent runs. Agents write glossary additions to
   `curriculum/glossary-inbox/module-NN.md` instead of touching `glossary.md`.
6. Add a module to `_sidebar.md` only once all its lessons and its module quiz exist.

## Style rules that are not negotiable

- Every lesson uses the **same eight `##` sections**, in this order: What you need, Why it works,
  Step by step (with a `### Left-handed and Continental` subsection), Check your work, Fixing common
  mistakes, Practice, Tips from experienced knitters, Recap. A section that does not apply stays,
  with one line saying so. Never skipped.
- Exactly one H1, `# NN.M · Title`, whose title matches the sidebar link text exactly.
- A plain intro paragraph right after the H1, which becomes the lesson's summary.
- **Every graded question is multiple choice** in a `.quiz.yaml`: 4 options, one correct, an
  `explanation`, `correct` spread across 0-3, plausible-but-wrong distractors, never "all of the
  above". 3-5 questions per lesson, 8-10 per module quiz.
- No quiz, knowledge-check or answer section in the markdown. Ever.
- Diagrams are SVG in `assets/`, named `mNN-<topic>.svg`, following
  `curriculum/diagram-style-guide.md`, with alt text that **describes the motion in words**.
- Video is one YouTube URL alone on its own line, from `curriculum/video-library.md` only.
- Only relative links, to files that exist. A link to a missing file becomes plain text on import
  and is counted as a problem.
