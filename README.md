# ppt
*/
# Auto PPT Generator - Example Implementation


This repository demonstrates a simple full-stack app that converts long text into a PowerPoint presentation using an LLM (user-supplied API key) or a local fallback.


## Features
- Paste large text (markdown or prose)
- Optional one-line guidance (tone)
- Upload a .pptx/.potx template to pick up styles & images
- Uses user-supplied LLM API key (OpenAI example) — not stored
- Downloads the generated .pptx


## How to run


### Backend (FastAPI)


1. `cd backend`
2. `python -m venv .venv && source .venv/bin/activate` (on Windows use `.venv\\Scripts\\activate`)
3. `pip install -r requirements.txt`
4. `uvicorn main:app --reload --host 0.0.0.0 --port 8000`


### Frontend (Vite + React + Tailwind)


1. `cd frontend`
2. `npm install`
3. `npx tailwindcss init` (or ensure Tailwind is configured)
4. `npm run dev`


Open http://localhost:5173 (or what Vite prints)


## Security & Limits
- The API key you paste is forwarded to the LLM provider for a single request and is never logged by this demo. In production, move to direct client-to-provider calls or a secure proxy and implement rate limiting.
- This demo does not generate images via AI. It reuses images from the template when present (best-effort).
- LLM output parsing may fail — there is a local fallback that splits text into slides.


## Extensions
- Add better template style copying (fonts, color themes)
- Use server-side caching for large templates
- Add speaker notes generation, slide previews, and pagination




/* End of project files */
