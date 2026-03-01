# K-ATOMS — The Atomic Unit of Knowledge

**Knowledge you can see. Data your agents can read.**

> This repository introduces a new primitive:
> **a K-Atom — an atomic, self-contained unit of knowledge that is simultaneously human-readable and machine-executable.**

K-Atoms turn files, documents, datasets and structured knowledge into **self-contained SVG/SVGZ artifacts** that:

* look like images,
* behave like databases,
* and can be consumed directly by AI agents.

---

## Why this exists (short version)

Knowledge today lives in two incompatible worlds:

* **Human-first** → documents, markdown, PDFs
* **Machine-first** → databases, APIs, embeddings

K-Atoms introduce a third category:

> **A portable, verifiable, visual knowledge unit**
> that humans can share *as an image*
> and machines can consume *as structured data*.

This is not compression.  
This is not steganography.  
This is a **new interaction primitive for human + AI systems**.

---

## Core idea

A **K-Atom** is:

* a **valid SVG/SVGZ image**
* with a **gzip-compressed payload embedded in `<metadata>`**
* containing a **mini filesystem** (text, markdown, JSON, code, datasets)
* cryptographically identifiable and optionally signed
* visually summarized by a **pure Sierpinski carpet glyph**

A K-Atom is **atomic**:
it cannot be partially understood, partially transferred, or partially consumed.

---

## The visual glyph (why Sierpinski)

Each K-Atom contains a **canonical Sierpinski carpet**:

* The **structure is fixed** (pure mathematical object)
* The **overlay is derived from `sha256(payload)`**

Result:

* same content → same visual fingerprint
* different content → different glyph
* humans get an immediate *“this is not the same K-Atom”* signal
* machines get exact hashes and signatures

This is **content-addressed knowledge — made visual**.

---

## What’s in this repo

This repo ships a **fully client-side** reference implementation:

* **K-Atom Maker** — convert files into K-Atoms
* **K-Atom Viewer** — load an image and recover the knowledge

No backend.  
No server required.

---

## Features (v0.22)

### Maker

* Upload:
  * `.txt`, `.md`, `.csv`, `.json`
  * `.pdf` (text extracted via PDF.js)
* Generate:
  * `artifact.svg` or `artifact.svgz`
* Automatically:
  * builds a structured payload
  * generates a human-readable visual cover
  * embeds compressed data inside SVG metadata
* Optional:
  * **Ed25519 signature** (payload integrity + authorship)

### Viewer

* Load a K-Atom:
  * via **file upload** (`.svg` / `.svgz`)
* Extract:
  * full payload
  * original file
  * or a `.zip` bundle
* Browse:
  * tree view (`input/`, `derived/`, `README.md`, etc.)
  * Markdown rendering
  * CSV preview
  * JSON pretty print
* Verify:
  * **cryptographic signature** (Ed25519)

---

## What makes K-Atoms different (the non-obvious part)

### 1. Atomic knowledge

Everything needed to understand or reuse the content is **inside the K-Atom**.

* No broken links
* No missing context
* No dependency on external storage

---

### 2. Shareability across hostile channels

Images survive where files don’t.

You can:

* send a K-Atom over chat
* post it on image-based platforms
* archive it offline
* pin it visually

Try doing that with a ZIP file.

---

### 3. Human + AI symmetry

The same K-Atom supports:

* **human reading** (visual + markdown)
* **agent ingestion** (structured payload)

No duplication.  
No separate “doc vs data” pipelines.

---

### 4. Verifiable by design

Every K-Atom can include:

* `sha256(payload)`
* Ed25519 signature
* deterministic visual fingerprint

This enables:

* trust
* provenance
* reproducibility
* auditability

---

## Emergent advantage: size vs. meaning (why this scales)

One non-obvious property of K-Atoms is **how much usable knowledge fits inside a small image**.

Because K-Atoms use:
- structured text (Markdown / JSON),
- deterministic gzip compression,
- and SVG/SVGZ as a container,

the ratio between **file size** and **semantic content** is radically different from traditional formats.

### A practical reference (not a benchmark)

These numbers are not limits — they are *reference orders of magnitude* observed in practice.

- A **~10 KB SVGZ K-Atom**
  - can typically expand to **~50–150 KB** of uncompressed payload
  - depending on structure, redundancy, and text entropy

