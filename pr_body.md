**Feature:** Dynamic LLM Provider Support

This PR introduces comprehensive support for managing and switching between multiple LLM providers, with a specific focus on **Local LLMs** (Ollama, LM Studio).

### Key Features
*   **Multiple Provider Support:** easily toggle between OpenAI, Anthropic, and local endpoints via the Settings page.
*   **Local LLM First-Class Support:**
    *   **Ollama:** Auto-detects models via `/api/tags`.
    *   **LM Studio:** Supports `/api/v0/models` and relaxed API key requirements.
    *   **Smart Testing:** Automatically fixes common configuration errors (like pasting full `/chat/completions` URLs) and handles missing API keys for local tools.
*   **Dynamic Configuration:** The backend now dynamically loads credentials based on the active provider, replacing static `.env` dependencies.

### Improvements
*   Resolves `InvalidResponseError` crashes caused by malformed user URLs.
*   Enables use of embedding models without strict API key enforcement when running locally.
*   Updates Dashboard System Status to correctly reflect local model health.
