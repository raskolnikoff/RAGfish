# RAGfish

A deep private RAG core for macOS/iOS, inspired by the depths of the ocean.

## Features
- 🛡️ Privacy-first, fully on-device RAG
- 💻 Runs natively on Apple Silicon (macOS/iOS, M1+)
- 🐟 Pre-packaged with embedded models and sample "RAGfish DB" for instant exploration
- 🗂️ Supports user-imported RAGpacks (chunked & embedded docs, ZIP format)
- Multi-RAGpack support
- Threaded Q&A history
- Full Apple Silicon optimization
- ⚡️ Fast local search, summary, and QA—no cloud, no tracking
- Future plans: web & cloudless multi-user collaboration

## Quick Start
1. Download and launch [NoesisNoema app](https://github.com/raskolnikoff/NoesisNoema) for macOS
2. (Optional) Preprocess your own docs using the [RAGpack Colab Preprocessor Notebook](https://github.com/raskolnikoff/noesisnoema-pipeline/blob/main/notebooks/chunks_and_embeddings_colab.ipynb) from the noesisnoema-pipeline project, download the RAGpack ZIP, and import it in-app
3. Start asking questions in natural language. Enjoy!

*Note: Official release builds are coming soon. For now, use the main branch of NoesisNoema app. See [RAGfish](https://github.com/raskolnikoff/RAGfish) for specs and dev tools.*

## Ecosystem & Related Projects

RAGfish is the core RAGpack specification and toolkit.  
It is designed to be used with the following companion projects:

### NoesisNoema (macOS/iOS App)
- **Reference implementation:** A private RAG client for macOS (and iOS, WIP) that leverages RAGfish RAGpack format.
- **Features:**  
  - Full offline, on-device retrieval-augmented generation (RAG)
  - QA history & thread management (your questions are stored and retrievable)
  - Multi-RAGpack support (import as many knowledge packs as you want)
  - Modern two-pane UI (QA history/threads, detail view, future extensibility)
  - Privacy-first, Apple Silicon optimized
- **Get started:**  
  1. Download [NoesisNoema](https://github.com/raskolnikoff/NoesisNoema)
  2. Import RAGpacks (sample or your own)
  3. Ask questions, explore knowledge, see instant answers with cited chunks

### noesisnoema-pipeline (Colab/CLI Preprocessing Toolkit)
- **Reference pipeline:** Create your own RAGpack (.zip) from PDF/text using Google Colab or CLI.
- **Features:**  
  - Chunking & embedding for any document (English or multilingual)
  - Outputs compatible RAGpack (.zip) for direct import in RAGfish/NoesisNoema
  - Supports export of both `.npy` and `.csv` for easy integration (see docs)
  - Fast prototyping: no local environment required if using Colab
- **Get started:**  
  1. Go to [noesisnoema-pipeline](https://github.com/raskolnikoff/noesisnoema-pipeline)
  2. Follow the notebook or CLI steps to generate your own RAGpack from PDF or text
  3. Download and import the RAGpack (.zip) in NoesisNoema or RAGfish

### Architecture Overview

```
[Your docs/architect/ARCHITECTURE.md and diagrams describe the RAGfish architecture, RAGpack format, and the flow between pipeline, core, and app.]
```

## Business Workflow Transformation: As-Is vs. To-Be

See how RAGfish revolutionizes document Q&A and knowledge workflows compared to conventional approaches:

![Business Workflow: As-Is vs. To-Be](docs/assets/noesisnoema.png)

**Key Benefits:**
- Unified, instant document Q&A (no more fragmented search)
- On-device privacy—no cloud, no leaks
- Fully offline, always available
- Easy to extend with your own knowledge packs (RAGpacks)
- Built for business productivity and compliance

## Project Philosophy

RAGfish is built on the principle that knowledge work should remain private, powerful, and beautiful—like the silent depths of the ocean. We believe LLM-powered RAG should require no server, no login, and no risk. Your documents, your brain—on your device.


## Diagrams

### Class Diagram
![Class Diagram](docs/assets/ClassDiagram.png)

### Sequence Diagram
![Sequence Diagram](docs/assets/SequenceDiagram.png)

### Component Diagram
![Component Diagram](docs/assets/ComponentDiagram.png)

### Use Case Diagram
![Use Case Diagram](docs/assets/UseCaseDiagram.png)

## Documentation
- [Architecture](./docs/architect/ARCHITECTURE.md)
- [Design Docs (WIP)](./docs/designs/)
- [ADRs (WIP)](./docs/adr/)

## Roadmap / Future Plans

- iOS universal app (currently macOS-focused)
- Advanced chunk highlighting, source trace, and cross-document QA
- In-app RAGpack generation (pipeline-less)
- UI/UX: Enhanced right-pane for document preview, chunk roots, or annotation
- Cloudless peer-to-peer knowledge sharing (private multi-device sync)
- More LLM model support (future Apple ML, third-party LLMs)
- API for plugin and automation extension
- More: See [Issues](https://github.com/raskolnikoff/ragfish/issues)

## License
[MIT](./LICENSE)