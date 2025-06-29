# Expose Ollama to external origins

Want to run LLMs locally with @ollama but need to access it from non-local origins?

Here’s a quick guide to configure Ollama for cross-origin access.
🧵 ⬇️

## 1. Set the OLLAMA_HOST:

By default, Ollama binds to `127.0.0.1:11434`. To make it accessible externally, set the `OLLAMA_HOST` to `0.0.0.0`.

- On macOS: `launchctl setenv OLLAMA_HOST "0.0.0.0"`
- On Linux (systemd): Edit the service with `sudo systemctl edit ollama.service`, add `Environment="OLLAMA_HOST=0.0.0.0"` under `[Service]`.
- On Windows: Go to System Environment Variables, add `OLLAMA_HOST` as `0.0.0.0`.

## 2. Allow Cross-Origin Requests: Ollama restricts origins to `127.0.0.1` and `0.0.0.0` by default. To allow non-local origins, set `OLLAMA_ORIGINS`.

- For all origins (be cautious!): `OLLAMA_ORIGINS="*"`.
- For specific origins: `OLLAMA_ORIGINS="https://example.com"`.
- Use the same method as above to set this env variable based on your OS.

## 3. Restart Ollama: Apply changes by restarting.

- macOS: Restart the app.
- Linux: `sudo systemctl daemon-reload && sudo systemctl restart ollama`.
- Windows: Restart via the taskbar or Start menu.

## 4. Firewall Check

Ensure port 11434 is open on your firewall to allow external access.

## 5. Security Tip

Exposing Ollama to `0.0.0.0` makes it accessible on your network.

Avoid public networks, and consider using a proxy like Nginx for added security.

Now you can access your local LLM from other devices! 🎉
