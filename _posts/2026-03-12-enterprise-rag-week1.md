---
title: "Building an Enterprise RAG System: Week 1"
date: 2026-03-12
categories: [AI]
tags: [RAG, AI, engineering, production]
image:
  path: /assets/img/posts/rag-week1-architecture.png
  alt: RAG System Architecture
---

One pattern keeps showing up in real AI deployments: the hardest part usually isn't the model. It's the system around it.

As a Solutions Architect working with teams adopting AI, I often help organizations move from prototypes to real systems. And there's a clear gap between a polished prototype and a system that's safe, reliable, and production-ready.

Evaluation, retrieval quality, safety, observability — these are usually where real deployments get hard.

So I decided to go deeper on the engineering side. Over the next 10 weeks, I'm building a production-oriented enterprise RAG system from scratch, documenting the engineering tradeoffs along the way.

## Week 1: Basic RAG Pipeline

Built a basic RAG pipeline: **PDF ingestion → embeddings → retrieval → context → LLM answers with citations.**

![RAG System Architecture](/assets/img/posts/rag-week1-architecture.png)
_Week 1 architecture: a minimal but functional RAG pipeline_

### Chunking Strategy

One key design decision this week was chunking: **800 characters with 150 overlap**.

- Smaller chunks improve retrieval precision but fragment context
- Overlap restores continuity but increases redundancy
- 150/800 (~19%) feels like a reasonable starting point

The real answer should come from evaluation, not intuition — which is exactly what the next few weeks will focus on.

## The Next 9 Weeks

- Retrieval evaluation
- Multi-source ingestion
- Hybrid search and reranking
- Managed storage and tenant-aware architecture
- AI safety guardrails
- Observability and monitoring
- Production deployment and system hardening

---

The full repo is [here](https://github.com/yiju6/enterprise-rag). For those who've taken AI systems from demo to production — where did you hit the hardest engineering walls?
