# System Architecture: RAGfish

## Overview
RAGfish is a privacy-first, on-device Retrieval-Augmented Generation (RAG) engine for Apple platforms. The core system is designed to run fully locally, without cloud dependencies, and can be extended for both macOS and iOS.  
Visual architecture diagrams are available below and in `assets/`.

- ![Class Diagram](assets/ClassDiagram.png)
- ![Sequence Diagram](assets/SequenceDiagram.png)
- ![Use Case Diagram](assets/UseCaseDiagram.png)

## Components

- **Core Engine**
  - Handles all LLM model inference, embedding, and retrieval logic.
  - Written for Apple Silicon (Metal/CoreML or native C/C++ backends).
  - Example: Efficient vector search and prompt construction modules.
- **Document/Embedding Manager**
  - Manages all user documents, chunked/embedded RAGpacks, and handles import/export.
  - Supports preprocessed ZIP import (RAGpack format).
  - Example: Document chunking, embedding caching, and metadata indexing.
- **UI (Noesis)**
  - SwiftUI-based interface for chat, file management, settings.
  - Separated from business logic for platform flexibility.
  - Example: Responsive chat interface, document browser, and preferences panel.
- **File Import/Export**
  - Local file system and Google Drive integration.
  - Handles user data and model/resource import.
  - Example: ZIP unpacking, file format validation, and cloud sync hooks.

## Data Flow

- User launches RAGfish, which loads default embedded model and sample RAG DB.
- User can import additional RAGpacks (preprocessed ZIPs from Colab or CLI).
- User queries via chat; query is embedded and searched in the local vector store.
- Relevant chunks are retrieved; RAG pipeline combines prompt + context, sends to LLM for answer.
- All operations occur locally; no network/cloud access is required.
- Example: Query embedding → vector similarity search → prompt assembly → LLM inference → response display.

## Dependencies

- Apple Silicon (macOS/iOS, M1+)
- Swift (UI/business logic)
- C/C++/Metal/CoreML (backend performance)
- PlantUML or Mermaid (for architecture diagrams)
- Optional: Google Drive API (for import/export)
- Example: CoreML for model acceleration, Swift concurrency for UI responsiveness.

## Extensibility

- Add support for new LLM/embedding models (GGUF, CoreML, etc)
- Future iOS-specific UX/UI enhancements
- Encrypted storage, biometric unlock, or multi-user support
- Serverless sharing of vector stores or models
- Plugin system for 3rd-party data connectors (TBD)
- Example: Modular backend interfaces, pluggable import/export adapters, secure data layers.