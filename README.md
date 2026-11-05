## Software engineer: back-end systems, AI applications and systems programming

I build software that is measured, tested and documented. Each project below reports results from a standard benchmark or a reference implementation, runs its full test suite in CI, and records its design decisions in architecture decision records.

### Projects

| Project | What it is | Highlights |
| --- | --- | --- |
| [**kvstore**](https://github.com/daen8584-spec/kvstore) | Redis-compatible in-memory key-value server in C++20 | Single-threaded epoll event loop, incremental rehashing, append-only file persistence with fork-based compaction. Integration tests pass against both kvstore and Redis; throughput is close to Redis on the same machine. Tested under sanitizers and continuous fuzzing |
| [**hybrid-search**](https://github.com/daen8584-spec/hybrid-search) | Hybrid keyword and vector retrieval service in Python on PostgreSQL and pgvector | BM25 over an inverted index in SQL, HNSW vector search and Reciprocal Rank Fusion, evaluated on the BEIR SciFact benchmark. Hybrid search outperforms both retrievers on their own, with millisecond-level latency |
| [**docextract**](https://github.com/daen8584-spec/docextract) | Document extraction service in TypeScript with LLM output validation and human review | Next.js, PostgreSQL job queue with retries and crash recovery, schema-validated model output, audit log, role-based access, and an evaluation harness that measures extraction accuracy |

### What I work with

- **Languages:** C++, Python, TypeScript, JavaScript, SQL
- **Back end:** PostgreSQL, Redis, FastAPI, Next.js, REST APIs, job queues, authentication and authorization
- **AI applications:** retrieval and RAG, embeddings, vector search, LLM integration and evaluation
- **Systems:** network servers, concurrency, persistence and crash recovery, performance measurement
- **Quality:** unit and integration tests, sanitizers, fuzzing, strict type checking, CI on GitHub Actions

### How I work

- I check behaviour against a reference rather than assuming it: kvstore's tests run against real Redis, and hybrid-search is scored on a public benchmark with expert relevance judgements.
- I measure before claiming. When a first measurement shows a weakness, the fix and the before and after numbers go into the project's documentation.
- I write down significant design decisions and their trade-offs, so reviewers can evaluate them against their assumptions.
