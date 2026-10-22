# Style 1: editorial explainer reel (default house style)

This is the default look for every video made with this kit unless the user
asks for something else. It was measured from `reference.mp4` in this folder:
a 79-second vertical psychology explainer. The reference video, contact sheets
and frames stay local (gitignored); this file is the shareable description.

Re-measure anytime with:

```sh
node .claude/skills/motion-showreel/scripts/analyze-reference.mjs \
  style-references/style_1/reference.mp4 style-references/style_1/analysis --fps 1
```

## Format

- Vertical 9:16, build at 1080x1920 (reference is 720x1280, 23.976 fps).
- One talking-head angle, locked off, medium shot, warm muted room. No jump-zoom
  punch-ins; the energy comes from typography and full-screen diagrams.
- Length 60 to 90 seconds. Calm, educational pacing: let sentences finish.

## Structure (reference timings)

| Time | Section |
| --- | --- |
| 0.0 to 1.8 s | Series title card over the speaker: "FRIENDSHIP / PSYCHOLOGY", small italic "series" and "#051". |
| 1.8 to 7 s | Hook on camera with captions and one or two giant keywords. |
| 7 to 29 s | Full-screen diagram explainer on off-white (speaker voice continues underneath). |
| 29 to 41 s | Back on camera; one diagram strip takes over the top third. |
| 41 to 63 s | Second full-screen explainer: a named theory and a named expert. |
| 63 to 79 s | On camera: big keyword payoffs, then the series card returns as the outro and a spoken follow call. |

Roughly half the runtime is full-screen graphics. Alternate camera and diagram
blocks of 10 to 20 seconds rather than flashing graphics briefly. Hard cuts
between blocks; inside the diagram world, transitions are wipes where a white
panel slides down over the top of the frame and expands.

## Color

| Token | Hex | Use |
| --- | --- | --- |
| `--paper` | `#F7F7F7` (up to `#FBFBFB`) | Diagram background, very faint horizontal grain |
| `--ink` | `#111111` | People dots, outlines, body text on paper |
| `--headline-red` | `#8A1208` | Giant condensed keywords and theory titles |
| `--accent-red` | `#E92828` | "You" node, label pills, connection lines, alert badges |
| `--blush` | `#F6C9C9` | Soft pill labels and highlighted zones (accent red at about 25%) |
| `--tan` | `#946B41` | Name plates, "resources" coins, warm secondary objects |
| `--grey` | `#BDBDBD` | Lost, faded or distant people |
| `--caption-white` | `#FFFFFF` | Captions over footage, with a soft shadow |

## Typography

- **Keywords and titles:** an ultra-condensed heavy grotesque, all caps, tight
  leading (0.85), in `--headline-red`. Free match: **Anton** (Google Fonts).
  Keywords fill about 85% of frame width.
- **Captions, lead-ins and labels:** a high-contrast **italic serif**, sentence
  case. Free match: **Instrument Serif Italic** or Playfair Display Italic.
- Never use a sans for captions. Never use more than these two families.

## Captions

- Word-by-word build: words appear as spoken and stay until the phrase ends;
  one short phrase (2 to 6 words) at a time. No karaoke color highlight.
- **Normal position:** centered at about 70% of frame height, chest level,
  about 28 px at 720 wide (about 42 px at 1080 wide), white with soft shadow.
- **Keyword mode:** when a key word lands, the phrase moves to the top left
  (about 12% from top) as a small italic lead-in, and the keyword appears below
  it as giant red condensed caps. The rest of the phrase continues in small
  italic, right-aligned under or beside the keyword. Example: "This isn't
  about being" / **ANTISOCIAL**; "your brain" / **GENERALIZED** / "the risk".
- Use one keyword about every 5 to 10 seconds of on-camera speech.

## Diagram language (full-screen paper scenes)

- The viewer is a red pill/ellipse labeled "*You*" in white italic serif,
  usually centered.
- Other people are solid black ellipses; small clusters of three mean a group.
- Lost or faded people turn grey, then dashed outlines, then vanish.
- Relationships are thin lines: dashed black for weak or distant, solid red for
  strong. Rings of dashed lines show a circle of people; a red dashed ring shows
  who you let close.
- Labels are small italic pills: red fill with white text for the key idea,
  white fill with black outline for neutral notes, blush fill with dark red
  text for soft context.
- Emotion icons: a red spiky starburst behind "You" for a strong reaction, a
  red lightning zig-zag for a trigger, small red "!" badges on threats, a
  padlock on a protective circle.
- Concrete metaphors drawn as flat outlined objects (for example a jar of tan
  coins for limited resources) that tip, empty or get a red lid.
- Every diagram builds one element at a time, on the spoken word that names it,
  and keeps earlier elements on screen so the idea accumulates.

## Expert and theory introductions

- A full-width grey band across the upper third with a black-and-white cutout
  portrait in front of a red circle.
- "*Psychologist*" (or role) in italic serif above the band; the name in a tan
  plate with white italic serif text at the portrait's base.
- The concept name appears below in giant red condensed caps, with an outlined
  italic pill underneath for the source (for example "fear conditioning research").
- Afterwards the theory title shrinks to a header at the top and the diagram
  builds beneath it.

## Motion

- Elements pop in with a short scale-up (0.25 to 0.35 s, ease "back.out(1.6)")
  and settle; nothing floats or loops.
- Lines draw on from their source; dashed rings rotate slowly at most.
- Removals fade to grey, then out. Keep motion calm; this is not sizzle pacing.

## Sound

- Spoken voice is the lead and is always clear.
- Light music bed under the whole piece, well below the voice.
- Soft pops or clicks on diagram element entries; a gentle whoosh on wipes.
  The `media-use` skill's bundled sound effects (pop, click-soft, whoosh-short)
  cover this for free.

## Branding

- Each video is an episode of a named series with a number (`#051`): the series
  card opens and closes the video, and the speaker closes with a follow call.
  Ask the user for their series name and episode number.
