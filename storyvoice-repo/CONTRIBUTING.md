# Contributing to StoryVoice

Thanks for helping. Bug reports, ideas, docs and code are all welcome.

## Ways to help

- **Report a bug:** open an issue with the bug report template. Include your browser and the grey "Sound:" line from **Character studio → Test sound**.
- **Suggest a feature:** open an issue with the feature request template.
- **Fix something:** look for issues labelled `good first issue`.
- **Test:** try books in different formats and browsers, and report what breaks.

## Before you start coding

For anything bigger than a small fix, open an issue first to discuss it. This avoids two people building the same thing, or work that doesn't fit the project.

## Making a change

1. Fork the repository and create a branch: `git checkout -b fix-epub-titles`
2. Run it locally: `python -m http.server 8000`, then open http://localhost:8000
3. Make your change in `index.html`.
4. Test it (see the checklist below).
5. Commit with a clear message, for example `Fix EPUB chapter titles with numbers`.
6. Push your branch and open a pull request. Describe what changed and how you tested it.

## Project rules

- **Single file.** StoryVoice is one `index.html` with no build step. Keep it that way unless an issue agrees otherwise.
- **No accounts or tracking.** Books and audio stay on the user's device.
- **No API keys in the code.**
- **External scripts** load only from cdnjs.cloudflare.com or cdn.jsdelivr.net, pinned to an exact version.
- **Accessibility.** Buttons need labels, and the app must work with the keyboard.
- **Both themes.** Check that your change looks right in light and dark mode.

## Testing checklist

- [ ] Uploading a PDF and an EPUB still works
- [ ] Playback, skip, speed and chapter navigation work
- [ ] Tested in Edge and Chrome
- [ ] Checked on a narrow (phone-sized) window
- [ ] No errors in the browser console

## Licence

By contributing, you agree that your contributions are licensed under the [AGPL-3.0](LICENSE), the same licence as the project.

## Code of conduct

Please follow the [Code of Conduct](CODE_OF_CONDUCT.md).
