# Cocapn Equipment Library

You build an agent by assembling the parts you need, not by gluing together opaque packages. This is a shared library of components used within the Cocapn Fleet. Each module solves a common, infrastructural problem that every agent runtime eventually faces.

**Live Instance:** https://cocapn-equipment.casey-digennaro.workers.dev

---

## What's Here
- **Zero Dependencies:** The library has no external npm packages. What you deploy is what runs.
- **Fork-First:** You maintain your own copy. Updates are pulled voluntarily, not pushed.
- **Cloudflare Workers Native:** Built for and tested on the Workers runtime. No adapters.
- **Production-Proven:** Each module has been used in live systems and refined through failure.

**One Limitation:** This is built specifically for Cloudflare's JS runtime. It won't run directly in Node.js without modification.

---

## Modules
Import only what you need. Each module is a standalone set of functions.

| Module | Purpose |
|---|---|
| **BYOK v2** | Routes requests across multiple LLM providers using API keys stored only as environment variables. Includes failover. |
| **Trust System** | A scoring mechanism for agents that decays over time and gates access to sensitive capabilities. |
| **Crystal Graph** | A cache for expensive model responses (reasoning chains, conclusions) to avoid redundant computation. |
| **Dead Reckoning** | A pattern to run a costly reasoning step once, then use cheaper, faster models for subsequent similar tasks. |
| **Keeper Memory** | Tiered storage (hot/warm/cold) for agent memory with a policy for intentional forgetting. |
| **PII Dehydrate** | Removes personally identifiable information from text before processing, with a method for safe rehydration. |
| **Boot Camp** | A structure for gradually granting an agent new capabilities based on demonstrated performance. |

---

## Quick Start
1.  **Fork** this repository.
2.  **Deploy** it to Cloudflare Workers.
3.  Copy the specific module files you need into your own agent project.

You can test all modules interactively at the live URL.

---

## Configuration
API keys are managed exclusively through Cloudflare Worker environment variables. They are never embedded in code or logs.

Example environment variables:
```
DEEPSEEK_API_KEY="your_key"
ANTHROPIC_API_KEY="your_key"
OPENROUTER_API_KEY="your_key"
```

---

## Contributing
The fork-first model means you own your deployment. If you build a robust, zero-dependency module compatible with Workers, contributions are welcome via pull request.

---

## License
MIT License.

Superinstance & Lucineer (DiGennaro et al.).

---

<div>
<a href="https://the-fleet.casey-digennaro.workers.dev">The Fleet</a> · <a href="https://cocapn.ai">Cocapn</a>
</div>