# RRBR — rrbr-agents

> **Agentic Layer**: LangGraph multi-agent system for Brazilian market risk analysis.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

## Overview

AI agent orchestration layer for the RRBR system. Connects the quantitative engine to human operators via intelligent agents capable of explaining risk metrics, detecting anomalies, and generating regulatory reports — all in Portuguese.

## Stack

- **Python 3.12+** + **LangGraph 0.3+** — agent orchestration
- **xAI Grok** (default) via pluggable `LLMProvider` interface — swappable to Anthropic, OpenAI, Ollama
- **LangSmith + LangFuse** — full observability, tracing, audit log
- **PostgreSQL/PGVector** — agent state checkpointing and RAG (BCB regulations, ANBIMA manuals)

## Agent Architecture

```
SupervisorAgent
├── RiskAnalysisAgent    → calls rrbr-quant-engine via gRPC
├── ExplainAgent         → generates Portuguese explanations via LLM
├── RegulatoryAgent      → FRTB-SA compliance checks
└── HumanApprovalGate    → mandatory for all critical actions
```

## LLM Provider Configuration

```bash
RRBR_LLM_PROVIDER=xai       # default
RRBR_LLM_PROVIDER=anthropic
RRBR_LLM_PROVIDER=openai
RRBR_LLM_PROVIDER=ollama
```

## Related Repositories

| Repository | Description |
|------------|-------------|
| [rrbr-quant-engine](https://github.com/Risk-Reference-BR/rrbr-quant-engine) | Rust quantitative core |
| [rrbr-data](https://github.com/Risk-Reference-BR/rrbr-data) | Data streaming layer |
| [rrbr-api](https://github.com/Risk-Reference-BR/rrbr-api) | API Gateway |

## License

Apache 2.0
