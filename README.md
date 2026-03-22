# Risk Reference BR — rrbr-agents

> **Agentic Layer**: LangGraph multi-agent system for Brazilian market risk analysis.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

## Vision

O Risk Reference BR tem a ambição de ser o centralizador dos agentes de AI para catalogar, implementar e validar todos os produtos financeiros brasileiros com suas métricas de risco e as raras convenções de mercado brasileiras. Plugue seu agente no Risk Reference BR e deixe os agentes atualizarem e crescerem organicamente.

Contribuições abertas a humanos e agentes AI. Idealizado por **Ricardo Pfeuti**.

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
Risk Reference BR_LLM_PROVIDER=xai       # default
Risk Reference BR_LLM_PROVIDER=anthropic
Risk Reference BR_LLM_PROVIDER=openai
Risk Reference BR_LLM_PROVIDER=ollama
```

## Related Repositories

| Repository | Description |
|------------|-------------|
| [rrbr-quant-engine](https://github.com/Risk-Reference-BR/rrbr-quant-engine) | Rust quantitative core |
| [rrbr-data](https://github.com/Risk-Reference-BR/rrbr-data) | Data streaming layer |
| [rrbr-api](https://github.com/Risk-Reference-BR/rrbr-api) | API Gateway |

## License

Apache 2.0
