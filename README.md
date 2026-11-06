
StoryVoice

Your books, performed by a full cast.

StoryVoice turns a book into a multi-voice audiobook in your browser. It reads the whole book, works out who is speaking and how they feel, then narrates it with a distinct voice for every character.

Try it:
https://projectstoryvoice.netlify.app


FEATURES

- Many formats: PDF, EPUB, TXT, Markdown, HTML, Word (.docx), and PowerPoint (.pptx).
- A voice for every character: Dialogue is attributed to speakers, and each character gets their own voice.
- Emotion-aware narration: Pacing and volume follow the mood of each line.
- Free AI voices: Kokoro runs on your own computer, with no account or API key.
  https://huggingface.co/hexgrad/Kokoro-82M
- Prepared chapters: Generate a chapter's audio once, play it smoothly any time, or download it as a .wav file.
- Word-by-word highlighting: The text animates as it's read.
- Listening tools: Chapters, bookmarks, sleep timer, speed control, and resume.
- Private: Books and audio stay in your browser. Nothing is uploaded to a server.


WHERE TO FIND BOOKS

Readflix has 95,000+ free public-domain books. Download one as EPUB or TXT and drop it into StoryVoice.

https://readflix.club/

Only use books you own or have permission to use.


RUNNING IT YOURSELF

StoryVoice is a single index.html file with no build step.

Quickest Method:

Download index.html and open it in Microsoft Edge or Google Chrome.

Recommended Method (Faster Voices):

Serve the folder locally:

python -m http.server 8000

Then open:

http://localhost:8000


DEPLOYING

Any static host works.

On Netlify, keep the _headers file next to index.html. It lets Kokoro use every processor core, which makes voices roughly 2–4 times faster.


BROWSER SUPPORT

Microsoft Edge:
Best. Includes free Microsoft neural voices and runs Kokoro well.

Google Chrome:
Supported.

Firefox and Safari:
Partly supported. Kokoro is slower, and some features may not work.

Phones:
Uses the phone's built-in voices by default. Kokoro may be too heavy.


HOW IT WORKS

1. Reading:
The file is converted into chapters and paragraphs in the browser using pdf.js, JSZip, and DOMParser.

2. Casting:
On claude.ai, Claude builds character profiles and works out who says each line. Elsewhere, speakers are guessed from attribution tags like "said Sarah".

3. Voicing:
Lines are spoken with Kokoro (in a background worker) or with the browser's built-in voices.

4. Storage:
Books, progress, and prepared audio are saved in IndexedDB on your device.


CONTRIBUTING

Contributions are welcome. Please read CONTRIBUTING.md first.


CREDITS

Kokoro-82M:
https://huggingface.co/hexgrad/Kokoro-82M

kokoro-js:
https://github.com/hexgrad/kokoro

pdf.js:
https://github.com/mozilla/pdf.js

JSZip:
https://github.com/Stuk/jszip

Kokoro-82M and kokoro-js are licensed under Apache-2.0.
pdf.js is licensed under Apache-2.0.
JSZip is licensed under MIT or GPL-3.0.


LICENSE

StoryVoice is free software, licensed under the GNU Affero General Public License v3.0.

If you run a modified version of StoryVoice as a website, you must make your modified source code available to its users.
