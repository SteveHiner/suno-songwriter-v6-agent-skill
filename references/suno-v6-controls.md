# Suno v6 Controls

Use this reference for model choice, field mapping, sliders, personalization, and troubleshooting. The skill targets Suno v6; the v6 FAQ, model, what's-new, Voices, and Custom Models articles, the v6 announcement, and the release notes were read directly on 2026-11-04; other source checks remain dated 2026-09-13. Community v6 test reports (slider defaults, Variety behavior, section cues, Voices, Custom Models, lyric density) were surveyed 2026-11-04 and are labeled as reported, not documented. Account, plan, app, and rollout can change which controls appear. Confirm the user's surface before prescribing unavailable settings.

## Models

Suno released the v6 generation on 2026-09-09 and retired every earlier model. v5.5, v5, v4.5, and v4 can no longer generate new material. Songs already in a library stay playable, shareable, and eligible for remaster and cover; any new iteration runs on v6. Do not offer a model choice the user cannot select, and do not treat a v5.5-era recipe as reproducible.

[Current Models: v6](https://help.suno.com/en/articles/13924737) lists three variants, chosen from the model dropdown at the top right of the Create form. The same dropdown holds Custom Models and a selected Voice. Pick by how much control the request needs, not by tier.

| Model | Use For | Access |
| --- | --- | --- |
| `v6` | Flagship. Precise, polished, strongest adherence when the brief is specific | Pro and Premier |
| `v6-wild` | Deliberate exploration. Less predictable, more varied, unconventional results | Pro and Premier |
| `v6-mini` | Faster and lighter; the free-plan model | All plans |

Default to `v6` for a defined brief and to `v6-wild` only when the user wants surprise. `v6-wild` is designed to deviate from the prompt, so judge it across several generations, not one. Write for `v6-mini` when the user is on the free plan; keep the same craft and drop paid-only control suggestions. [What's new in v6](https://help.suno.com/en/articles/13924801) states all three variants generate up to 8 minutes in one pass.

## What Changed From v5.5

Use this list when a user brings v5.5 habits or recipes. Documented items come from Suno's v6 pages; reported items are community observations to verify by listening.

| Area | v5.5 habit | v6 practice |
| --- | --- | --- |
| Models | One model plus older picks | `v6`, `v6-wild`, `v6-mini` only; pre-v6 models cannot generate (documented) |
| Length | Shorter ceilings per model | Up to 8 minutes per generation on all three (documented); Duration Custom reported at 0:10 to 6:00 |
| Style text | Tag stacks worked | Plain musical language that connects voice, instruments, and feel tends to work better; long vague adjective lists get averaged into blandness (reported) |
| Style rewriting | Text used as typed | Variety can rewrite Style before generation; set it to 0 to keep control (documented) |
| Take variance | Takes differed modestly | The two takes of one generation can differ more than a deliberate prompt edit (reported) |
| Section cues | Bare section headers | v6 reportedly reads short delivery direction inside a section bracket, such as `[Bridge \| whispered, in French]`; see `suno-meta-tags.md` (reported, thin evidence) |
| Editing | Replace Section by region | Plain-language edits of one section or one lyric line, on top of Replace Section (documented) |
| Inputs | Text and audio uploads | Songs, playlists, audio, images, video, voice memos, mashups, sample-and-isolate (documented) |
| Personas | Personas button | Voices; older Personas convert and can be upgraded to v6 (reported); see `personas.md` |
| Consistency | Prompt only | Max Mode toggle trades credits for consistency (documented) |
| Training data | Unstated | Suno says v6 was developed with industry partners including Warner Music Group, BMG, and Believe. Mention only if the user asks about provenance |
| Spoken audio | Spoken tags inside a song | A separate Speech (beta) mode generates narration and its soundtrack together; see `suno-speech.md` (documented) |

Suno's FAQ says v6 "understands more of the language and building blocks musicians use" and that in Simple mode "you don't need to know which tool to reach for (like Cover, Remix, Extend)... The model figures out the workflow." Old v5.5 prompts were tuned to a model that no longer exists. Rebuild from the song's intent rather than porting a recipe word for word.

## Surfaces

The Create page separates Simple, Advanced, and Sounds. Simple takes plain-language description plus references; its description box was measured at 3,000 characters by one community source, so aim for one or two dense sentences. Advanced exposes the explicit controls below and is where every setting in this file lives. Sounds generates short one-shots and loops; see `suno-sounds.md`.

Call it Advanced, not Custom Mode. Suno's [Custom Mode guide](https://help.suno.com/en/articles/3197377) still describes a Custom toggle and is behind the shipped UI; the field order it lists (lyrics or Instrumental, Styles, then the advanced controls) still holds. Do not revert this naming to match that article, and do not equate a no-vocal song with a description-only UI.

| Skill Output | Where It Goes |
| --- | --- |
| `Title` | Title |
| `Style` | Styles: positive sound direction |
| `Excluded Styles` | Exclude Styles under Advanced, when available |
| `Lyrics` | Lyrics: sung words and sparse section cues |
| `Instrumental Prompt` | Styles in Advanced, or the description field on a simpler surface |
| `Arrangement` | Planning map; summarize essential changes in an available prompt field |
| `Slider Suggestions` | Advanced controls only; never paste these into Style or Lyrics |

For a plain instrumental brief, keep the portable `Title` / `Instrumental Prompt` / `Arrangement` package. If the user asks for Advanced settings and exposes those controls, add Excluded Styles and sliders. Enable Instrumental for a strictly voiceless track. For wordless sung syllables, use a vocal-enabled workflow and describe the intended texture.

A title identifies the song. Do not claim it controls mood or generation behavior; put musical intent in the prompt.

## References And Inputs

v6 accepts more than text. The [v6 FAQ](https://help.suno.com/en/articles/13924481) and the [v6 release notes](https://suno.com/release-notes/introducing-v6) document referencing multiple inputs in one request: Suno songs, playlists, audio uploads, images, and video, plus starting from a voice memo. Suno frames this as Simple mode work.

Also documented as new in v6: building a mashup from several sources in one request, and sampling then isolating part of a track to build a new beat around it (Suno's example: sample the riff at 0:45, isolate the guitar, build a beat around it).

Suno's own example requests show the expected phrasing: "Change the chorus so it's sung by a gospel choir", "Take the vocals from x, drums from y, and add new lyrics about losing control, make it 80s synthwave", "Make a song that feels like midnight on a rooftop", "Make a song based on this image, this audio, and my journal entry", and "Change the lyric from 'love' to 'light.'" When the user wants one of these, write the request in that plain, specific form: name each source, what to take from it, and the target.

Suno documents that these inputs exist but not what the controls are called, which mode holds each one, or how many are allowed. Only [Upload Audio](https://help.suno.com/en/articles/6141569) has a confirmed label. Describe the intent and let the user find the control; do not invent a field name for the skill to tell them to fill. Image and video inputs raise the credit cost by an amount Suno does not publish.

[Inspire](https://help.suno.com/en/articles/6882753) is a separate, older feature: a `+Inspo` button above the lyrics box and an Inspire button on a playlist, generating a track in the style of that playlist. It is not the same thing as attaching a reference to a generation, so confirm which one the user means.

## Style And Exclude

Lead with the genre or groove and defining sound, then add mood, tempo, vocal delivery, and a few arrangement or production details. A compact line around 200 characters is a useful default, not a Suno limit. Expand when needed and obey the visible field counter. Suno has never published a character limit for any field; community measurements off the live counters converge on 5,000 for Lyrics and 1,000 for Styles and Exclude Styles. Treat those as measured, not specified, and let the counter in front of the user win.

```text
garage rock, restless, 132 BPM, raw group vocal, distorted guitar and live drums, dry basement mix; pull back to bass and voice before the final chorus
```

Style holds prose, not markup. Square brackets belong in Lyrics; slider values belong in the Advanced panel. Writing `Weirdness: 32%` or `[crisp transients]` into Style spends characters on text the model reads as ordinary prompt content.

When a compact line underspecifies a dense arrangement, or the take has a named production fault, use the directed brief in `v6-production-direction.md` instead of padding this line with adjectives.

Use [Exclude](https://help.suno.com/en/articles/3161921) for unwanted instruments, genres, or vocal traits. Keep the list focused on actual constraints or observed drift; do not fill it with speculative problems. Avoid contradicting Style. Exclude is a request, not a guaranteed ban. Prefer stating the wanted behavior positively in Style over listing its opposite here.

Write Style as connected musical language, not a bag of nouns. `breathy alto close to the mic over brushed drums and upright bass, piano answering each vocal phrase` tells v6 how the parts relate; `jazz, sad, piano, female, slow, moody, cinematic, emotional` leaves it to average. Concrete descriptors beat a long list of vague adjectives. Front-load the defining sound; early terms are reported to carry the most weight.

Translate artist references into era, groove, instrumentation, phrasing, and production. For example: `early-2010s Toronto melodic rap, sparse 808s, hazy keys, intimate half-sung delivery`. This makes individual traits editable and avoids passing artist names to generation fields.

## Creative Sliders

[Official slider behavior](https://help.suno.com/en/articles/6141377): Weirdness spans Safe to Chaos, with 50% described as normal; Style Influence spans Loose to Strong and controls adherence to Styles; Audio Influence appears with audio uploads.

Community guides consistently report v6 defaults of Weirdness 50%, Style Influence 50%, and Audio Influence 25%. A 50% Style Influence gives a carefully written Style line only moderate authority, so a precise brief usually wants it raised. Read the user's displayed values rather than asserting defaults; they are reported, not documented.

### Variety

Variety is in the Advanced tab, confirmed by the user on 2026-09-24. Set it there, not in Styles or Lyrics. This UI-location observation is separate from the documented behavior below. The [v6 FAQ](https://help.suno.com/en/articles/13924481) documents the mechanism and the fix in Suno's own words: the slider "is designed to introduce variety in your outputs by adjusting and updating your style prompts," and "if you'd like to retain full control of your style tags, reduce the Variety slider to 0."

Set Variety to 0 whenever the exact Style text matters: A/B prompt comparisons, a persona or album that must stay consistent, a recipe the user wants reproduced. A rewritten prompt can obscure the change being tested, so prompt comparisons should control Variety as well as the other visible settings. Even at 0, different takes can vary. Raise it later, deliberately, when the user wants stranger hybrids.

Suno documents no intermediate stops, no per-model defaults, and no numeric scale beyond "reduce to 0". Several community guides now report the same five stops, Off ("Exact style"), Normal, High, Extra, and Max, with Normal the default on `v6`, `v6-mini`, and Custom Models and Off the default on `v6-wild`. One tester (2026-10-22, 27 renders, 54 takes) reports that at Off the pasted Style survived word for word on 52 of 54 takes, while at Normal it was rewritten on every take. Treat this as consistent community evidence, not documentation, and read the user's own slider. Because Normal is the reported default on `v6`, assume an untouched slider is rewriting the prompt.

### Ranges

The ranges below are skill heuristics, not official presets or measured success rates. Start from the user's current settings when troubleshooting. Use these for a fresh request only when settings help.

| Goal | Weirdness | Style Influence | Variety | Tradeoff |
| --- | --- | --- | --- | --- |
| Calibrating a new brief | 20-40% | 80-95% | 0 | Establishes what the prompt actually does before anything is loosened |
| Balanced exploration | 35-50% | 60-80% | 0, or raise if exposed | Room for variation within the brief |
| Experimental but directed | 50-70% | 60-85% | Raise if exposed | More surprising results to compare |
| Deliberately loose exploration | 70-100% | 20-60% | High or above | Higher risk of drift and unusable takes |

Reported failure edges: Weirdness below about 20 can sound stale, and 90 or above tends toward artifacts. Testers suggest Style Influence of roughly 65-95% with Weirdness under 50% when a precise brief is being ignored. These are field notes, not thresholds.

Calibrate first, then loosen. A clearly described hybrid at moderate Weirdness usually holds together better than a vague prompt at high Weirdness. If lowering Weirdness makes the output break down, return to the last working setting and compare with the same prompt and model; do not continue lowering it as a stability fix.

Choose by desired predictability, not a rule that a genre must have a certain number. A sparse ambient bed may need conservative settings; a bluegrass murder ballad may deliberately seek unusual production.

### Vocal Gender

[Vocal Gender](https://help.suno.com/en/articles/10153473) is a dropdown under the advanced options with two documented values, Male and Female. No third or neutral value is documented. It steers the singer; it does not select a Voice, and it does not replace delivery direction in Style. Leave it unset when the brief does not call for a specific vocal, and never use it to substitute for describing register, texture, and phrasing.

### Audio Influence And Uploads

Only recommend Audio Influence when an upload or the selected workflow exposes it. Ask what must survive from the reference: melody, groove, phrasing, or texture. Start with the user's displayed setting; compare a modest increase when the source identity is lost, or a decrease when it over-constrains the new direction. Do not invent one universal percentage for every reference.

Keep the source clip and other controls fixed while comparing. A selected Voice, a text persona, and an audio reference serve different purposes; none is an exact-match guarantee.

## Max Mode

Max Mode is an Advanced toggle that spends more credits per generation in exchange for consistency and fidelity. The [v6 FAQ](https://help.suno.com/en/articles/13924481) names its cases: songs past the short end of the range, covers that must stay close to the source, style transfer between songs, and holding vocals and style steady across a full track. Community reports put the cost at double (20 credits per two-song generation instead of 10), which halves a Pro plan's song count; treat the multiplier as reported and the direction as certain. Suno reportedly recommends Max Mode when a Voice is selected; its Voices article separately advises a high Audio Influence.

Leave it off while calibrating a brief. Getting standard v6 to follow the prompt is a prompt problem, and paying double to discover that wastes credits. Turn it on once the direction is right and the remaining fault is consistency or fidelity. A baseline generation is two songs for 10 credits; image and video inputs add cost.

## Duration And Precision

Write to the requested time using the bar budget in `song-matrix.md`. All v6 variants generate up to 8 minutes in one pass. Where the user's UI exposes Duration, use its visible range; a 0:10 to 6:00 Custom setting is a reported observation, not a limit verified here. Those figures describe generation length, not a promise of an exact cut.

Leave Auto when there is no target length. For a target cut, budget phrases, rests, and ending space before generation. A little headroom may help if the user will trim, but extra seconds do not guarantee resolution. `[End]` and `[Fade Out]` request an ending; audition and Crop or edit for exact timing. Give the final lyric somewhere to land after it, as described in `v6-production-direction.md`. For a very short individual hit, consider Sounds; a short melodic cue remains an instrumental task.

Tempo, key, chord progressions, bar counts, and specific vocalist hand-offs in text are intentions to check by listening. When exact notes or rhythm matter, consider a supplied audio/MIDI reference or a Studio edit instead of adding more prompt adjectives.

## Personalization

Suno separates [Voices](https://help.suno.com/en/articles/11362369), [Custom Models](https://help.suno.com/en/articles/11362497), and [My Taste](https://help.suno.com/en/articles/11362561). Voices and Style Personas are one surface: Style Personas sits in the Voices menu and opens `Create a Voice` (Beta), taking a recorded or uploaded sample, with converted older Personas reachable through `Select from library`. See `personas.md`. Keep the selected Voice's identity separate from delivery directions such as restrained, whispered, or belted. A text instruction does not select or train a Voice. Custom Models provide a personalized model basis and now run on v6; existing models were carried over, so keep the requested song direction coherent with the model rather than assuming its earlier behavior. Suno's [what's new in v6](https://help.suno.com/en/articles/13924801) says Custom Models "fine-tune v6 on your own tracks", and the FAQ says older custom models were upgraded automatically so v6 powers them. The [Custom Models article](https://help.suno.com/en/articles/11362497) gives Pro and Premier access, up to three models, at least six songs the user owns the rights to, about 2-5 minutes to build, and creation from `Create Custom Model` in the model dropdown. It still calls them private, but the 2026-10-15 [release notes](https://suno.com/release-notes) added shareable custom models with 2x the inputs for Premier users, alongside team workspaces for Pro and Premier; follow the newer release note and confirm on the user's screen. A 100-credit creation cost and a 24-song suggestion are community reports only. With a Custom Model selected, prompt around the song's intent and avoid piles of conflicting genre tags.

My Taste personalizes the Magic Wand, the icon at the top right of the Styles box that writes a detailed style description from the user's listening and creation habits. It is on by default and can be viewed, edited, or disabled from the account menu. For comparisons, retain the exact final Style text rather than invoking the wand again between takes, and hold Variety at 0 so the retained text survives. If suggestions repeatedly pull toward a familiar palette, review personalization settings and rewrite the direction deliberately.

## Moderation And Troubleshooting

Suno's [moderation guide](https://help.suno.com/en/articles/3198209) says generation may be prevented by well-known names, protected terms, derogatory language, excessive profanity, or other inappropriate content. A bland take alone is not evidence of a hidden filter. Use the actual error or warning when diagnosing a rejection and explain any proposed wording change.

| Observation | First Step |
| --- | --- |
| Explicit moderation error | Inspect the flagged wording and propose a compatible revision |
| Styles ignored | Set Variety to 0, remove conflicting directions, front-load the defining sound, then compare Style Influence |
| Two takes differ more than the prompt edit | Set Variety to 0 in the Advanced tab and hold other controls fixed; listen to both takes and compare across at least two generations before crediting the edit |
| Rushed, flat, or spoken-sounding vocal | Check the rendered tempo first, then reduce lyric density for the section or give it more time; see `v6-production-direction.md` |
| Sections skipped or lyrics repeated in a long song | Trim the lyric toward the time budget, then repair the span with Replace Section or a plain-language edit rather than re-rolling |
| Old v5.5 recipe sounds wrong | Rebuild from the song's intent in connected musical language; do not port tag stacks verbatim |
| Generic but valid take | Add one defining groove, instrument, or arrangement gesture |
| Chaotic take | Simplify the prompt or lower Weirdness; compare separately |
| Unwanted sound | Add a focused Exclude item if available; audition again |
| Random instruments appear | Lower Variety, lower Weirdness, raise Style Influence, and name the intended instrumentation |
| Mumbled lyric | Simplify stressed phrases and replace the affected section |
| Extra ending material | Request closure with `[End]`; trim an unwanted tail or edit an internal span |
| Song ends mid-lyric | Add an instrumental section after the final vocal section as a buffer; see `v6-production-direction.md` |
| Verses lose the band | State the verse energy and instrument activity explicitly; see `v6-production-direction.md` |
| Mix is muddy, distant, or uneven | Add a short production clause naming the wanted result; see `v6-production-direction.md` |
| Chorus fails to lift | Change phrase density or arrangement contrast before slider tuning |
| Identity drifts | Check selected Voice/reference and conflicting descriptions; confirm Variety is at 0 |

Change one variable at a time. See `studio-and-iteration.md` for take logs, stopping criteria, and edits that preserve a good performance.
