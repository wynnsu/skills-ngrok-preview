# 🌐 Ngrok Preview Skill

A high-utility skill for AI agents to share local artifacts (HTML, images, web apps) with users via temporary, secure public URLs.

This skill is specifically designed to bridge the gap between a local development environment and a mobile-first user experience (like Telegram or mobile browsers), where `localhost` links are inaccessible.

## 🚀 Why use this?

- **Mobile-Friendly Workflows**: Perfect for previewing agent-generated web content on your phone while the agent runs locally.
- **OpenClaw Integration**: Works seamlessly with the OpenClaw local gateway. Instead of walls of text or local file paths, the agent sends a clickable ngrok link directly to chat.
- **Zero-Config Sharing**: Handles creation and cleanup of short-lived tunnels for local artifacts.

## 🛠 Installation

Install via the skills.sh ecosystem:

```bash
npx skills add https://github.com/wynnsu/skills-ngrok-preview --skill ngrok-preview
```

## ⚙️ Prerequisites

- `ngrok` CLI installed on your local machine.
- ngrok account authenticated:

```bash
ngrok config add-authtoken <your-token>
```

## 📖 How it works

When the agent generates a local file (for example a data visualization, mockup, or report), it can invoke this skill to:

1. Start a local HTTP server in the artifact directory.
2. Tunnel that server through ngrok.
3. Return the public URL to the user via the OpenClaw gateway.

## Skill structure

- `skills/ngrok-preview/SKILL.md`: Metadata and operating guidance.
- `skills/ngrok-preview/scripts/ngrok_preview.py`: Core Python logic for tunnel management.
- `skills/ngrok-preview/references/troubleshooting.md`: Common fixes for auth issues, stale sessions, and tunnel errors.

## 🤝 Compatibility

Optimized for:

- **Gateway**: OpenClaw
- **Ecosystem**: skills.sh
- **Platforms**: Telegram, web-based agent UIs
