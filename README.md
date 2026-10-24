# Reise-Übersetzer – German ⇄ English voice translator

Static front end (`index.html`) + one serverless function (`api/translate.js`)
that calls the Google Gemini API. Your API key stays on the server.

## Deploy on Vercel (free tier is fine)
1. Get a free API key at https://aistudio.google.com/apikey
2. Push this folder to a GitHub repo (or run `npx vercel` inside it).
3. Import the repo at https://vercel.com/new
4. In Project Settings → Environment Variables add:
   - `GEMINI_API_KEY` = your key
   - `GEMINI_MODEL` (optional, default `gemini-3.6-flash`; set e.g. `gemini-2.5-flash` if that name isn’t available to your key)
5. Deploy. Open the HTTPS URL on your phone and allow microphone access.

## Run locally
    npm i -g vercel
    vercel dev        # asks for env vars; serves on http://localhost:3000

(Microphone access needs HTTPS or localhost.)

## Notes
- Voice input uses the browser’s Web Speech API: Chrome, Edge and Safari work; Firefox doesn’t (typing still works).
- Add rate limiting before sharing the URL publicly, since anyone with the link can use your API quota.
