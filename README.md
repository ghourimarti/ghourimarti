# I build production RAG and agentic systems — and every claim below is something you can go verify yourself.

No inflated metrics. Each repo ships with real eval numbers, a CI gate that can fail the build on regression, and an honest line about what's actually deployed versus only validated.

**Zain Ul Abdin** · LLMOps / AI engineer · open to freelance & contract work

---

### Start here

| Repo | What's actually in it |
|---|---|
| [**Anime-Recommendation-Engine**](https://github.com/ghourimarti/Anime-Recommendation-Engine) | Hybrid retrieval — pgvector + full-text search + reciprocal-rank fusion — into a cross-encoder rerank and MMR diversification pass. Tiered LLM gateway with per-provider circuit breakers. A 111-query eval gate wired into CI. |
| [**Product-Recommender-Engine**](https://github.com/ghourimarti/Product-Recommender-Engine) | Qdrant hybrid RAG. The CI gate requires the reranker to beat Google Shopping's own product ordering (0.94 vs 0.82 NDCG@3) — if it stops earning its place, the build goes red, not green. |
| [**Travel-Planner**](https://github.com/ghourimarti/Travel-Planner) | LangGraph multi-agent trip planning with live external tool grounding, streamed to the browser. The only one of these actually installed on a Kubernetes cluster so far — not just validated. |

Every repo: `make check` runs lint, strict type checking, and the full test suite — the same gate CI runs on every PR. Clone it and run it yourself.

**Current honest scope:** Docker builds and runs verified end-to-end on all three. Kubernetes manifests and Terraform are authored and validated (`helm lint`, `terraform validate` / `plan`) — applying them to a live cloud cluster is in progress now. I'd rather you read that here than find it out as a surprise on a call.
