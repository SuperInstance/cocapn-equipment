# Cocapn Equipment Library

Build agents on your own terms. This is a collection of standalone modules that handle common infrastructure concerns, extracted from the vessels running in the Cocapn Fleet. Use one piece or use them all.

---

## Why this exists

Agent frameworks often bundle everything together. This library is the opposite: independent, composable units for key management, memory, and trust. It’s the same code used in production, but you control what you deploy.

---

## What’s inside

*   **Zero Dependencies.** Each module is self-contained and runs on standard Cloudflare Workers. No `node_modules` surprises.
*   **Fork First.** The code is yours. Deploy it, modify it—no upstream updates will break your running agents.
*   **Explicit Behavior.** No hidden magic or background processes. Code only runs when you call it.
*   **Granular Imports.** Import a single module without pulling in the rest of the library.

**One Limitation:** These modules are built for the Cloudflare Workers runtime and its ecosystem (like KV for persistence). They are not generic Node.js packages.

---

## Try It Live

Test endpoints and explore module documentation directly:
[https://cocapn-equipment.casey-digennaro.workers.dev](https://cocapn-equipment.casey-digennaro.workers.dev)

---

## Quick Start

1.  Fork this repository.
2.  Deploy any module to Cloudflare Workers (compatible with the free tier).
3.  Import the specific functions you need into your agent code.

---

## Modules

*   **BYOK v2** – Route requests across multiple LLM providers. API keys are stored as environment variables and never exposed in code or network traffic.
*   **Trust System** – Reputation scoring based on event history. Gate actions or throttle interactions between agents.
*   **Crystal Graph** – A cache for common model responses to help reduce redundant LLM calls.
*   **Dead Reckoning** – A pattern for generating many low-cost outlines and selectively expanding only the best ones.
*   **PII Handling** – Utilities to detect and manage personal data before it is sent to external APIs.
*   **Keeper Memory** – A three-tier memory system (hot, warm, cold) that summarizes older entries instead of deleting them.
*   **Bootcamp Training** – A set of standard routines to initialize a new agent's capabilities.

---

## Configuration Example: BYOK

Set API keys in your Cloudflare Worker environment:

```bash
DEEPSEEK_API_KEY="your_key_here"
DEEPINFRA_API_KEY="your_key_here"
```

---

## Contributing

We follow a fork-first workflow. Test changes in your own deployment, then submit a pull request. All modules must remain standalone with zero cross-dependencies.

---

## License

MIT License.

Superinstance & Lucineer (DiGennaro et al.)

---

<div>
<a href="https://the-fleet.casey-digennaro.workers.dev">⚓ The Fleet</a> · <a href="https://cocapn.ai">Cocapn</a>
</div>