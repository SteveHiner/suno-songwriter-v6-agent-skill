# Suno Meta-Tags

Use this reference for bracketed and parenthetical cues that go *inside* the `Lyrics:` body, beyond plain section headers. These are prompting conventions, not a formally guaranteed command language; individual cues may be ignored or sung.

## Section Headers vs Inline Cues

Two different things:

- **Section headers** start a section: `[Verse 1]`, `[Chorus]`, `[Bridge]`, `[Theme A]`. Always on their own line.
- **Inline cues** sit between or inside lyric lines and tell Suno to change delivery, hand off vocals, drop in an instrumental moment, add an effect, or stop the song.

Section headers can also carry a short performance descriptor (see `references/song-structure.md` § Section Tag Descriptors): `[Whispered Verse]`, `[Explosive Chorus]`, `[Half-time Verse 2]`.

## v6 Section Cues

Community testers report that v6 reads short performance direction written inside a section header and acts on it, including details that appear nowhere in Style. The best-known example is a v6-written caption describing a whispered French bridge and Italian verses that existed only in the section cues. The evidence is one launch-day test repeated by guides, so treat it as a useful lever, not a guarantee.

Two equivalent forms are in use. Pick one per song and keep it consistent:

```text
[Verse 1 - low, close-mic, almost spoken]
[Bridge | whispered, in French]
[Final Chorus | key lift, gang vocals]
```

- Keep the descriptor to roughly 3-12 words with one or two instructions. Stacking many modifiers behind several pipes is unverified and more often ignored.
- Use a cue where delivery, language, energy, or arrangement actually changes. Persistent genre and mix still belong in Style.
- When a section change is essential, state it in both places: a cue in the section header and one plain clause in Style (for example `whispered French bridge`). Testers report that agreement between fields lands more often than either alone.
- Unknown or invented bracket tags are reported to be dropped rather than interpreted. Prefer plain musical words over coined tag syntax.
- Never use em dashes or en dashes in cues. Use the ASCII hyphen or the pipe.
- Section headers are hints. Testers also report v6 sometimes rolls through Verse, Pre-Chorus, Chorus, and Bridge labels without an audible reset; make the contrast audible in the writing (phrase length, register, density) as well as in the tag.

## Instrumental Moments

Put these on their own line where the band should take over:

```text
[Guitar Solo]
[Instrumental Break]
[Drum Break]
[Piano Interlude]
[Saxophone Solo]
[Beat Drop]
[Build]
[Breakdown]
```

These work in both vocal songs and as structural markers. Keep them sparse: one or two per song. A long stack of solo tags usually produces a muddy jam, not a clean arrangement.

## Vocal Delivery

Cue how a line is sung:

```text
[Spoken]
[Whispered]
[Shouted]
[Belted]
[Falsetto]
[Soft]
[Aggressive]
[Vocoder]
[Layered Vocals]
[Harmonies]
[Call and Response]
```

Place the cue on its own line directly above the lines it affects, or at the start of a section header. Mid-line cues risk being sung aloud.

## Multiple Vocalists

Hand off between voices:

```text
[Male Voice]
[Female Voice]
[Duet]
[Both]
[Choir]
[Group Vocals]
[Child Voice]
[Narrator]
```

Use these when the song needs verse trading, a duet chorus, or a featured guest section. Keep the count low and audition the hand-offs; distinct voices are not guaranteed. If the user has a trained Voice selected, do not fight it with vocal-gender tags.

Use bracketed vocalist labels for duet/storytelling layouts; reserve parentheses for words intended to be sung:

```text
[Male Voice]
[Female Voice - wordless hum]
[Female Voice - wordless backing]
[Male Voice - spoken, intimate]
```

Use them on their own line before the affected passage. Keep the label short enough that it works as a cue, not a lyric.

## Ad-Libs and Backing Phrases

Short parenthetical phrases suggest backing/ad-lib vocals, but may be delivered as lead lines:

```text
I'm not coming back (no no)
Hold the line (hold it)
Say it again (say it, say it)
```

Use sparingly in choruses, post-choruses, and rap hooks. Long parentheticals get sung as lead and clutter the line.

## Sound Effects and Texture

Suno will attempt ambience or one-shot effects from tags like:

```text
[Applause]
[Crowd Cheering]
[Laughing]
[Phone Ringing]
[Rain]
[Vinyl Crackle]
[Static]
[Door Slam]
[Footsteps]
```

Reliability varies. Treat these as nice-to-have, not load-bearing. If an effect is essential, also describe it in `Style:` for vocal and Advanced modes or `Instrumental Prompt:` for Instrumental Mode (e.g. `vinyl texture`, `crowd ambience`).

For groove-narrative vocal songs, short arrangement cues can be useful inside the lyric block:

```text
[Intro - 8 bars, bus doors hiss, street ambience, Rhodes and bass groove]
[drums enter bar 7]
[Bridge - drums drop to kick and hi-hat, bass lead]
[Fade to end - bus engine drone, night crickets, Rhodes chord]
```

Use these when the sound design is part of the concept. Avoid overloading every section with long production notes.

## Ending Control

Suno will often invent extra verses or fade awkwardly if the lyric block ends without a signal. Use:

```text
[Outro]
[End]
[Fade Out]
[Hard Stop]
```

`[End]` after the final section requests closure; it cannot guarantee that generation stops there. Crop an unwanted tail or edit the generated audio when precision matters. For loopable instrumentals, do the opposite: avoid a hard ending and mark `[Loop Point]`.

## Rules and Failure Modes

- **Tags get sung if placed mid-line:** Keep cues on their own line.
- **Unknown tags are dropped:** Coined syntax such as a timed rest inside brackets is not documented; plain musical words work better than invented commands.
- **Too many tags = ignored or muddy:** Budget tags by purpose. A groove-narrative song can carry more arrangement cues than a pop song, but each cue should affect the recording.
- **Don't put production direction in tags:** Persistent genre/instrument/mix direction belongs in `Style:` for vocal and Advanced modes or `Instrumental Prompt:` for Instrumental Mode. Tags are for moment-to-moment changes.
- **`[End]` requests closure:** If the user complains Suno keeps adding verses, add `[End]`.
- **Brackets in lyrics ≠ Suno-only:** Check whether the target tool supports section headers or inline cues before carrying them across. Note that when writing portable prompts.

## Output Note

When meta-tags materially shape the arrangement, mention it briefly in `Suno v6 Notes:` (e.g. `Uses [Guitar Solo] after Chorus 2 and [End] to cap length`). Do not narrate every tag: the lyric body already shows them.
