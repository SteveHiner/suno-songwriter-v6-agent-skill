# v6 Production Direction

Use this reference when a compact Style line underspecifies the recording: dense full-band arrangements, a take with a named production fault, or a brief where the performance matters as much as the genre. For model choice, sliders, and field mapping, see `suno-v6-controls.md`.

Status: this file collects community field notes from v6 users, not documented platform behavior. Suno publishes no guidance on prompt ordering, production vocabulary, or ending buffers. Treat every technique here as a starting hypothesis to test against the user's own takes, and say so when recommending one. The slider guidance in `suno-v6-controls.md` is corroborated by Suno's own note on Variety; the rest is not.

## The Core Move

Name the finished recording, not only the genre. A genre label tells the model what shelf the song sits on; it does not tell the drummer how busy to be, the guitarist what their hands are doing, or the mix what clean means. For unusual combinations, assign each element a role so the desired result can be evaluated.

Direct the musicians and the engineer in the same prompt.

## Directed Brief

The default remains a compact Style line of roughly 200 characters. When that line cannot carry the arrangement, use a labeled brief in musical order instead:

```text
Genre: cumbia sonidera, dub bass weight, psychedelic surf guitar.
Vocals: weathered male tenor, conversational phrasing, group responses on the hook.
Drums: steady guira and timbale pattern, rim accents, steady verse pattern, fills at section transitions.
Bass: heavy round electric bass, long sustained roots, dub delay throws.
Other: tremolo surf guitar lead, spring reverb organ stabs, tape echo.
Arrangement: full-band energy throughout, percussion stays active under every verse.
Production: high-fidelity studio production, close-mic lead vocal, open low-mids, clear high-end air, layered instruments with clear separation, stable loudness.
Ending: complete every written lyric before a short instrumental outro and a hard stop.
```

Tradeoff: the brief spends far more of the field than a compact line and leaves less room to iterate, and no test shows it beats a well-written compact line on a simple brief. Use it where the arrangement is dense enough to need every label, not as the default shape. Drop any label the song does not need rather than filling it.

## Instrument Activity

Name what the player is doing. Nouns describe the lineup; verbs describe the performance.

| Instead Of | Write |
| --- | --- |
| `electric guitars` | `interlocking melodic leads, fast alternate picking, driving power chords` |
| `aggressive drums` | `relentless driving drums, rapid double kick, active fills, ghost notes, ride bell accents` |
| `bass guitar` | `active melodic bassline countering the guitar riff` |
| `banjo and fiddle` | `rolling three-finger banjo, fiddle trading breaks with the mandolin` |
| `synths` | `arpeggiated analog lead climbing each bar, sustained pad underneath` |
| `horns` | `stabbing brass shots on the offbeats, saxophone answering each vocal line` |

## Vocal Character

Register, texture, and delivery carry further than gender alone. State the wanted behavior rather than listing everything to avoid.

- `mature low-mid male vocals, gritty chest voice, raspy melodic cleans, powerful sustained chorus`
- `gritty expressive female cleans, strong chest voice, contemporary rock delivery, aggressive edge`
- `light airy falsetto, breathy close-mic delivery, doubled on the hook`
- `mid-low false cord growls, visceral fry screams, guttural lows`

For a texture that must hold across the whole track, say so positively and per section: `unclean vocals throughout, growls and fry screams in every vocal section`. Start with one clear description of the wanted delivery; compare results before adding exclusions.

If a female vocal keeps arriving operatic when the brief wants rock, name the register and delivery directly: `gritty chest voice, contemporary rock delivery, aggressive edge`.

## Verse Energy

If a take has a full intro and chorus but verses where most of the band drops out, check whether that contrast serves the brief. Nothing in the prompt asked for continuous energy, so the model is free to thin the arrangement.

State it when it matters:

- `full-band energy throughout`
- `continuous foreground guitar activity`
- `active bass and drums under every verse`
- `layered rhythm guitars remain present beneath the vocal`
- `verses maintain forward momentum`

One compact version: `full-band energy throughout with foreground riffs and active drums during verses`.

## Vocal Delivery And Lyric Density

"v6 vocals sound flat or rushed" is the most common v6 complaint in community reports. Work in this order; each step is cheaper than the next.

1. **Check the rendered tempo.** One tester asked for 74 BPM and the editor read back 130 (possibly double-time detection, possibly an ignored BPM). Lyrics written for a slow tempo will rush at a fast one whatever else changes. Write the BPM in Style, check what the song reports, and regenerate if they disagree.
2. **Reduce syllable load.** Match words to tempo and section length; cut words before cutting lines. Splitting long lines into short ones did not slow delivery in one replication report; fewer syllables does.
3. **Punctuate for breath.** A comma inside a line, where a singer would breathe, reportedly produces a small hold (`Salt, on a borrowed guitar`). A comma at the end of a line reportedly causes stutter, because the line break already ends the phrase; strip trailing commas from lyric lines.
4. **Direct delivery per section,** positively: `[Verse 1 | soft chest voice, behind the beat, holding the ends of lines]`, `[Chorus | full voice, pushed, sustained]`.
5. **Repair locally.** For one bad line or section, use a plain-language edit or Replace Section instead of rebuilding the song. Shorter sections give finer edit boundaries. One tester estimates section replacement lands cleanly about two times in three; audition the joins.

