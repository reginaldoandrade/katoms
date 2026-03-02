# ⚛️ K-ATOMS — The Atomic Unit of Knowledge

**Knowledge you can see. Data your AI agents can read.**

> **K-ATOMS** introduces a new digital primitive: an atomic, self-contained unit of knowledge that is simultaneously human-readable and machine-executable. This is not just a file format; it is a **Content-Addressed Knowledge** system designed for the era of Human-AI collaboration.

---

## Why this exists

Knowledge today lives in two incompatible worlds:

* **Human-first:** Documents, PDFs, and Markdown (visual, but lossy for machines).
* **Machine-first:** Databases, APIs, and Embeddings (structured, but invisible to humans).

**K-Atoms introduce a third category:** A portable, verifiable, visual knowledge unit that humans share as an image and machines consume as structured data.

---

## Core Idea: The Atomic Primitive

A **K-Atom** is a valid **SVG/SVGZ** artifact with a Gzip-compressed payload embedded in its `<metadata>`. It is **atomic**: it cannot be partially understood, partially transferred, or partially consumed.

### The Visual Glyph (Sierpinski Fingerprint)

Each K-Atom contains a canonical Sierpinski carpet.

* The structure is a fixed mathematical object.
* The visual overlay is derived from `sha256(payload)`.
* **Result:** Same content → same visual fingerprint. Different content → different glyph. Humans get an immediate "signal" of integrity; machines get exact cryptographic hashes.

---

## What makes K-Atoms different (The non-obvious part)

### 1. Hostile Channel Resilience

Images survive where files don’t. You can post a K-Atom on image-based platforms, send it via chat, or archive it visually. While a ZIP might be blocked or stripped, the SVG persists as a valid image.

### 2. Emergent Advantage: Size vs. Meaning

This is not just about compression; it is about **Structure as Compression**.

* A **~10 KB SVGZ** K-Atom can expand to **~150 KB** of uncompressed payload.
* This corresponds to ~60 pages of technical text or a full agent context bundle.
* The ratio between file size and **semantic content** is radically superior to traditional formats.

### 3. Human + AI Symmetry

No more "doc vs. data" pipelines. The K-Atom is the single source of truth.

* **Humans** see the visual summary and can "read" the intent through AR or OCR.
* **Agents** extract the structured JSON/Markdown core via the metadata layer.

---

## Use Cases & Applications


### 1. Scientific & technical papers as K-Atoms

A single K-Atom can contain:

* full paper (i.e. Markdown, PDF, TXT,and, etc.)
* datasets (i.e. CSV, JSON, and, etc.)
* code (i.e. R, M, C, Python, and, etc.)
* metadata
* references

One image = one reproducible research unit.

---

### 2. K-Atoms + ArangoDB (graph + vector + image)

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

### 7. Web3 & Content-Addressed Knowledge

By linking the visual fingerprint to the SHA-256 hash, K-Atoms act as **physicalized hash-keys**. They are the perfect container for decentralized data, where the image itself serves as the verifiable proof of the data it carries.

---

### 8. Actionable Physicality (AR/Camera)

Since K-Atoms are visual, they are designed to be **actionable in the real world**.

* Pointing a camera at a printed K-Atom (or screen) can trigger a summary description.
* Mobile agents can "see" the info, extract the hash, and pull the full payload, making offline knowledge instantly discoverable.

---

## Features (v0.22)

### Maker

* **Multiformat Upload:** `.txt`, `.md`, `.csv`, `.json`, and `.pdf` (text extracted via PDF.js - No needed).
* **Deterministic Generation:** Automatic building of structured payloads and visual covers.
* **Cryptography:** Optional **Ed25519 signature** for authorship and integrity.

### Viewer

* **Zero-Server Extraction:** Fully client-side recovery of the original files or `.zip` bundles.
* **Deep Inspection:** Tree view of the internal filesystem, Markdown rendering, and JSON pretty-printing.
* **Verification:** Real-time cryptographic signature validation.

---

## Implementation Details

This repository ships as a **Pure JavaScript** reference implementation.

* **No Backend Required.**
* **No Node_Modules Bloat.**
* **Zero Infrastructure.**

It is designed to be lightweight enough to run in a browser, an Electron app, or as a module for an AI Agent's toolset.

---

## Get Started

1. Clone the repo.
2. Open `index.html` (no `npm install` needed).
3. Drop a file and create your first Atom.

---

## What K-Atoms are NOT

* ❌ **Not QR codes:** They carry the actual data, not just a link.
* ❌ **Not steganography:** We are not "hiding" data; we are using valid SVG metadata standards.
* ❌ **Not image compression:** We are using structure to maximize semantic density.

---

## Conceptual Notice

K-ATOM is introduced as a **knowledge primitive**.
While this repository is licensed under **Apache 2.0**, we ask that derivative works or systems building upon this concept explicitly reference **K-ATOM** as the originating primitive to preserve conceptual attribution and historical continuity.

---

**If you build something weird with K-Atoms, that’s the point.**
