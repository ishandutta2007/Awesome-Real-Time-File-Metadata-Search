# Awesome-Real-Time-File-Metadata-Search

# Awesome Real-Time File & Metadata Search

> A curated list of top Real-Time File and Metadata Search platforms — both SaaS/Hosted commercial search and discovery engines and open-source alternatives for indexing and querying files, documents, and metadata with low latency.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Druva Live Search & Federated Search](#druva-live-search--federated-search)
  - [Algolia](#algolia)
  - [Glean](#glean)
  - [Coveo](#coveo)
- [Open-Source Software](#-open-source-software)
  - [Meilisearch](#meilisearch)
  - [Typesense](#typesense)
  - [sist2](#sist2)
  - [Tamsaek](#tamsaek)
  - [InfoGrep](#infogrep)
  - [dsearch](#dsearch)
  - [Project Indexly](#project-indexly)
  - [drivedex](#drivedex)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Real-Time File and Metadata Search platforms. These are not open-source but are included as reference points for feature comparison.

### Druva Live Search & Federated Search
**Type:** Data protection-native search with near-real-time indexing  
Druva's inSync maintains a unified index structure across the entire archive, with each message stored as a single instance containing metadata about its mailbox. This enables **near real-time search across multiple mailboxes or the entire repository** [citation:1][citation:18]. The index is generated before content is added to the archive, ensuring all items are searchable. **Federated Search** allows organizations to locate files across endpoints and cloud apps, identifying which device or cloud app stores a file and even the device's geographic location [citation:26]. Legal holds and eDiscovery are supported natively, with pre-ingestion culling filters to reduce downstream review costs [citation:26].  
**Best for:** Druva customers needing compliance-grade search across backup data for eDiscovery and investigations, with native legal hold integration.

### Algolia
**Type:** AI search and retrieval platform with agentic capabilities  
Algolia orchestrates over 1.75 trillion queries annually across 18,000+ businesses [citation:2]. Its **Agent Studio** (January 2026) brings agentic AI directly into the search bar, making the search experience a unified entry point for questions, exploration, and answers grounded in trusted data [citation:2]. The platform supports hybrid search, vector search, keyword relevance, rules, and personalization, with a model-agnostic architecture supporting any OpenAI-compatible LLM and native MCP alignment [citation:2].  
**Best for:** Developers wanting a production-grade search API with agentic capabilities, strong relevance tooling, and no infrastructure management.

### Glean
**Type:** Enterprise AI coworker with permission-aware search  
Glean connects to apps and documents across the company, finding information across connected apps with results limited to what the user already has permission to see [citation:3]. It provides grounded answers with citations, people discovery, and can be used as company context inside supported AI tools through MCP [citation:3]. Search is one job among many—Glean also drafts work, summarizes documents, and moves tasks forward [citation:3].  
**Best for:** Organizations wanting a permission-aware enterprise search and AI coworker that connects siloed knowledge across SaaS tools.

### Coveo
**Type:** AI search platform with conversational agent  
Coveo's **Search Agent** (Open Beta, March 2026) brings conversational search with memory and contextual awareness, handling follow-up questions without losing context [citation:4]. It is a fully managed "Agentic RAG" solution with out-of-the-box UI components via Coveo Atomic library [citation:4]. Traditional search capabilities include intelligent query suggestions, semantic understanding, dynamic navigation, and real-time behavior signals [citation:13].  
**Best for:** Enterprises wanting managed conversational search with strong relevance and agentic capabilities for service, website, and workplace use cases.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Real-Time File and Metadata Search tools. The open-source ecosystem spans **lightning-fast search engines**, **filesystem indexers with metadata extraction**, **local search with MCP integration**, and **cloud file indexers**.

### Meilisearch
**Stack:** Rust | **License:** MIT  
Meilisearch is a lightning-fast search engine designed for instant search experiences, with **search-as-you-type results in under 50 milliseconds** [citation:5]. Features include typo tolerance, filtering and faceted search, sorting, synonym support, geosearch, multi-tenancy, and a RESTful API [citation:5]. Recent additions include **hybrid search** (semantic + full-text), **conversational search** with AI-generated answers grounded in results, and **AI-ready** out-of-the-box integration with LangChain and MCP .  
**Best for:** Developers wanting a fast, easy-to-deploy search engine for apps and websites with minimal configuration and strong developer experience.

### Typesense
**Stack:** C++ | **License:** GPL-3.0  
Typesense is an open-source, typo-tolerant search engine optimized for **instant (sub-50ms) search-as-you-type experiences** [citation:15]. It is positioned as an open-source alternative to Algolia with key quirks solved, and an easier-to-use alternative to Elasticsearch [citation:15]. It does not crawl data—you push your own data into it and allow your users to search through it [citation:15].  
**Best for:** Developers wanting an Algolia-like instant search experience with self-hosted control and simpler operations than Elasticsearch.

### sist2
**Stack:** C / Elasticsearch or SQLite | **License:** Open Source  
sist2 is a **lightning-fast filesystem indexer and search tool** with low memory usage and multi-threaded performance [citation:17]. It extracts text and metadata from common file types, generates thumbnails, supports OCR via Tesseract, and provides a mobile-friendly web interface [citation:17]. Features include incremental scanning, manual and automatic tagging, recursive scanning inside archives, and a stats page with disk utilization visualization [citation:17]. It can use Elasticsearch or SQLite as the search backend.  
**Best for:** Teams wanting a self-hosted, fast filesystem indexer with metadata extraction, OCR, and a web UI for searching local or network file collections.

### Tamsaek
**Stack:** Rust / Tantivy | **License:** Open Source  
Tamsaek is a local file search engine powered by Tantivy with full-text capabilities, available as both an **MCP server** and a **standalone CLI tool** [citation:25]. Features include phrase/boolean/field-specific queries, regex search at the term level, metadata filtering by file extension and source type, incremental indexing, and **zero external dependencies** (no separate database or search server) [citation:25]. The CLI and MCP server share the same index.  
**Best for:** Developers wanting a lightweight, zero-dependency local file indexer with both CLI and AI agent (MCP) access, particularly for codebases and document collections.

### InfoGrep
**Stack:** Python | **License:** Open Source (PyPI)  
InfoGrep is a local file search tool with **hybrid retrieval** (sparse, dense, knowledge base, and graph modes) and an **MCP server for coding agents** [citation:19]. It builds a **folder/filename metadata graph** on every reindex, materializing it as an Obsidian-compatible vault for browsing folder relationships [citation:19]. The `search_graph` mode matches queries against folder/file names then expands to neighboring folders, so co-located files surface even if their own names didn't match [citation:19]. It also supports knowledge base search over Obsidian vaults with link/backlink expansion [citation:19].  
**Best for:** Developers and researchers wanting hybrid local search with folder metadata graph expansion and MCP integration for AI-assisted workflows.

### dsearch
**Stack:** Go / Bleve | **License:** Open Source  
dsearch is a fast, configurable filesystem search service for Unix-based systems with fuzzy matching, text content extraction, and **EXIF metadata extraction** from images [citation:21]. Features include concurrent multi-worker indexing, real-time file watcher for incremental updates, virtual folder search, and an optional REST API [citation:21]. EXIF search supports filtering by camera make/model, ISO range, focal length, aperture, date range, and GPS bounding box [citation:21].  
**Best for:** Photographers and media teams needing filesystem search with rich image metadata (EXIF) filtering alongside full-text content search.

### Project Indexly
**Stack:** Python / SQLite FTS5 | **License:** MIT  
Project Indexly is a **privacy-first, 100% offline local file search tool** powered by SQLite FTS5 [citation:23]. It indexes files with metadata enrichment, supports smart file-type detection (TXT, MD, CSV, XML, JSON, images), tag management, advanced CSV/JSON analysis, time-series visualization, and export to CSV/Markdown/JSON [citation:23]. It makes zero network calls, ensuring full privacy.  
**Best for:** Researchers, writers, and analysts wanting a fully offline, privacy-preserving local file search with tagging and analysis capabilities.

### drivedex
**Stack:** Python (stdlib only) | **License:** MIT  
drivedex signs in to SharePoint Online, OneDrive, and Google Drive via OAuth (SSO) and keeps a **local, private index** of files for instant search over hundreds of thousands of items [citation:27]. Features include a change log (added/modified/deleted), a single-file HTML browser, and **Office (docx/xlsx/pptx) to Markdown conversion** for feeding documents to LLMs [citation:27]. It uses only Python standard library, makes no external network calls beyond official Microsoft Graph/Google Drive APIs, and stores the index locally with Windows DPAPI encryption for tokens [citation:27].  
**Best for:** Teams using Microsoft 365 or Google Workspace wanting a private, local index of cloud files with Markdown conversion for AI/LLM workflows, without sending data to third parties.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Real-Time Indexing | Metadata/EXIF | MCP/AI Agent | Self-Hosted | Best For |
|----------|---------|-------|-------------------|---------------|--------------|-------------|----------|
| **Druva** | Proprietary | Cloud | ✅ Near real-time | ✅ Extended metadata | ❌ | ❌ | eDiscovery + compliance search |
| **Algolia** | Proprietary | Cloud | ✅ <50ms | (Custom attributes) | ✅ MCP | ❌ | App/website search + agents |
| **Glean** | Proprietary | Cloud | ✅ | (Permissions) | ✅ MCP | ❌ | Permission-aware enterprise search |
| **Coveo** | Proprietary | Cloud | ✅ | (Custom) | ✅ Search Agent | ❌ | Conversational enterprise search |
| **Meilisearch** | MIT | Rust | ✅ <50ms | (Custom) | ✅ MCP | ✅ | Fast app search + AI |
| **Typesense** | GPL-3.0 | C++ | ✅ <50ms | (Custom) | ❌ | ✅ | Algolia alternative |
| **sist2** | Open Source | C | (Incremental) | ✅ Text + EXIF | ❌ | ✅ | Filesystem indexer + OCR |
| **Tamsaek** | Open Source | Rust/Tantivy | (Incremental) | ✅ Extension filter | ✅ MCP | ✅ | Zero-dependency local search |
| **InfoGrep** | Open Source | Python | (Incremental) | ✅ Folder graph | ✅ MCP | ✅ | Hybrid local + folder graph |
| **dsearch** | Open Source | Go/Bleve | ✅ File watcher | ✅ EXIF rich | ❌ | ✅ | Photo/EXIF search |
| **Project Indexly** | MIT | Python/SQLite | (Optional) | ✅ Rich extraction | ❌ | ✅ | 100% offline privacy search |
| **drivedex** | MIT | Python | (Sync) | ✅ Office metadata | (Markdown for LLM) | ✅ | Cloud files → local index |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Real-Time File or Metadata Search tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between **general-purpose search engines** (Meilisearch, Typesense) for application and website search, **filesystem indexers with metadata extraction** (sist2, dsearch, Project Indexly) for local file collections, and **AI-agent-ready local search** (Tamsaek, InfoGrep, drivedex). **Meilisearch** is the strongest choice for developers wanting fast, modern search with AI-ready features and MCP support . **sist2** offers the most comprehensive filesystem indexing with OCR and thumbnails [citation:17], while **drivedex** uniquely indexes cloud files (SharePoint, OneDrive, Google Drive) locally with Markdown conversion for LLM workflows [citation:27]. Commercial platforms like Druva and Glean remain differentiated by permission-aware enterprise search and compliance-grade eDiscovery that open-source tools cannot replicate.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