That means:

- ~50–150 KB of **pure structured text**
- which roughly corresponds to:
  - **25–60 pages** of Markdown / technical text
  - or a **small paper**
  - or a **non-trivial dataset / mini-CRM**
  - or a **full agent context bundle**

Now extrapolate:

- **100 KB SVGZ** → hundreds of KB to multiple MB of structured knowledge  
- **300 KB SVGZ** → potentially *entire repositories*, playbooks, or research bundles  

All still packaged as:
> a single image.

### Why this matters (beyond compression)

This is not just about saving space.

The emergent advantages are:

- **Portability**
  - images travel where ZIPs, databases and folders don’t
- **Atomicity**
  - one K-Atom = one complete knowledge unit
- **Context integrity**
  - nothing is “external” or missing
- **Human + AI symmetry**
  - humans see a visual summary
  - agents extract structured data

The size efficiency is just the visible side-effect  
of treating **structure as the primary compression layer**.

---

## Mini documentation

### Create a K-Atom

1. Open the app
2. Go to **Maker**
3. Upload a file
4. Click **Generate artifact**
5. Download `.svg` or `.svgz`

### Recover content from a K-Atom

1. Go to **Viewer**
2. Upload the image
3. Browse files
4. Export original or full bundle
5. (Optional) Verify signature

---

## Use cases & applications: What can you build with K-Atoms?

Below are **real, non-theoretical use cases**.

---

### 1. Scientific & technical papers as K-Atoms

A single K-Atom can contain:

* full paper (Markdown)
* datasets
* code
* metadata
* references

One image = one reproducible research unit.

---

### 2. ArangoDB + K-Atoms (graph + vector + image)

K-Atoms integrate naturally with **GraphDBs and RAG systems**:

* Store each K-Atom as a **document**
* Extract:
  * graph relationships (citations, dependencies, authorship)
  * vectors (embeddings generated from payload)
* Use the image as:
  * the **atomic knowledge node**
  * human-facing preview
  * machine-facing data source

This enables:

* graph reasoning
* vector search
* provenance tracking  
all starting from a single K-Atom.

---

### 3. AI orchestration & pipelines

K-Atoms can be:

* inputs to agents
* outputs of agents
* checkpoints in workflows

Example:

* Agent researches → outputs a K-Atom
* Next agent consumes the K-Atom → extends it → emits a new K-Atom

This creates **visual, inspectable AI pipelines**.

---

### 4. Agent memory capsules

Store an agent’s state as a K-Atom:

* context
* rules
* notes
* intermediate results

Agents can:

* load the image
* extract structured context
* continue reasoning

Humans can:

* see, version and share agent memory visually

---

### 5. Knowledge Pinterest / Visual GitHub

A grid of images where:

* each image = one K-Atom
* clicking reveals markdown, code, data
* visual similarity hints semantic similarity

This is a **GitHub where commits are images**.

---

### 6. Offline-first knowledge distribution

Ideal for:

* field operations
* education
* governance
* research sharing

No infrastructure required once the image exists.

---

## What K-Atoms are NOT

* ❌ Not QR codes
* ❌ Not steganography hacks
* ❌ Not image compression tricks
* ❌ Not “metadata in SVG”

K-Atoms are a **new knowledge primitive** with:

* a visual surface
* a structured core
* and a verifiable identity

---

## Status

* v0.23 — **spec closed**
* Pure Sierpinski carpet glyph
* Client-side Maker + Viewer
* SVG/SVGZ only (by design)

---

## If this makes you uncomfortable — good.

That usually means:

* you’re seeing a new primitive
* not just a new tool

---

## Next directions (open)

* gallery mode (Pinterest-style)
* URL loading with proxy fallback
* publisher keys & trust chains
* graph-native indexing
* agent-native protocols

---

**If you build something weird with K-Atoms, that’s the point.**

---

## Conceptual Notice

K-ATOM is introduced here as a **knowledge primitive**.

While this repository is licensed under Apache 2.0,
the authors ask that derivative works, research, or systems
that build upon this concept explicitly reference
**K-ATOM** as the originating primitive.

This is not a legal restriction — it is a request
to preserve conceptual attribution and historical continuity.
