# Deep Learning Knowledge Base — Demo

A demonstration of a structured, interlinked knowledge base for deep learning, with interactive teaching materials that complement concept articles.

## What this is

This repository showcases an approach to building a personal learning resource for a complex technical domain. It combines:

- **Concept articles** — structured markdown files covering deep learning topics, interlinked with wiki-style `[[references]]`
- **Interactive teaching materials** — standalone HTML pages with step-by-step math walkthroughs, interactive simulations, and explorable visualizations
- **Reference materials** — glossary, notation guide, timeline, and key people for quick lookup

The knowledge base was seeded from François Fleuret's *The Little Book of Deep Learning* (2023) and expanded through iterative review, with articles cross-referencing each other to build a connected understanding.

## Demo scope

**5 fully developed concept articles** demonstrate the article format and editorial approach:

| Article | Description |
|---------|-------------|
| [backpropagation](concepts/backpropagation.md) | The algorithm that makes training feasible — chain rule, BPTT, adjoint method, memory requirements |
| [gradient-descent](concepts/gradient-descent.md) | SGD, learning rates, momentum, Adam, mini-batch trade-offs |
| [loss-functions](concepts/loss-functions.md) | MSE, cross-entropy (with softmax explained), contrastive loss, autoregressive loss |
| [activation-functions](concepts/activation-functions.md) | ReLU through GELU, desirable properties, initialization interaction |
| [multilayer-perceptrons](concepts/multilayer-perceptrons.md) | The simplest deep architecture, universal approximation theorem |

The remaining ~90 concept articles are **stubs** — they retain their title, tagline, and connections section to preserve the linking structure, but their full content is not included in this demo.

## Interactive teaching materials

Each material is a self-contained HTML file — no build step, no server. Try them live via GitHub Pages or clone the repo and open locally.

### Backpropagation
- **[The Math of Backpropagation](https://klauseduard.github.io/deep-learning-knowledge-base-demo/teach/backpropagation/index.html)** — partial derivatives refresher, chain rule with numbers, full forward/backward pass by hand, how autograd works. Includes synced network diagrams that highlight the active computation at each step.
- **[Vanishing & Exploding Gradients](https://klauseduard.github.io/deep-learning-knowledge-base-demo/teach/backpropagation/vanishing-gradients.html)** — simulation with controls for depth (2-50 layers), activation function, initialization scheme, skip connections, and layer normalization. Watch gradient magnitudes respond in real time.

### Gradient Descent
- **[SGD by the Numbers](https://klauseduard.github.io/deep-learning-knowledge-base-demo/teach/gradient-descent/sgd-math.html)** — worked mini-batch example: per-example gradients, averaging, parameter update, plus a multi-epoch training runner with adjustable learning rate and batch size.
- **[Gradient Descent — Interactive Learning](https://klauseduard.github.io/deep-learning-knowledge-base-demo/teach/gradient-descent/index.html)** — 3D loss landscape exploration, learning rate comparison, momentum visualization, optimizer race (SGD vs Adam).

### Loss Functions
- **[Cross-Entropy & Softmax — Worked Math](https://klauseduard.github.io/deep-learning-knowledge-base-demo/teach/loss-functions/cross-entropy-math.html)** — step-by-step: softmax computation, cross-entropy loss, gradients, parameter update, autoregressive cross-entropy with perplexity, and contrastive loss (CLIP-style).
- **[Cross-Entropy & Softmax Explorer](https://klauseduard.github.io/deep-learning-knowledge-base-demo/teach/loss-functions/index.html)** — adjust logits with sliders, watch softmax probabilities and the -log(p) loss curve respond. Temperature control, gradient visualization, presets for edge cases.

### Activation Functions
- **[Activation Function Explorer](https://klauseduard.github.io/deep-learning-knowledge-base-demo/teach/activation-functions/index.html)** — drag along curves to probe function values and derivatives, compare any two functions side by side, stack 1-30 layers to see how repeated activation crushes or preserves signals.

### Tensors
- **[Tensor Fundamentals](https://klauseduard.github.io/deep-learning-knowledge-base-demo/teach/tensors/index.html)** — interactive grid visualization of tensor shapes, indexing, reshaping, and broadcasting.

## Reference materials

| File | Contents |
|------|----------|
| [reference/notation.md](reference/notation.md) | Mathematical symbols and conventions ($\hat{y}$ = predicted, $\nabla$ = gradient, etc.) |
| [reference/glossary.md](reference/glossary.md) | 55+ term definitions (logits, softmax etymology, cross-entropy, epoch, backbone, etc.) |
| [reference/timeline.md](reference/timeline.md) | 42 milestones from McCulloch-Pitts (1943) to frontier models (2025) |
| [reference/key-people.md](reference/key-people.md) | ~40 researchers organized by contribution area |

## Structure

```
concepts/           95 topic articles (5 full, 90 stubs in this demo)
teach/              Interactive HTML teaching materials
  backpropagation/    3 pages (math walkthrough, vanishing gradients)
  gradient-descent/   2 pages (SGD math, interactive landscapes)
  loss-functions/     2 pages (cross-entropy math, interactive explorer)
  activation-functions/ 1 page (function explorer)
  tensors/            1 page (tensor fundamentals)
tools/              5 framework/library articles (stubs)
reference/          4 reference documents (notation, glossary, timeline, people)
_index.md           Master index of all articles
_connections.md     Cross-cutting themes and relationships
_sources.md         Bibliography
_open_questions.md  Unresolved questions across the field
```

## Design principles

**Concept articles** follow a consistent structure: tagline → overview → key details (intuition, etymology, technical subsections) → learn (links to teaching materials) → connections → sources → open questions. Inline `[[wiki-links]]` connect articles where concepts are naturally referenced.

**Teaching materials** use vanilla HTML/CSS/JS with CDN-hosted libraries (KaTeX for math, Plotly for charts). They follow a consistent design system (Source Serif for headings, Inter for body, JetBrains Mono for code/values). Two complementary formats:
- *Math walkthroughs* — step-through panels with concrete numbers at every step, synced diagrams
- *Interactive explorers* — parameter controls with immediate visual feedback, "what to notice" hints

**Reference materials** are look-up resources, not study materials. They support the concept articles without duplicating them.

## How to use

### Concept articles (Markdown)

The concept articles use `[[wiki-links]]` for cross-referencing and embedded Plotly charts for visualizations. To get the full experience:

1. **[Obsidian](https://obsidian.md/)** (free) — open this repository as an Obsidian vault. Wiki-links become clickable, the graph view shows connections between articles, and LaTeX math renders inline.
2. **[Obsidian Plotly plugin](https://github.com/Dmytro-Shulha/obsidian-plotly)** — install via Obsidian's community plugins to render the embedded charts in the loss-functions and activation-functions articles.

Without Obsidian, the articles are still readable as plain Markdown — `[[wiki-links]]` won't be clickable but the text is clear. The Plotly chart data is visible as YAML blocks.

### Teaching materials (HTML)

The `teach/` directory contains standalone HTML files. Just open them directly in a browser (Firefox, Chrome, etc.) — no server, no build step, no installation. They load fonts and math rendering from CDNs, so an internet connection is needed on first open.

### Reference materials (Markdown)

Plain Markdown with some LaTeX math notation. Readable in any Markdown viewer or text editor; best in Obsidian where the math renders.

## Built with

The knowledge base was built iteratively using [Claude Code](https://claude.ai/code) — article drafting, review, teaching material generation, and cross-linking were done in conversation.

## License

Content is provided for demonstration purposes. The teaching material HTML files can be opened directly in any modern browser.
