# Suno Speech (Beta)

Use this reference when the user wants spoken audio rather than a sung song: a narrated poem, bedtime story, meditation, pep talk, dramatic reading, voice-note joke, or ASMR piece over music. Sources: Suno's [Speech announcement](https://suno.com/blog/introducing-speech-beta) and [release notes](https://suno.com/release-notes), read 2026-11-04.

## What It Is

Speech launched 2026-10-01 as an open beta on web and mobile. Suno describes it as "the first audio model that generates voice and music together as one cohesive track": type an idea, a poem, or something written, then describe the voice and the musical style. It is a separate creation mode, not a song model, so Style, Lyrics, and the v6 sliders do not apply unless the user's screen shows them.

Suno's own caveats: accents can wander, and "dramatic pauses may be very dramatic." Community guides add that it is not precision text-to-speech, and that music may still appear when the user asks for none. Credit cost, maximum length, and supported languages are not published.

## When To Route Here

| Request | Route |
| --- | --- |
| Spoken piece with a score underneath | Speech |
| Song with a spoken verse or bridge | Normal v6 song; mark the section `[Spoken]` (see `suno-meta-tags.md`) |
| Rap or spoken-sung vocal over a beat | Normal v6 song |
| Exact narration with no music | Say Speech may still add music; a dedicated TTS tool may fit better |

Offer Speech as an option when the brief is mostly spoken. Do not claim the user has it; confirm that Speech appears in their Create page.

## Output

```text
Title: <title>
Script:
<the exact words to be spoken, in short sentences and paragraphs>
Voice: <age range, accent, register, pace, attitude; e.g. warm low female narrator, unhurried, gentle smile in the voice>
Music: <genre, instruments, tempo, energy arc, how it sits under the voice; e.g. soft felt piano and distant strings, slow, swells only at the last line, always under the voice>
Notes: <optional: pacing changes, where the music should rise or drop out, beta caveats>
```

## Writing For Speech

- Write the finished script yourself when wording matters. Asking Suno to write it hands over the words.
- Use short sentences and paragraph breaks where a breath or pause belongs. Punctuation is the main pacing tool; do not add bracket tags unless the user's interface documents them.
- Describe the voice by traits, never by a real person's name.
- Give the music a job relative to the voice: under, answering between lines, or swelling at a single moment. One arc is enough.
- Keep the craft standards of the skill: a clear center, concrete detail, and an ending that lands. A bedtime story still needs a shape.
- Apply the output contract's punctuation rule: no em dashes or en dashes in the script.
