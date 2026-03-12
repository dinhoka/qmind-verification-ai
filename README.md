# Q-MIND

**The verification layer for artificial intelligence.**

Deterministic symbolic reasoning engine that **computes, proves, and verifies mathematical reasoning with zero hallucination.**

---

## What Q-MIND Does

Q-MIND is a **neuro-symbolic scientific reasoning platform** with:

- **35+ modules** across 20 domains
- **1,253 tests** passing
- **19 API endpoints** (REST + conversational)
- **LGPD-compliant** privacy and data protection
- **Bilingual** interface (PT/EN)

```
LLM generates reasoning  ->  Q-MIND verifies correctness
```

---

## Quick Start

```bash
# Install
cd packages/engine
pip install -e ".[dev]"

# Run tests (1,253 tests)
pytest tests/ -v

# Start API server
uvicorn qmind.api.main:app --reload
# -> http://localhost:8000/docs

# Run demo
python examples/demo_queries.py
```

---

## Capabilities

### Symbolic Computation
| Feature | Example | Result |
|---------|---------|--------|
| Equations | `x^2 - 5x + 6 = 0` | `x = 2, 3` (VERIFIED) |
| Derivatives | `derivada de x^3 + 2x` | `3x^2 + 2` |
| Integrals | `integral of sin(x)` | `-cos(x) + C` |
| Factoring | `Factor 1234567890` | `2 x 3^2 x 5 x 3607 x 3803` |
| Simplification | `(x^2-1)/(x-1)` | `x + 1` |
| Proofs | `Prove que x^2 >= 0` | Formal proof with steps |
| Knowledge | `O que e Pitagoras?` | Theorems + identities |

### Scientific Domains
- **Physics** -- kinematics, dynamics, waves, thermodynamics, optics, relativity
- **Chemistry** -- molar mass, pH, stoichiometry, electron config
- **Finance** -- NPV, IRR, Black-Scholes, CAPM, bonds
- **Engineering** -- circuits, signals, control systems, impedance
- **Cryptography** -- Bitcoin pipeline, secp256k1, SHA256, Base58/Bech32

### AI Integration
- OpenAI / Anthropic tool specifications
- LangChain tools (5 tools)
- CrewAI / AutoGen agent integration
- LLM output verification pipeline

---

## API Endpoints

### Core
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/solve` | Solve math/logic problem |
| POST | `/analyze` | Full analysis: solve + prove + evaluate + report |
| POST | `/prove` | Prove or disprove a statement |
| POST | `/verify` | Verify expression correctness |
| POST | `/simplify` | Simplify expression |
| POST | `/factor` | Factor expression or number |
| POST | `/check` | Quick true/false check |
| POST | `/chat` | Conversational interface (intent detection + context) |
| POST | `/report/latex` | Generate LaTeX report |

### Knowledge Graph
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/knowledge/query` | Search semantic knowledge graph |
| GET | `/knowledge/stats` | Knowledge graph statistics |
| GET | `/knowledge/export` | Export full KG as JSON |

### Privacy (LGPD)
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/privacy/policy` | Privacy policy (PT/EN) |
| POST | `/privacy/consent` | Record/revoke consent |
| GET | `/privacy/data/{id}` | Export session data (portability) |
| DELETE | `/privacy/data/{id}` | Delete session data (erasure) |

### Infrastructure
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/health` | Health check |
| GET | `/metrics` | API metrics |
| GET | `/graph/visualize` | Pipeline graph (Mermaid/Graphviz) |

---

## Architecture

```
User Input
    |
Cognitive Layer (extract, classify, route)
    |
Intent Analyzer (16 intent types)
    |
Strategy Engine (cost-aware, multi-path)
    |
Symbolic Engines (SymPy + Z3)
    |
Verification Layer (proofs + counterexamples)
    |
Knowledge Graph (4,000+ entities)
    |
Explanation Generator (bilingual PT/EN)
```

### Modules

| Module | Path | Purpose |
|--------|------|---------|
| Core | `qmind/core/` | QNode AST, LaTeX parser, NLP parser, serializer |
| Engines | `qmind/engines/` | MathEngine (SymPy), LogicEngine (Z3), NumberTheory |
| Orchestrator | `qmind/orchestrator/` | Pipeline, DAG, Strategy, Distributed execution |
| Proof | `qmind/proof/` | Prover, verifier, counterexample, Lean4 export |
| Conversation | `qmind/conversation/` | Intent analyzer (16 types), conversational engine |
| Knowledge | `qmind/knowledge/` | Semantic KG, retrieval, 4,000+ entities |
| Cognitive | `qmind/cognitive/` | Math extractor, classifier (25 categories), router |
| Domains | `qmind/domains/` | Physics, chemistry, finance, engineering, crypto |
| Evaluation | `qmind/evaluation/` | Consistency checks, confidence scoring |
| Report | `qmind/report/` | LaTeX, JSON, Markdown reports |
| Explanation | `qmind/explanation/` | Step-by-step bilingual templates |
| API | `qmind/api/` | FastAPI REST, LGPD, billing, metrics |
| Plugins | `qmind/plugins/` | Plugin system, marketplace, sandbox |
| SDKs | `qmind/sdk/` | Python, JavaScript, Rust SDKs |
| Dataset | `qmind/dataset/` | Reasoning graphs, PII anonymization, export |
| LLM | `qmind/llm/` | OpenAI/Anthropic tools, LangChain, benchmarks |

---

## LGPD Compliance

Q-MIND implements Brazilian data protection law (Lei Geral de Protecao de Dados):

- **PII scrubbing** -- email, phone, IP, CPF, CNPJ auto-removed from logs
- **Consent management** -- record/revoke user consent per session
- **Data portability** -- export all session data as structured JSON
- **Right to erasure** -- delete all session data permanently
- **Session auto-expiry** -- sessions expire after 1 hour of inactivity
- **Security headers** -- X-Frame-Options, X-XSS-Protection, CSP, etc.
- **In-memory storage** -- no data persists after server restart

---

## Project Structure

```
IaQuantica/
  packages/
    engine/          # Python backend (main codebase)
      src/qmind/     # 35+ modules, 155 Python files
      tests/         # 1,253 tests
      pyproject.toml
    web/             # Next.js frontend
  examples/          # Demo queries
  docs/              # Architecture documentation
  CLAUDE.md          # AI assistant guidelines
```

---

## Tech Stack

- **SymPy** -- symbolic mathematics
- **Z3** -- SAT/SMT solving
- **FastAPI** -- REST API
- **Next.js 15** -- web frontend
- **pytest** -- testing (1,253 tests)
- **SQLite** -- knowledge graph persistence

---

## License

Open Core model. Community edition: [MIT License](LICENSE).

| Part | License |
|------|---------|
| Core engine | MIT |
| Advanced plugins | Commercial |
| Cloud infrastructure | Commercial |

---

## Copyright

Copyright (c) 2026 Dinhoka.

Q-MIND is an open core project.
The community edition is licensed under the MIT License.

Commercial features, enterprise integrations and proprietary modules
may be distributed under separate commercial licenses.

Q-MIND™ is a trademark of Dinhoka.

---

*Q-MIND: the verification layer for artificial intelligence.*
*Symbolic reasoning that computes, proves, and explains -- without hallucination.*
