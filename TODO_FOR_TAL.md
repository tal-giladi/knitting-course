# TODO_FOR_TAL

Working file. Not imported.

## Blocking: your review of the pilot

The course is at the plan's **phase 2 checkpoint**: foundations are done, and three pilot lessons
are written so you can judge whether the rest of the course is worth writing in this voice.

Please look at these four, in this order:

| | File | What I need from you |
|---|---|---|
| 1 | `lessons/module-01/lesson-01.md` | A concept lesson. Is the "why it works" section the right depth for a beginner? |
| 2 | `lessons/module-02/lesson-01.md` | A technique lesson. Are the numbered steps plus one diagram per step enough to learn from, or do you miss something? |
| 3 | `lessons/module-03/lesson-02.md` | The principle lesson — the one that has to justify the whole course. Does the stockinette-curling explanation land? |
| 4 | `assets/m01-loop-chain.svg`, `assets/m02-knit-motion.svg`, `assets/m03-stockinette-spiral.svg` | **The three sample diagrams**, per the plan's phase 1. If the diagram style is wrong, 66 lessons of diagrams are wrong, so this is the most expensive thing to get wrong. |

I also wrote 03.1 (the purl stitch) even though the plan names only three pilots, because 03.2
cannot be reviewed without it.

Three questions, and my answers so you can overrule them:

1. **Is the tone right?** Plain, specific, second person, no cheerleading. The plan asks for
   principle-first, so every lesson has a `Why it works` section — is that a welcome idea or a
   lecture?
2. **Are the quizzes too easy?** They are written to test reasoning, not recall, per the plan.
3. **Anything wrong with the kit or the order?** The course assumes one 5 mm circular needle for
   everything.

Two things you should know about rather than discover later:

- **Lesson 01.1 is longer than its stated 10 minutes** — about 11-12, because the four consequences
  derived from "one strand" and the check-your-work exercises were kept rather than cut to hit a
  line count. Say the word and I will cut it; it means losing a consequence or an exercise.
- **The Module 1 quiz asks about lessons that are not written yet.** It was built from the plan's
  outlines for 01.2-01.5, and two of its eight questions (a dropped stitch, a needle too large for
  the yarn) really belong to Modules 5 and 6. It imports cleanly and the questions are sound, but
  I will tighten it when those lessons are written.

## What is decided and does not need you

These are settled from your answers on 2026-10-01 and are recorded in `BUILD_PROGRESS.md`:
pilot-first scope, verified YouTube links, all three simulations, markdown + SVG printables.

## Still open, from the plan's §12

| # | Question | My recommendation |
|---|---|---|
| 1 | **Test-knitting.** Who knits the scarf, hat and sweater patterns before they ship, and in which sizes? | This is the real schedule risk, not the writing. The plan promises all three patterns test-knitted in at least two sizes. A volunteer learner group is probably fastest; Tal plus family is most reliable. |
| 2 | **Sweater scope.** One pullover sized 80-150 cm chest, or also child sizes and a cardigan? | One pullover, full adult range. A cardigan is a second pattern and a second test-knit. |
| 3 | **Free or paid.** `curriculum/course-details.md` suggests free. | Free, as drafted. |
| 4 | **Mirrored diagrams.** Continental subsection plus the translation table, or mirrored diagrams for every technique too? | What is built now: subsections + one translation table. Mirrored diagram files are roughly double the diagram work for a small slice of learners. |
| 5 | **Photos.** Close-up photos for "reading your knitting" and "what good looks like" — shoot our own, or drawn diagrams only? | Diagrams now, and real photos later if the Academy's art budget allows. Drawn is also a correctness win: a photo of "this is a dropped stitch" needs a model, a camera and a reshoot. |
| 6 | **Printable PDFs.** Currently markdown + SVG. Add generated PDFs? | No. The guidelines discourage binaries in git, and the markdown already prints. |

## Housekeeping you will need to do

- [ ] **Git remote.** No remote is set up. The course needs to be pushed to
      `tal-giladi/knitting-course` (public) for the Academy to import it.
- [ ] **Register the course** in the Academy from `curriculum/course-details.md` when the course
      is complete, not now.
- [ ] **Decide the slug.** Suggested: `knitting`.

## Known gaps, so nothing is a surprise

- **Modules 4-14 do not exist yet.** `_sidebar.md` lists Modules 1-3 only, because a sidebar link
  to a missing file is an import error.
- **The glossary cites lessons in plain text** ("introduced in 06.1") rather than linking, because
  those lessons are not written. A final pass converts them to links once the modules exist.
- **Diagrams are machine-checked, not eyeballed.** Every SVG is verified for well-formed XML, for
  geometry inside its canvas, and for text that overflows the card. Nobody has looked at them with
  a human eye yet, which is why they are the first item in the review table above.
- **The patterns are not test-knitted.** They do not exist yet either. The plan's own QA gate for
  them is "all three patterns test-knitted in at least two sizes with no open errata", and that
  gate is not near.
