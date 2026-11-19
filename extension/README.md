# First Principles Studio: browser extension

The same studio as `app/`, packaged as a Chrome or Edge extension. Click the toolbar icon to open it in a new tab.

## Install (unpacked, for now)

1. Open `chrome://extensions` (or `edge://extensions`).
2. Turn on **Developer mode**.
3. Click **Load unpacked** and choose this `extension/` folder.

## Use it with Ollama

Ollama only answers pages it trusts. Extensions use a `chrome-extension://` origin, so allow it:

- Windows: `setx OLLAMA_ORIGINS "chrome-extension://*"`, then quit Ollama from the tray and start it again.
- Mac/Linux: `export OLLAMA_ORIGINS="chrome-extension://*"`, then run `ollama serve`.

Open the studio, go to **Settings**, pick the Ollama brain, and test the connection.

## Permissions

The extension asks only for access to `localhost:11434` (Ollama), `api.anthropic.com` (Claude, if you use your own key) and `generativelanguage.googleapis.com` (Gemini, if you use your own key). Nothing else is requested.

## Notes

- Voice input uses the browser's speech recognition, which in Chrome is an online service.
- To use an Ollama server on another machine, add its address to `host_permissions` in `manifest.json`.
