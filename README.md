# Veo3 Video Generator (n8n)

Automated short-form video generation workflow that turns a simple concept into a fully rendered AI video, then logs a downloadable link to Google Sheets for quick posting.

## What it does

1. **Idea Agent** generates a video concept (characters, setting, action).
2. **Prompt Agent** converts the concept into a detailed Veo3-ready prompt.
3. The workflow sends the prompt to **Veo3 via Vertex AI**.
4. The generated video is fetched and a **downloadable link** is saved to a Google Sheet.

## Why it matters

Creating consistent social media video content is time-consuming. This automation reduces the process to a single run, producing ready-to-post video outputs with tracking in a spreadsheet.

## Features

- AI-generated concepts (characters / setting / action)
- Prompt expansion into detailed video instructions
- Automated request to Veo3 (Vertex AI)
- Fetches the rendered video output
- Logs video link + metadata into Google Sheets
- Optional scheduling via n8n trigger

## Example Output

The Google Sheet can store columns like:
- createdAt
- idea
- finalPrompt
- model
- videoUrl (download link)
- status / notes

> Tip: Use placeholder/fake data for screenshots in a public repo.

## Setup (high level)

### Prerequisites
- n8n (cloud or self-hosted)
- Google Sheet for outputs
- Google Cloud project with Vertex AI access (Veo3)
- Credentials configured in n8n (Google + Vertex)

### Configure placeholders
Before running, replace placeholders in the workflow:
- `<GCP_PROJECT_ID>`
- `<GOOGLE_SHEET_ID>`
- `<GOOGLE_SHEET_URL>` (optional)
- `<ACCESS_TOKEN>` *(recommended: use a proper auth method instead of pasting tokens)*

### Recommended auth approach
For production use, authenticate Vertex AI using:
- **Service Account credentials** (preferred for server workflows), or
- **OAuth** (if you require user-based access)

Avoid hardcoding access tokens directly in nodes.

## How to use

1. Import `veo3-video-generator-n8n.github-ready.json` into n8n.
2. Connect your credentials (Google + Vertex).
3. Set your output Google Sheet.
4. Run the workflow (or enable the schedule trigger).
5. Check the sheet for the video link and details.

## Technologies

- n8n
- Vertex AI (Veo3)
- Google Sheets
- LLM agents (idea + prompt generation)
- HTTP requests

## Notes / Safety

This repo contains **no live keys**. Add your own credentials in n8n.
Do not upload real client data, API keys, or private sheet URLs to public repos.

## License

MIT (optional) — or leave unlicensed if you prefer.
