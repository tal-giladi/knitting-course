# Diagram style guide (production reference)

Binding for every SVG in `assets/`. Production guidance only: this file lives under
`curriculum/`, which is never imported, so learners never see it. The three sample diagrams
`m01-loop-chain.svg`, `m02-knit-motion.svg` and `m03-stockinette-spiral.svg` were approved by
Tal as the reference set (see the revision log at the bottom).

The course must be complete without any diagram: text and tables carry the full information, and
each diagram adds the one thing prose cannot show — a **motion**, a **structure**, or a **cause**.

## 1. File conventions

| | |
|---|---|
| Location | `assets/` at the repo root |
| Name | `mNN-<topic>.svg`, lowercase, hyphens, no spaces. `mNN` is the module number. |
| Format | SVG 1.1, plain, no `<script>`, no external fonts, no CSS classes needing JS |
| Size | `viewBox="0 0 W H"` plus matching `width`/`height` in px, so it scales in the Academy |
| Background | Self-contained light card (see §2) so it reads in both light and dark themes |
| Fonts | `font-family="Arial, Helvetica, sans-serif"` only |
| Accessibility | `<title>` and `<desc>` inside the SVG, in plain words describing the motion |

Lessons reference them from a lesson at `lessons/module-NN/`:

```markdown
![Right needle tip enters the front loop of the stitch from the left](../../assets/m02-knit-motion.svg)
```

Alt text must **describe the motion or the structure in words**. It is what a screen-reader user
gets instead of the drawing, so "Right needle tip enters the front loop of the stitch from the left"
is right and "knit stitch" is not.

## 2. Canvas and contrast

Every diagram is a self-contained light card, because an SVG loaded as an image cannot inherit the
page theme. This is the one place we are allowed to assume a background — and we assume the
*light* one, then keep every ink colour dark enough to read on it.

| Token | Value | Used for |
|---|---|---|
| Card | `#FAF8F5` fill, `#D8D2C8` stroke, `rx="10"` | the rounded panel behind everything |
| Left needle | `#2A6F97` | the left needle, always labelled `L` |
| Right needle | `#C1502E` | the right needle, always labelled `R` |
| Working yarn | `#6A994E` | the yarn that feeds the next stitch |
| Fabric ink | `#3D405B` | existing stitches, loops, rows, the fabric |
| Highlight | `#7A5195` | motion arrows, numbered step markers |
| Problem | `#B23A48` | a mistake, a hole, a wrong stitch, an error marker |
| Text ink | `#22252A` | all labels |
| Muted ink | `#6B6E76` | secondary labels, measurements, guides |

Contrast against `#FAF8F5` is at least 4.5:1 for text and 3:1 for the structural lines.

### Never rely on colour alone

This is a hard requirement, and colour-blind learners and anyone printing in greyscale depend on
it. Every diagram must remain unambiguous in greyscale. Therefore:

- **Needles** are long tapered bars with rounded caps, and carry a visible `L` / `R` letter.
- **Yarn** is a wavy or rope-like line, visibly different from the straight needle shafts.
- **Fabric** is drawn as actual loops (U shapes and V shapes), never as a shaded block.
- **Motion** is shown with arrows that carry a number (`1`, `2`, `3`) matching the lesson's steps.
- **Mistakes** carry a `✗` mark and a label such as "hole", not just a red circle.

## 3. Drawing the three things that recur

### The needles

A needle is a long, slightly tapered bar, drawn at about 8-10 px thick, with a pointed tip. It is
never a plain line. Behind the tip, put a small rounded rectangle for the "thumb rest" only if it
helps orientation; skip it in small diagrams.

- Left needle: `#2A6F97`, label `L` near the butt end, always at the left of the canvas.
- Right needle: `#C1502E`, label `R`, always at the right of the canvas, or crossing over.
- A **circular** needle cable is a thin `#2A6F97`/`#C1502E` line joining the two butts.

Right-handed convention: the yarn comes from the **right**, and the right needle enters from the
**right**. Mirror knitting is the horizontal flip of the whole canvas, which is why nothing in a
diagram may depend on left/right asymmetry beyond the needle positions themselves.

### The loops

Existing fabric is drawn as real loops, and a loop must read as a loop at a glance:

| Stitch | Seen from | Drawn as |
|---|---|---|
| Knit, right side | facing you | a `V` — two straight legs meeting at the bottom |
| Knit, wrong side | facing you | a bump — a small arch `∩` |
| Purl, right side | facing you | a bump `∩` |
| Purl, wrong side | facing you | a `V` |
| Cast-on loop | on the needle | a `U` hanging off the needle shaft |
| A live loop on a needle | on the needle | a `U` whose legs straddle the shaft |

A `V` is two straight segments; a bump is an arc. Do not use a `V` and a `∩` of the same stroke
weight for different things in the same diagram without a label.

### The arrows

A motion arrow is a curved or straight `#7A5195` line with a filled triangular head and a number in
a small circle at its start. Direction must be unambiguous: the head is clearly larger than the
shaft. For "insert the needle", the arrow runs along the direction of travel; for "wrap the yarn",
the arrow curves around the tip. A diagram with more than three arrows should become two diagrams.

## 4. Composition rules

- One idea per diagram. If you need "and then", it is two diagrams.
- Orient the work the way a learner holds it: fabric at the bottom, needles above, hands implied.
- Panels for a sequence are equal-sized, left to right, in reading order, with a step number in the
  top-left of each panel and a thin separator. Never number them out of order.
- Label every dimension that the lesson's maths depends on (`5 cm`, `20 sts`), using muted ink and
  a dimension line with arrowheads at both ends.
- Keep 24 px of padding inside the card. Nothing touches the card edge.
- Text is 15 px minimum, 17-18 px for anything a learner must read while knitting.

## 5. What each diagram type is for

| Type | Answers | Example |
|---|---|---|
| Motion | "what do my hands do?" | `m02-knit-motion.svg` — the four steps of a knit |
| Structure | "what am I looking at?" | `m02-knit-faces.svg` — a V and a bump, labelled |
| Cause | "why did that happen?" | `m03-stockinette-spiral.svg` — why the edges curl |
| Compare | "which one, and what changes?" | `m03-garter-vs-stockinette.svg` |
| Count | "how many?" | a swatch with a counting bracket |

A "cause" diagram is the most valuable kind in this course and the one beginners rarely get. When
a lesson explains why something happens, include one.

## 6. Checklist before committing a diagram

- [ ] Reads correctly with all colour removed (grayscale print test).
- [ ] Every needle carries `L` or `R`; the yarn is visibly a yarn, not a line.
- [ ] Every motion arrow has a number that matches the lesson's step number.
- [ ] `<title>` and `<desc>` present and describing the motion, not naming the file.
- [ ] Alt text in the lesson describes the motion in words, independently of the file name.
- [ ] Nothing depends on the light/dark theme of the page.
- [ ] No `<script>`, no external font, no embedded raster image.
- [ ] The lesson it belongs to reads correctly if the image is never loaded.

## 7. Revision log

- **2026-10-01** — first version, written for the pilot. Sample diagrams `m01-loop-chain.svg`,
  `m02-knit-motion.svg` and `m03-stockinette-spiral.svg` submitted for Tal's review.
