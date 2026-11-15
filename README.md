## Senior software engineer: back-end, data and applied AI systems

I design and build services where correctness and performance matter: network servers, data-intensive back ends on PostgreSQL, and LLM and retrieval systems that are evaluated rather than assumed. I verify behaviour against reference implementations and public benchmarks, find the real cause when the numbers disagree with the design, and record decisions so teams can review and maintain them.

**Portfolio:** [daen8584-spec.github.io](https://daen8584-spec.github.io)

<!-- Add when ready:
**Contact:** [Email](mailto:YOU@EXAMPLE.COM) · [LinkedIn](https://www.linkedin.com/in/YOUR-PROFILE)
-->

### Selected work

| Project | What it is | Evidence |
| --- | --- | --- |
| [**kvstore**](https://github.com/daen8584-spec/kvstore) | Redis-compatible in-memory server in C++20: event loop, persistence with crash recovery, transactions with optimistic locking | 0.86 to 1.18× Redis throughput on the same machine; 71 protocol and command tests pass against both kvstore and Redis 7.0; sanitizers and fuzzing in CI |
| [**hybrid-search**](https://github.com/daen8584-spec/hybrid-search) | Retrieval service for RAG in Python: BM25 and vector search in PostgreSQL, fused by rank, with a query embedding cache shared across processes | 0.719 nDCG@10 on BEIR SciFact, above both retrievers alone; 18 ms median retrieval; 36% fewer embedding calls with the shared cache |
| [**docextract**](https://github.com/daen8584-spec/docextract) | Document extraction in TypeScript: schema-validated LLM output, OCR of scanned PDFs, a transactional job queue and human review | 100% field accuracy on a 20-case evaluation set with 0 hallucinated values; 0.4 to 0.5% OCR character error rate on rendered scans |

### Investigations worth reading

- **[A 42 ns lookup that cost 15% of throughput](https://github.com/daen8584-spec/kvstore/blob/main/docs/adr/0009-transactions.md):** a first fix that changed nothing, then a measurement inside the running server that pointed at CPU cache misses.
- **[OCR that dropped the invoice total](https://github.com/daen8584-spec/docextract/blob/main/docs/adr/0008-ocr-for-scanned-pdfs.md):** Tesseract's default layout analysis lost a `TOTAL DUE` line; the error rate fell from 2% to 0.5% once the cause was found.
- **[Keyword search that made hybrid search worse](https://github.com/daen8584-spec/hybrid-search/blob/main/docs/adr/0007-bm25-in-postgresql.md):** BM25 in SQL took keyword nDCG@10 from 0.399 to 0.688 and latency from 374 ms to 22 ms.

### Capabilities

- **System design:** the simplest architecture that meets the requirements, with trade-offs written down in architecture decision records (26 across these projects)
- **Performance engineering:** reproducible benchmarks, separating noise from effect, and fixing causes down to CPU cache behaviour
- **Reliability:** crash recovery, transactional job queues, safe retries, all-or-nothing persistence and backpressure
- **Applied AI:** LLM integration with validated output, RAG and hybrid retrieval, reranking, evaluation harnesses that gate changes, OCR
- **Verification:** tests against real dependencies and reference implementations, sanitizers, fuzzing, strict typing, CI
- **Technical leadership:** clear specifications, reviewable changes, scoped issues for contributors, and AI coding agents directed and reviewed end to end

### Tools

- **Languages:** TypeScript, JavaScript, Python, C++, SQL, Bash
- **Back end:** Node.js, Next.js, React, FastAPI, REST APIs, authentication and authorization, job queues
- **Data:** PostgreSQL, pgvector, Redis, caching
- **Delivery:** Docker, Docker Compose, GitHub Actions, Linux

Spanish (native) · English (advanced)