Experiments, offered only after the steps above and labeled as anecdotal (two independent reports, mostly slow ballads):

- `[Silence]` at the end of every lyric line, inline rather than on its own row, reportedly adds a breath-to-a-beat hold. Pause length is not controllable. Do not add periods or an ellipsis before it; testers found stacked stop markers sped delivery up. Do not combine it with other stop tags.
- Capitalizing a word reportedly makes it land harder. Use it sparingly and escalate toward the final chorus.
- Invented tags such as `[2 Bar Rest]` did nothing; unknown tags are dropped. An instrument tag at a line end is texture, not a gap.
- The same testers found a higher Variety setting gave more melodic movement than Off. Hold Variety at Off while testing a change, then consider raising it for the generation you intend to keep, accepting that Style may be rewritten.

## Buried Or Muffled Vocals

Community diagnosis splits "muffled" into three causes with different fixes:

| Cause | Test | Fix |
| --- | --- | --- |
| Density: too many parts in the vocal range | The vocal snaps into focus when the band drops out | Say per section what plays under the vocal: `verse: only acoustic guitar and bass under the vocal`; add habitual culprits (pads, strings, synth layers) to Exclude |
| Placement: the vocal was never put in front | Arrangement is clear but the voice sits inside it | Place it, do not praise it: `lead vocal in front of the band, close-miked and dry, instruments sit behind and below the voice`. Put the vocal clause right after the genre |
| Render: the take itself is dull | The intro is already dull before the vocal enters | No adjective adds top end. Regenerate the same prompt, try another model, keep the song shorter; Max Mode if it degrades late in the track |

Quality words (`crisp`, `clear`, `professional`, `radio-ready`) give the model nothing to act on; placement and relationships do. For a dry vocal, say it positively (`dry, close-mic'd, narrow stereo image`) and move reverb, hall, and room words out of Style and into Exclude.

## Voice Line

A useful Style voice line has four parts, about 15 to 30 words, placed right after the genre: who (range and voice type), texture (rasp, breath, grit), delivery (half-spoken verses, belted chorus, behind the beat), and placement (close and dry, doubled in the chorus). Example: `a warm female alto with a little rasp, singing just behind the beat, close and dry in the verses and doubled in the chorus`. Change it per section in the section headers rather than in Style.

## Production Clause

When a take sounds muffled, distant, or smeared, describe the wanted result rather than writing `professional production`. Keep the clause short; the musical direction still needs the field.

Working vocabulary: `high-fidelity studio production`, `close-mic lead vocals`, `stable vocal intensity and loudness`, `open defined low-mids`, `clear high-end air`, `crisp transients`, `layered instruments with clear separation`, `stable tonal balance`, `consistent mix fidelity throughout`.

| Fault | Clause |
| --- | --- |
| Muddy or blanketed | `open defined low-mids, clear high-end air, crisp transients` |
| Vocal sounds far away | `close-mic lead vocals, intimate vocal presence` |
| Loudness swings between sections | `stable vocal intensity and loudness, consistent mix fidelity throughout` |
| Instruments blur into one wall | `layered instruments with clear separation` |

A compact all-purpose version: `high-fidelity studio production, close-mic vocals, crisp transients, clear instrument separation, open low-mids, stable loudness and tonal balance`.

## Endings

v6 takes sometimes stop while the vocalist is still singing. Give the song somewhere to land after the last lyric so an early cut consumes a disposable section instead of a sung line.

```text
[Final Chorus]
last written lines here

[Instrumental Outro]
[End]
```

Pair it with a short ending instruction in Style: `complete every written lyric before a short instrumental outro and a hard stop`.

The opposite fault is an outro that wanders. A bare `[Outro]` leaves the shape open; name the ending you want instead. `[Hard Stop]` appears in community prompts and is not documented Suno syntax. Both it and `[End]` request closure and cannot enforce it, so audition and Crop for an exact time.

## Intros

An undefined intro invites improvised vocal noise before the song starts. Either begin the lyric immediately under `[Intro]`, or declare `[Instrumental Intro]` and describe its instrumentation in Style. Leave no unlabeled space at the top.

## Keep What Works

A prompt that produced a good song is a result worth keeping verbatim. Save the exact Style text, sliders, and model alongside the track rather than editing the recipe in place, and version a v6 revision as a new entry beside the original. This matters more now than it did: every pre-v6 model is retired, so a recipe written for v5.5 cannot be rerun for comparison. See `studio-and-iteration.md` for take logs and stopping criteria.

## Musical Detail And Prompt Priority

Use `harmony-and-melody.md` for harmonic rhythm, contour, and vocal range; use `rhythm-and-arrangement.md` for meter, pocket, and part roles. These describe musical intent, not additional v6 controls.

For a dense brief, retain the user's must-haves first: identity and groove, foreground performance, then section changes. Add mix adjectives only for an actual goal or observed fault. If a take misses a requirement, simplify competing directions before adding more tags. State exact chords, notes, meter, and duration as targets to verify by listening. For strict reproduction, use a supported audio or MIDI reference rather than promising text-level precision.
