# Israel Electric Company Request UI

Hebrew UI for submitting requests to the Israel Electric Company. The server accepts the form, uploads the attachment, and calls the webhook with the `Process this Israel Electric Company request` message and the attachment id.

## Requirements

- Node.js 18+ (tested with Node 25)

## Run locally

```bash
npm start
```

Server defaults to `http://localhost:5173`.

## Configuration

The server uses these environment variables (defaults are baked in for the demo; set env vars to override).

Required (override if needed):

- `WEBHOOK_URL` - webhook endpoint URL.
- `WEBHOOK_SECRET` - value for the `x-webhook-secret` header.
- `STORAGE_URL` - storage API endpoint URL.
- `STORAGE_API_KEY` - value for the `X-API-Key` header.

Optional:

- `BASE_URL` - base URL for the Wonderful demo app (used to derive the API base URL).
- `API_BASE_URL` - API base URL (defaults to the `BASE_URL` with `wonderful.app` replaced by `api`).
- `PORT` - server port (default `5173`).

Defaults currently in code (edit `server.mjs` or set env vars if you need to change the task metadata):

- `BASE_URL`: `https://iec.app.sb.wonderful.ai`
- `API_BASE_URL`: `https://iec.api.sb.wonderful.ai`
- `WEBHOOK_URL`: `https://api.sb.wonderful.ai/api/v1/tasks/webhook/38d2ed4a-3435-474c-aade-c1800adad9c0`
- `WEBHOOK_SECRET`: `29743c1f-c0d1-44b5-8e4d-752aa799f128`
- `STORAGE_URL`: `https://iec.api.sb.wonderful.ai/api/v1/storage`
- `STORAGE_API_KEY`: `2ad14e81-c3e4-4191-8c8f-43f70b8d1f48`
- `task_type`: `process_application`
- `trigger_id`: `4fd88805-7cde-4a7a-9d99-5347e5fb308e`

## Vercel Deployment

Set the required environment variables in the Vercel dashboard (Project → Settings → Environment Variables) before deploying. The frontend does not receive these values.

### Example (placeholders)

```bash
PORT=5173 \\
WEBHOOK_URL=<your_webhook_url> \\
WEBHOOK_SECRET=<your_webhook_secret> \\
STORAGE_URL=<your_storage_url> \\
STORAGE_API_KEY=<your_storage_api_key> \\
npm start
```
