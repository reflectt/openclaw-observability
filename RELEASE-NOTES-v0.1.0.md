# OpenClaw Observability Toolkit v0.1.0

**Release Date:** February 4, 2026

## 🎉 Initial Release

The first public release of the OpenClaw Observability Toolkit - framework-agnostic visual debugging for AI agents.

### 🚀 What's Included

**Core Tracing SDK:**
- ✅ Universal `@observe` decorator for any Python function
- ✅ Context manager API (`with trace()`)
- ✅ LLM call tracking (model, tokens, cost, latency)
- ✅ Error capture with full stack traces
- ✅ JSON-based storage (local-first, no cloud required)

**Framework Integrations:**
- ✅ **LangChain:** Drop-in callback handler for automatic tracing
- ✅ **OpenClaw:** Native integration for OpenClaw agents
- 🚧 CrewAI and AutoGen (coming in v0.2.0)

**Web Visualization UI:**
- ✅ Real-time dashboard with trace metrics
- ✅ Interactive execution graph visualization
- ✅ Step-level inspection (click any node to see details)
- ✅ LLM call viewer (prompts, responses, tokens, cost)
- ✅ Error highlighting and debugging

**Documentation:**
- ✅ Comprehensive README with examples
- ✅ Quick Start guide (5-minute setup)
- ✅ API documentation
- ✅ Working examples (basic + LangChain)

### 🎯 Key Features

**Framework-Agnostic:** Unlike LangGraph Studio (LangGraph-only) or LangSmith (LangChain-focused), this toolkit works with ANY Python-based agent framework.

**Visual Debugging:** See your agent's execution flow as an interactive graph. Click any step to inspect inputs, outputs, LLM calls, and errors.

**Local-First:** All traces stored locally on your machine. No cloud dependencies, no API keys, no vendor lock-in.

**Production-Ready:** Low overhead (<1% latency), async data collection, and configurable retention.

### 📊 Use Cases

1. **Debug multi-agent systems** - See which agent failed and why
2. **Optimize performance** - Identify slow steps and bottlenecks
3. **Track LLM costs** - See token usage and costs per operation
4. **Root cause analysis** - Inspect full error traces with context

### 🔧 Quick Start

```bash
# Install
pip install openclaw-observability

# Decorate your functions
from openclaw_observability import observe, init_tracer
from openclaw_observability.span import SpanType

tracer = init_tracer(agent_id="my-agent")

@observe(span_type=SpanType.AGENT_DECISION)
def my_agent_function(input):
    # Your code here
    return result

# Start web UI
python -m openclaw_observability.server

# View at http://localhost:5000
```

### 🐛 Known Issues

- Server requires manual start (no CLI entry point yet)
- No real-time streaming of traces (5-second polling)
- Limited filtering/search in UI
- No production monitoring features yet

### 🗺️ Roadmap

**v0.2.0 (4 weeks):**
- CrewAI and AutoGen integrations
- Real-time trace streaming (WebSocket)
- Advanced filtering and search
- Trace comparison tool

**v0.3.0 (8 weeks):**
- Production monitoring dashboard
- Cost alerts and budgets
- Quality metrics (accuracy, latency)
- Anomaly detection

**v1.0.0 (12 weeks):**
- Self-hosted deployment (Docker, K8s)
- Multi-tenancy and RBAC
- PII redaction
- Enterprise features

### 📦 Installation

```bash
pip install openclaw-observability
```

Or from source:

```bash
git clone https://github.com/reflectt/openclaw-observability.git
cd openclaw-observability
pip install -e .
```

### 🤝 Contributing

We welcome contributions! Priority areas:
- Framework integrations (CrewAI, AutoGen, etc.)
- UI improvements (filtering, search, real-time updates)
- Performance optimizations
- Documentation and examples

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### 📄 License

Apache 2.0 - See [LICENSE](LICENSE) for details.

### 🙏 Acknowledgments

Inspired by:
- **LangGraph Studio** - Best-in-class visual debugging
- **LangSmith** - Production observability for LLMs
- **OpenTelemetry** - Distributed tracing standards

Built by the [OpenClaw](https://openclaw.ai) team and [Reflectt](https://reflectt.ai).

---

**Questions or feedback?** Open an issue or join our [Discord](https://discord.gg/openclaw)

**Star the repo** if you find this useful! ⭐
