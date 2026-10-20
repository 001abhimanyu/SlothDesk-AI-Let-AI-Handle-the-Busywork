# SlothDesk AI

**Less busywork. More breathing room.**

SlothDesk AI is a local-first productivity helper built for the Hacktoberfest Open-Source AI Challenge theme **Slow and Steady**. It helps users organize a messy task list, summarize notes, create a low-energy plan, and break intimidating work into smaller steps.

## Why open-source AI?

SlothDesk is designed to use [Ollama](https://ollama.com/) with an open-weight model such as `llama3.2`. When connected to Ollama, prompts are sent to the local model running on the user's computer instead of a hosted proprietary AI API. This means:
- No paid AI API key is required.
- Personal notes can stay on the user's own machine.
- Users can swap models and change the assistant's prompts.
- The UI remains useful as a simple demo even when local AI is not connected.

**Honest limitation:** the browser UI's fallback is basic JavaScript, not an AI model. Real AI features require Ollama and a downloaded model. Model licensing varies; check the selected model's license and terms.

## Features

- Lazy Task Organizer
- Note Summarizer
- Low-Energy Mode
- Make It Simpler
- Ollama local model connection
- Responsive, single-page interface
- No frontend framework or API key

## Run the website

1. Download or clone this repository.
2. Open `index.html` in a browser to explore the interface and demo mode.
3. For local AI, install Ollama from <https://ollama.com/>.
4. In a terminal, download a model:

   ```bash
   ollama pull llama3.2
   ```

5. Make sure Ollama is running. Its local API normally listens at `http://localhost:11434`.
6. Browser security may block requests from a local HTML file due to CORS. If so, set `OLLAMA_ORIGINS` to allow the page's origin and restart Ollama. For a quick local development server, run Python from the project folder:

   ```bash
   python -m http.server 8000
   ```

   Then visit <http://localhost:8000>. Configure Ollama's `OLLAMA_ORIGINS` to allow `http://localhost:8000` before refreshing. Refer to Ollama's current documentation for OS-specific environment-variable steps: <https://github.com/ollama/ollama/blob/main/docs/faq.md>.

7. In SlothDesk AI, keep the model field set to `llama3.2` (or enter the exact model name you pulled) and click **Make it easier**.

## Privacy

The app sends the entered text to the local Ollama endpoint only when you press the action button. It does not intentionally send prompts to a remote service. Avoid entering sensitive data if you are unsure how your computer or local model is configured.

## Tech stack

- HTML
- CSS
- Vanilla JavaScript
- Ollama local HTTP API
- Open-weight model (example: Llama 3.2; check its license and terms)

## Challenge fit: Slow and Steady

SlothDesk rewards doing less repetitive work: it reduces a large task dump into a short plan, turns long notes into action items, and suggests a tiny first step. Open innovation matters because local inference offers more control over privacy, model choice, and behavior without a paid hosted AI API.

## Ideas for contributors

- Add export to Markdown or text
- Add saved task templates stored locally
- Add model selector populated from Ollama's local API
- Add optional due dates and effort estimates
- Improve accessibility and keyboard navigation
- Add tests for prompt construction and fallback mode

## License

MIT. See `LICENSE`.
