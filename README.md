# AI AIO Stack

The all-in-one AI stack providing automation, chat interface, and web serving capabilities.

## Features

- 🚀 **n8n**: Powerful workflow automation tool
- 💬 **Open WebUI**: Web interface for AI interactions
- 🔍 **SearXNG**: Privacy-focused metasearch engine
- 🛡️ **Caddy**: Modern web server with automatic HTTPS
- 🐘 **PostgreSQL**: Database for n8n
- 📝 **Tika**: Document processing engine

## Prerequisites

- Docker
- Docker Compose

## Quick Start

1. Clone this repository
2. Uncomment services that you want to run.
3. Update environment variables in `docker-compose.yml`:
   - All passwords (marked as "change-me")
   - Encryption keys
   - Webhook URLs
4. Update configuration in `Caddyfile`
   - All domains (marked as "change-me.com")
5. Run:

```bash
docker compose up -d
```

5. Open the app:
   - Open WebUI: http://localhost:8080
   - n8n: http://localhost:5678
   - SearXNG: http://localhost:9000

### Services Info

| Service    | Host Port | Container Port | Description                       |
| ---------- | --------- | -------------- | --------------------------------- |
| Open WebUI | 8080      | 8080           | Web interface for AI interactions |
| n8n        | 5678      | 5678           | Webhook server for n8n            |
| Caddy      | 80,443    | 80,443         | Web server with automatic HTTPS   |
| PostgreSQL | 5432      | 5432           | Database for n8n                  |
| SearXNG    | 9000      | 8080           | Privacy-focused metasearch engine |
| Tika       | 9998      | 9998           | Document processing engine        |

### Integrations

#### Open WebUI with SearXNG for Web Search

1. Open the Open WebUI
2. Go to Admin Panel
3. Go to Settings
4. Go to Web Search
5. Enable the "Web Search" toggle
6. Set the "Web Search Engine" to "SearXNG"
7. Set the "Web Search URL" to `http://searxng:8080/search?q=<query>&format=json`

   a. Replace "searxng" with the hostname of your SearXNG instance

   b. Replace "8080" with the container port of your SearXNG instance

8. Save the settings
9. Open a new chat
10. Toggle the "Web Search" toggle and submit the chat

#### Open WebUI with Tika for Document Processing

1. Open the Open WebUI
2. Go to Admin Panel
3. Go to Settings
4. Go to Documents
5. Set the "Content Extraction Engine" to Tika
6. Set the Tika URL to `http://tika:9998`

   a. Replace "tika" with the hostname of your Tika instance

   b. Replace "9998" with the container port of your Tika instance

7. Save the settings
8. Open a new chat
9. Upload a document (PDF, DOCX, etc.)
10. Chat with the document
