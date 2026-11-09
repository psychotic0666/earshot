# Earshot

Record conversations on your phone, grouped into events. Each recording gets a transcript, summary, key points, to-dos, reminders (with "Add to calendar"), decisions, open questions and sentiment. Each event gets a combined analysis and a sentiment trend across its recordings.

Everything is stored on your device (IndexedDB). Nothing leaves the phone unless you add an API key.

## Put it on your iPhone (GitHub Pages, free)

1. Create a new public repository on github.com, for example `earshot`.
2. Upload every file in this folder to the repository root.
3. Go to the repository's **Settings → Pages**, set **Source** to "Deploy from a branch", choose `main` and `/ (root)`, then save.
4. After a minute, open `https://<your-username>.github.io/earshot/` in **Safari** on the iPhone.
5. Tap **Share → Add to Home Screen**. Open Earshot from the home screen icon from then on.

Netlify Drop (drag the folder onto app.netlify.com/drop) or Cloudflare Pages work too. The site must be served over HTTPS for the microphone and offline mode to work.

## Transcription and analysis options (Settings)

| Setting | Cost | Notes |
|---|---|---|
| Built-in speech recognition | Free | Live captions while recording, uses iOS speech recognition. Quality varies; may not run in every context. |
| Transcription API | Paid per minute | Sends audio to OpenAI (`whisper-1`, `gpt-4o-transcribe`) or any OpenAI-compatible service such as Groq. Up to 25 MB per recording (about an hour). |
| Basic analysis | Free, offline | Word-based summary, to-dos, reminders and sentiment. Rough. |
| Claude | Paid per use | Anthropic API key. Best summaries, to-dos, reminders, emotions and mood timeline. |
| OpenAI-compatible | Paid per use | Any chat model that supports JSON mode. |

API keys are stored only in this browser and are sent only to the service they belong to.

## Tips

- Keep the app open and the screen on while recording. iOS stops the microphone when the app goes to the background.
- Add notes to an event (⋯ → Edit notes) such as who attended; the analysis uses them.
- Back up regularly in Settings. Clearing Safari website data erases the app's data.
- After changing `index.html`, bump `VERSION` in `sw.js` so installed copies update.
