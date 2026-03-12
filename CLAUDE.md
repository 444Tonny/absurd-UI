# Funny UI — Project Context

## Concept

A collection of web UI components that are **visually indistinguishable from a real interface** but **unnecessarily absurd to interact with**.

The joke is the contrast: it looks like something you'd find in a real settings panel or a SaaS product, but the interaction mechanic is completely ridiculous.

## Page Context Rule

Each component file is **not just the component** — it's a full fake page that makes the component feel natural and expected. The component is embedded inside a realistic fake web page that gives it context.

- The fake page should look like a real site (video player, settings page, checkout, etc.)
- The absurd component is triggered the same way the real one would be (click the volume icon → popup)
- The rest of the page is convincing filler: fake titles, fake content, fake UI chrome
- A well-placed fake comment or UI hint can quietly acknowledge the absurdity (see: `@just_vibing_here`)

## Design Philosophy

**Look like real UI.**
Every component should feel like it belongs in a modern web app (think settings page, dashboard, onboarding flow). Rounded card, clean label, subtle shadow, system font. A stranger should glance at it and think "oh, a volume control" — then realize they have to catapult a ball to use it.

**The absurdity is in the mechanic, not the visual.**
No game aesthetics. No pixel fonts. No scoreboards. No "POWER: 80%" bars. The canvas/interaction area sits inside the card like a normal input would. The label, the value, the layout — all of it should look native.

**Keep it tight.**
Components are compact. Not full-screen experiences. Think: a card you'd embed in a settings sidebar, not a standalone app.

## Visual Rules

- Font: `system-ui, sans-serif`
- Page background: `#f3f4f6`
- Container: white card, `border-radius: 12px`, subtle `box-shadow`, `padding: 24px`
- No game colors, no dramatic glows, no score-style typography

## Component Template Structure

```
[Title]            ← centered, 20px, font-weight 500, margin-bottom 20px
                     can be playful in wording (e.g. "CHOOSE YOUR VOLUME...")
[Interaction area] ← canvas or mechanic, full width, rounded border, #f9fafb bg
[Footer]           ← left: "Label: value" (15px, value bold 20px) | right: "Reset" link
```

- Value starts at a sensible default (e.g. `0%`), not a dash
- "Reset" is grayed out until the user has interacted, then becomes clickable
- No hint/subtitle text — the mechanic should be self-evident (or discoverable)

## Tech Stack

- Vanilla HTML + CSS + JavaScript only
- No frameworks, no libraries
- One `.html` file per component

## File Structure

```
/
├── CLAUDE.md
├── index.html              ← gallery (later)
└── components/
    ├── volume1.html        ← slingshot volume
    └── ...
```

## Tone & Copy

**Error messages, success states, labels, and any incidental text should be humorous whenever possible.**
This is not a real product — lean into it. Absurd error messages, fake-serious warnings, broken Franglais, over-confident success toasts, passive-aggressive validation — all fair game.

- Error: don't say "Invalid input." Say something like "Numéro de téléphone introuvable. Please, recommencer."
- Success: don't say "Done!" Say "Félicitations, we think."
- Labels can be slightly off ("Secondary phone number (in case we lose the first one)")
- The copy should feel like a parody of a real UI, not a real UI

The visual design stays professional. The words do not have to.

## Rules

1. The mechanic is the joke — not the visual design
2. Must look like a real UI component at first glance
3. Must actually output a real value
4. Compact — no full-screen game layouts
5. All text must be at minimum **15px** font size — this is a hard floor. Titles and subtitles should be even larger (18px+). The only exceptions are purely decorative/branding micro-text (e.g. fake reCAPTCHA "Privacy · Terms") that must stay small to look authentic.
