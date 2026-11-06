# StoryVoice

**Your books, performed by a full cast.**

StoryVoice turns a book into a multi-voice audiobook in your browser. It reads the whole book, works out who is speaking and how they feel, then narrates it with a distinct voice for every character.

**Try it:** https://projectstoryvoice.netlify.app

<!-- Add a screenshot of the player here: ![StoryVoice player](docs/player.png) -->

## Features

- **Many formats:** PDF, EPUB, TXT, Markdown, HTML, Word (.docx) and PowerPoint (.pptx).
- **A voice for every character:** dialogue is attributed to speakers, and each character gets their own voice.
- **Emotion-aware narration:** pacing and volume follow the mood of each line.
- **Free AI voices:** [Kokoro](https://huggingface.co/hexgrad/Kokoro-82M) runs on your own computer, with no account or API key.
- **Prepared chapters:** generate a chapter's audio once, play it smoothly any time, or download it as a `.wav` file.
- **Word-by-word highlighting:** the text animates as it's read.
- **Listening tools:** chapters, bookmarks, sleep timer, speed control and resume.
- **Private:** books and audio stay in your browser. Nothing is uploaded to a server.

## Where to find books

[Readflix](https://readflix.club/) has 95,000+ free public-domain books. Download one as EPUB or TXT and drop it into StoryVoice.

Only use books you own or have permission to use.

## Running it yourself

StoryVoice is a single `index.html` file with no build step.

**Quickest:** download `index.html` and open it in Microsoft Edge or Google Chrome.

**Recommended (faster voices):** serve the folder locally:

```bash
python -m http.server 8000
```

Then open http://localhost:8000.

**Deploying:** any static host works. On Netlify, keep the `_headers` file next to `index.html`. It lets Kokoro use every processor core, which makes voices roughly 2–4× faster.

## Browser support

| Browser | Status |
|---|---|
| Microsoft Edge | Best. Includes free Microsoft neural voices, and runs Kokoro well |
| Google Chrome | Supported |
| Firefox, Safari | Partly supported. Kokoro is slower, and some features may not work |
| Phones | Uses the phone's built-in voices by default. Kokoro may be too heavy |

## How it works

1. **Reading:** the file is converted into chapters and paragraphs in the browser (pdf.js, JSZip, DOMParser).
2. **Casting:** on claude.ai, Claude builds character profiles and works out who says each line. Elsewhere, speakers are guessed from attribution tags like "said Sarah".
3. **Voicing:** lines are spoken with Kokoro (in a background worker) or with the browser's built-in voices.
4. **Storage:** books, progress and prepared audio are saved in IndexedDB on your device.

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

## Credits

- [Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M) and [kokoro-js](https://github.com/hexgrad/kokoro) (Apache-2.0)
- [pdf.js](https://github.com/mozilla/pdf.js) (Apache-2.0)
- [JSZip](https://github.com/Stuk/jszip) (MIT or GPL-3.0)

## License

StoryVoice is free software, licensed under the [GNU Affero General Public License v3.0](LICENSE).

If you run a modified version of StoryVoice as a website, you must make your modified source code available to its users.
