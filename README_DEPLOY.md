# SIFF AI Recommender

This folder is a Vercel backend for the Shanghai International Film Festival questionnaire.

## What It Does

- Receives questionnaire answers from the static page.
- Reads `data/schedule.json`, generated from the festival schedule spreadsheet.
- Calls the OpenAI Responses API from the server.
- Returns a recommendation directly to the webpage.

The browser never sees your OpenAI API key.

## Deploy To Vercel

1. Create a new Vercel project and upload/import this folder.
2. In Vercel project settings, add Environment Variables:
   - `OPENAI_API_KEY`: your OpenAI API key
   - `ALLOWED_ORIGIN`: `https://14zayn14.github.io`
   - `OPENAI_MODEL`: `gpt-5-mini`
3. Deploy.
4. Copy the deployed function URL:
   - `https://your-project.vercel.app/api/recommend`
5. Put that URL into the GitHub Pages `index.html` as `DEFAULT_RECOMMEND_API_URL`, then re-upload it to the repository root.

## Cost Controls

- Default model: `gpt-5-mini`
- Default max answer length: `12000` characters
- Default max output tokens: `1800`

You can lower `MAX_OUTPUT_TOKENS` in Vercel environment variables if you want stricter token control.
