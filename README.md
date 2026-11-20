### Hi, I'm Harshith Patil 👋

**Software Engineer: backend, distributed systems, and low-latency systems.** Boston, MA.

🎓 MS at Northeastern, December 2026. Available full-time from February 2027.

I'm a backend engineer who makes complex data systems reliable. I spent two years at **Gainsight** as the de facto lead on Unification, a master data management platform serving 1,000+ enterprise customers and 60M+ records, then did a fintech co-op at **Hometap** building underwriting and valuation services. Outside work, I build performance-critical systems in Go and C++.

---

### Featured: [Clearline](https://github.com/harshithptl/clearline)

An event-driven trade settlement and double-entry ledger engine: orders come in through a REST API, a C++ engine matches them, and each trade is settled into a Postgres ledger **exactly once**, with live balances and a dashboard.

`Go` `C++20` `Kafka` `PostgreSQL` `Valkey` `gRPC` `Prometheus` `Kubernetes (Helm, kind)` `React + TypeScript`

- **Exactly-once on at-least-once Kafka:** idempotent consumers, offsets committed only after the database commit, and a transactional outbox.
- **Throughput scaled 20x** with batched, per-partition-concurrent processing: 100 → 2,000 trades/s sustained, with p99 order-to-ledger under 150 ms. 2,000 was the highest rate offered, so capacity wasn't reached.
- **Chaos-tested:** killed or restarted every service, the Kafka broker and the cache under live load. Across 14,000 order pairs: 0 lost, 0 double-posted, reconciler clean.
- CI on every PR covers lint, vulnerability scanning, C++ tests, end-to-end tests on Docker Compose and on Kubernetes (kind), browser tests, and unit-tested Prometheus alert rules.

<sub>Benchmarks: Apple M4, 16 GB, whole stack in Docker Desktop with the load generator on the same machine; full durability (Kafka acks=all on a single broker, Postgres synchronous_commit and fsync on, Valkey appendfsync=always). Full report, raw data and reproduce commands in the repo.</sub>

---

### Other projects

- **[LowLatencyBuffer](https://github.com/harshithptl/LowLatencyBuffer):** a lock-free single-producer/single-consumer ring and a price-time priority matching engine in C++. 5.2 µs best-run P50 submit-to-book (5.2 to 8.7 µs across runs, Apple M4) and 1.1 to 1.6 µs per order-book operation, with zero heap allocation on the hot path. It now powers Clearline's matching engine.
- **Options backtesting engine (C++23):** six years of market data in about 3 seconds. Bootstrap and walk-forward validation caught roughly 50% Sharpe ratio inflation from a methodology flaw.
- **RAG document Q&A:** retrieval-augmented generation on a local llama3.2 (Ollama) with Qdrant embeddings, plus evaluation of retrieval and answer quality.

---

### Experience

- **Hometap**, Software Engineering Co-op (Jan to May 2026): Django tooling and REST endpoints for underwriting and home-equity valuation, integrated with Salesforce and DigiFi.
- **Gainsight**, Software Engineer (promoted from Associate), Aug 2022 to Jul 2024: owned Unification end to end. Among other work, I cut a production query from a 30 s timeout to 2 s via execution-plan analysis, and built RabbitMQ event-driven sync between microservices.

### Tech

- **Languages:** Java, Python, Go, C++ (C++20/23), SQL, TypeScript
- **Backend:** Spring Boot, Django, FastAPI, Flask, gRPC, REST
- **Data and messaging:** PostgreSQL, Kafka, RabbitMQ, Valkey/Redis, MongoDB
- **Infrastructure:** Docker, Kubernetes (Helm, kind), AWS, GCP, Terraform, GitHub Actions
- **Observability:** Prometheus, Grafana, Sumo Logic

---

📫 [Portfolio](https://harshithptl.netlify.app) · [LinkedIn](https://www.linkedin.com/in/harshithptl) · [Email](mailto:harshithptl@gmail.com)
