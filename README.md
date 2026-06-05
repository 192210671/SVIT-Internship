SMART AI MOCK INTERVIEW — MASTER DESIGN SYSTEM
### Version 3.0 · Carbon Interface · Senior Frontend Specification · Production Grade

---

> **Design Philosophy: "Carbon Interface"**
> A precision-engineered dark UI built for cognitive performance under pressure. Inspired by aerospace HUDs, pro-grade terminals, and tactile glass instrumentation. Every surface is a deliberate instrument — deep voids of black, surgical zinc tones, crystalline glassmorphism layers, and chromatic gradient accents that signal intent before you read the label. The interface doesn't compete for attention; it *amplifies* the user's focus.
>
> **Core Principles:** Depth through darkness · Gradients as language · Typography as hierarchy · Motion as feedback

---

## PART I — FOUNDATION SYSTEM

---

## 1. DESIGN TOKENS & COLOR SYSTEM

### 1.1 Background Scale

The depth model uses color alone (no shadows) to create spatial layers. Darker = deeper. Never invert this.

```
╔══════════════════════════════════════════════════════════════════╗
║  BACKGROUND DEPTH SCALE  (Deepest → Surface)                    ║
╠══════════════════════════════════════════════════════════════════╣
║  bg-void        #020306   Page root / absolute floor            ║
║  bg-base        #09090B   Screen background (Zinc-950)          ║
║  bg-surface     #0F1117   Card base, inset sections             ║
║  bg-elevated    #18181B   Raised cards, list items (Zinc-900)   ║
║  bg-overlay     #1C1C21   Modals, drawers, popovers             ║
║  bg-muted       #27272A   Disabled fills, dividers (Zinc-800)   ║
║  bg-subtle      #3F3F46   Hover fills, strong borders (Zinc-700)║
╚══════════════════════════════════════════════════════════════════╝

Rule: bg-surface sits INSIDE bg-elevated. bg-elevated sits INSIDE bg-overlay.
Never use a lighter background color on a deeper layer.
```

### 1.2 Text Scale

```
╔══════════════════════════════════════════════════════════════════╗
║  TEXT SCALE                                                      ║
╠══════════════════════════════════════════════════════════════════╣
║  text-primary    #FAFAFA   Headlines, labels (Zinc-50)          ║
║  text-secondary  #A1A1AA   Body, descriptions (Zinc-400)        ║
║  text-muted      #71717A   Placeholders, metadata (Zinc-500)    ║
║  text-disabled   #3F3F46   Disabled states (Zinc-700)           ║
║  text-inverse    #09090B   Text on light accent backgrounds     ║
╚══════════════════════════════════════════════════════════════════╝
```

### 1.3 Border Scale

```
╔══════════════════════════════════════════════════════════════════╗
║  BORDER SCALE                                                    ║
╠══════════════════════════════════════════════════════════════════╣
║  border-ghost    #111116   Invisible dividers, structural lines  ║
║  border-subtle   #1A1A1F   Whisper separators, inactive zones   ║
║  border-default  #27272A   Standard card borders (Zinc-800)     ║
║  border-strong   #3F3F46   Focused inputs, selected (Zinc-700)  ║
║  border-accent   #52525B   Active/pressed borders (Zinc-600)    ║
╚══════════════════════════════════════════════════════════════════╝
```

### 1.4 Slate Overlay Scale (surfaces with blue undertone)

```
slate-950    #020817    Deep blue-black alternative root
slate-900    #0F172A    Alternative deep surface
slate-800    #1E293B    Cards with slate tint
slate-700    #334155    Section dividers
slate-600    #475569    Muted elements on slate
slate-500    #64748B    Mid-tone on slate surfaces
slate-400    #94A3B8    Secondary text on slate
slate-300    #CBD5E1    Highlighted text on slate
```

---

### 1.5 Gradient System — Enhanced

Every module has a **primary**, **hover**, and **muted** gradient variant. Never use flat accent colors — always gradients. Gradients signal module identity at a glance.

```
═══════════════════════════════════════════════════════════════════
SYSTEM GRADIENTS
═══════════════════════════════════════════════════════════════════

--grad-primary
  linear-gradient(135deg, #3B82F6 0%, #1D4ED8 100%)
  → Default CTA, general-purpose primary accent

--grad-electric
  linear-gradient(135deg, #60A5FA 0%, #2563EB 50%, #1E40AF 100%)
  → High-energy primary buttons, FABs, key interactions

--grad-electric-hover
  linear-gradient(135deg, #93C5FD 0%, #3B82F6 50%, #1D4ED8 100%)
  → Electric gradient hover state (brighter)

--grad-deep-space
  linear-gradient(135deg, #0F0C29 0%, #302B63 50%, #24243E 100%)
  → Ambient background mesh overlays at very low opacity

═══════════════════════════════════════════════════════════════════
MODULE IDENTITY GRADIENTS — Primary / Hover / Muted
═══════════════════════════════════════════════════════════════════

AUTH MODULE
  --grad-auth           linear-gradient(135deg, #3B82F6 0%, #8B5CF6 100%)
  --grad-auth-hover     linear-gradient(135deg, #60A5FA 0%, #A78BFA 100%)
  --grad-auth-muted     linear-gradient(135deg, rgba(59,130,246,0.15) 0%, rgba(139,92,246,0.15) 100%)
  → Electric blue bleeding into violet. Trust, intelligence, entry.

AI INTERVIEW MODULE
  --grad-interview      linear-gradient(135deg, #6366F1 0%, #4F46E5 50%, #3730A3 100%)
  --grad-interview-hover linear-gradient(135deg, #818CF8 0%, #6366F1 50%, #4F46E5 100%)
  --grad-interview-muted linear-gradient(135deg, rgba(99,102,241,0.15) 0%, rgba(55,48,163,0.15) 100%)
  → Deep indigo. Focus, intelligence, depth.

VIDEO INTERVIEW MODULE
  --grad-video          linear-gradient(135deg, #8B5CF6 0%, #7C3AED 50%, #6D28D9 100%)
  --grad-video-hover    linear-gradient(135deg, #A78BFA 0%, #8B5CF6 50%, #7C3AED 100%)
  --grad-video-muted    linear-gradient(135deg, rgba(139,92,246,0.15) 0%, rgba(109,40,217,0.15) 100%)
  → Rich violet. Presence, performance, confidence.

RESUME MODULE
  --grad-resume         linear-gradient(135deg, #0EA5E9 0%, #0284C7 50%, #0369A1 100%)
  --grad-resume-hover   linear-gradient(135deg, #38BDF8 0%, #0EA5E9 50%, #0284C7 100%)
  --grad-resume-muted   linear-gradient(135deg, rgba(14,165,233,0.15) 0%, rgba(3,105,161,0.15) 100%)
  → Cyan-to-ocean blue. Clarity, professionalism, structure.

QUIZ MODULE
  --grad-quiz           linear-gradient(135deg, #10B981 0%, #059669 50%, #047857 100%)
  --grad-quiz-hover     linear-gradient(135deg, #34D399 0%, #10B981 50%, #059669 100%)
  --grad-quiz-muted     linear-gradient(135deg, rgba(16,185,129,0.15) 0%, rgba(4,120,87,0.15) 100%)
  → Emerald. Growth, knowledge, achievement.

JOBS MODULE
  --grad-jobs           linear-gradient(135deg, #F59E0B 0%, #D97706 50%, #B45309 100%)
  --grad-jobs-hover     linear-gradient(135deg, #FCD34D 0%, #F59E0B 50%, #D97706 100%)
  --grad-jobs-muted     linear-gradient(135deg, rgba(245,158,11,0.15) 0%, rgba(180,83,9,0.15) 100%)
  → Amber. Opportunity, energy, aspiration.

SESSIONS / ANALYTICS MODULE
  --grad-sessions       linear-gradient(135deg, #F97316 0%, #EA580C 50%, #C2410C 100%)
  --grad-sessions-hover linear-gradient(135deg, #FB923C 0%, #F97316 50%, #EA580C 100%)
  --grad-sessions-muted linear-gradient(135deg, rgba(249,115,22,0.15) 0%, rgba(194,65,12,0.15) 100%)
  → Orange. Achievement, progress, momentum.

PROFILE MODULE
  --grad-profile        linear-gradient(135deg, #64748B 0%, #475569 50%, #334155 100%)
  --grad-profile-hover  linear-gradient(135deg, #94A3B8 0%, #64748B 50%, #475569 100%)
  --grad-profile-muted  linear-gradient(135deg, rgba(100,116,139,0.15) 0%, rgba(51,65,85,0.15) 100%)
  → Slate. Neutral, stable, personal.

═══════════════════════════════════════════════════════════════════
SCORE / STATUS GRADIENTS
═══════════════════════════════════════════════════════════════════

--grad-score-excellent  linear-gradient(135deg, #10B981 0%, #059669 100%)   → 90–100%
--grad-score-high       linear-gradient(135deg, #34D399 0%, #10B981 100%)   → 80–89%
--grad-score-mid        linear-gradient(135deg, #3B82F6 0%, #1D4ED8 100%)   → 60–79%
--grad-score-low        linear-gradient(135deg, #F97316 0%, #EA580C 100%)   → 40–59%
--grad-score-fail       linear-gradient(135deg, #EF4444 0%, #DC2626 100%)   → 0–39%

═══════════════════════════════════════════════════════════════════
SURFACE / GLASS GRADIENTS
═══════════════════════════════════════════════════════════════════

--grad-glass-subtle     linear-gradient(135deg, rgba(255,255,255,0.03) 0%, rgba(255,255,255,0.01) 100%)
--grad-glass-card       linear-gradient(145deg, rgba(255,255,255,0.055) 0%, rgba(0,0,0,0.18) 100%)
--grad-glass-strong     linear-gradient(145deg, rgba(255,255,255,0.08) 0%, rgba(0,0,0,0.3) 100%)
--grad-noise            SVG feTurbulence noise at 3% opacity over all elevated cards
--grad-mesh-ambient     3 blurred radial gradients composited:
                          top-right:   radial(#3B82F6, transparent) at 8% opacity
                          center-left: radial(#6366F1, transparent) at 5% opacity
                          bottom:      radial(#09090B, #030507) at 100% opacity
```

---

### 1.6 Badge & Chip Color Tokens

```
DIFFICULTY BADGES
──────────────────────────────────────
Easy    bg: rgba(16,185,129,0.12)  text: #10B981  border: rgba(16,185,129,0.28)
Medium  bg: rgba(59,130,246,0.12)  text: #60A5FA  border: rgba(59,130,246,0.28)
Hard    bg: rgba(249,115,22,0.12)  text: #FB923C  border: rgba(249,115,22,0.28)
Expert  bg: rgba(239,68,68,0.12)   text: #F87171  border: rgba(239,68,68,0.28)

QUESTION TYPE BADGES
──────────────────────────────────────
Technical      bg: rgba(99,102,241,0.12)  text: #818CF8  border: rgba(99,102,241,0.28)
Behavioral     bg: rgba(236,72,153,0.12)  text: #F472B6  border: rgba(236,72,153,0.28)
System Design  bg: rgba(14,165,233,0.12)  text: #38BDF8  border: rgba(14,165,233,0.28)
HR Round       bg: rgba(168,85,247,0.12)  text: #C084FC  border: rgba(168,85,247,0.28)
Mixed          bg: rgba(100,116,139,0.12) text: #94A3B8  border: rgba(100,116,139,0.28)

SKILL LEVEL CHIPS
──────────────────────────────────────
Beginner       bg: #1C1C21                   text: #71717A    border: #27272A
Intermediate   bg: rgba(59,130,246,0.09)     text: #93C5FD    border: rgba(59,130,246,0.22)
Advanced       bg: rgba(99,102,241,0.09)     text: #A5B4FC    border: rgba(99,102,241,0.22)
Expert         bg: rgba(250,204,21,0.09)     text: #FDE047    border: rgba(250,204,21,0.22)

EMOTION TAGS (video analysis)
──────────────────────────────────────
Confident   grad: linear-gradient(135deg, #10B981 0%, #059669 100%)
Nervous     grad: linear-gradient(135deg, #F97316 0%, #EA580C 100%)
Happy       grad: linear-gradient(135deg, #F59E0B 0%, #D97706 100%)
Neutral     grad: linear-gradient(135deg, #6366F1 0%, #4F46E5 100%)
Stressed    grad: linear-gradient(135deg, #EF4444 0%, #DC2626 100%)
Focused     grad: linear-gradient(135deg, #0EA5E9 0%, #0284C7 100%)

MATCH CHIPS (jobs)
──────────────────────────────────────
Matched     bg: rgba(16,185,129,0.1) text: #10B981 border: rgba(16,185,129,0.28) icon: check 10dp
Missing     bg: rgba(239,68,68,0.1)  text: #F87171 border: rgba(239,68,68,0.28)  icon: x-circle 10dp

LEADERBOARD PODIUM
──────────────────────────────────────
Gold (#1)   bg: rgba(250,204,21,0.10)  border: rgba(250,204,21,0.32)  text: #FDE047
            glow: 0 0 24px rgba(250,204,21,0.22), 0 0 48px rgba(250,204,21,0.10)
Silver (#2) bg: rgba(148,163,184,0.10) border: rgba(148,163,184,0.32) text: #CBD5E1
            glow: 0 0 18px rgba(148,163,184,0.18)
Bronze (#3) bg: rgba(180,83,9,0.10)    border: rgba(180,83,9,0.32)    text: #FDBA74
            glow: 0 0 18px rgba(180,83,9,0.18)
```

---

## 2. TYPOGRAPHY SYSTEM

```
╔══════════════════════════════════════════════════════════════════╗
║  FONT STACK                                                      ║
╠══════════════════════════════════════════════════════════════════╣
║  Display / Headings    "DM Sans"        sans-serif               ║
║    → Bold, geometric, confident at large scale.                  ║
║                                                                  ║
║  Body / UI             "IBM Plex Sans"  sans-serif               ║
║    → Technical clarity. Legible at small sizes. Data-first.      ║
║                                                                  ║
║  Monospace / Code      "IBM Plex Mono"  monospace                ║
║    → Timers, scores, IDs, code blocks, counters.                 ║
║                                                                  ║
║  Numbers / Stats       "DM Mono"        monospace                ║
║    → KPI values, percentages, all numeric readouts.              ║
║    → Always tabular-nums feature for visual stability.           ║
╚══════════════════════════════════════════════════════════════════╝

TYPOGRAPHIC SCALE
─────────────────────────────────────────────────────────────────
Name         Size  Font          Weight  Tracking     Use
─────────────────────────────────────────────────────────────────
Display-XL   52sp  DM Sans       800     -0.030em     App name, splash hero
Display-L    40sp  DM Sans       700     -0.025em     Screen cover titles
Display-M    32sp  DM Sans       700     -0.020em     Report hero headlines
Headline-L   28sp  DM Sans       600     -0.015em     Section headers
Headline-M   22sp  DM Sans       600     -0.010em     Card titles
Headline-S   18sp  IBM Plex Sans 600     -0.005em     List titles
Body-L       16sp  IBM Plex Sans 400     0em          Main body, line-h: 1.6
Body-M       14sp  IBM Plex Sans 400     0em          Secondary, line-h: 1.5
Body-S       13sp  IBM Plex Sans 400     0em          Metadata, line-h: 1.4
Label-L      13sp  IBM Plex Sans 500     +0.020em     Chip labels, form labels
Label-M      11sp  IBM Plex Sans 500     +0.040em     Badge text, UPPERCASE tags
Label-XS     10sp  IBM Plex Sans 500     +0.060em     Nav labels, UPPERCASE nav
Mono-L       15sp  IBM Plex Mono 400     0em          Score values, timers
Mono-M       13sp  IBM Plex Mono 400     0em          IDs, session codes
Mono-S       11sp  IBM Plex Mono 400     0em          Dense metric values
Number-XL    48sp  DM Mono       800     -0.020em     Hero KPI (streak, big score)
Number-L     36sp  DM Mono       700     -0.015em     Report score center
Number-M     28sp  DM Mono       700     0em          Stat card values
Number-S     22sp  DM Mono       600     0em          Smaller readouts
─────────────────────────────────────────────────────────────────
```

---

## 3. COMPONENT LIBRARY

### 3.1 Card System — Full Specification

```
BASE CARD
──────────────────────────────────────
Background:    bg-elevated (#18181B)
Inner overlay: grad-glass-card (subtle top-left highlight for depth)
Border:        1px solid border-default (#27272A)
Border-radius: 16dp
Shadow:        0 4px 24px rgba(0,0,0,0.45), 0 1px 4px rgba(0,0,0,0.65)
Padding:       20dp
Noise overlay: SVG feTurbulence at 3% opacity (optional, production)

INTERACTIVE CARD (clickable)
──────────────────────────────────────
Inherits BASE CARD
Press state:
  background  → bg-overlay (#1C1C21)
  border      → border-strong (#3F3F46)
  transform   → scale(0.984)
  transition  → all 150ms cubic-bezier(0.2, 0, 0, 1)
Ripple:       module accent color at 10% opacity, 200ms fade

HERO CARD (module identity cards, section headers)
──────────────────────────────────────
Background:    bg-elevated + [module-gradient-muted] composited
Border:        1px solid [module-color at 18% opacity]
Left-accent:   4dp wide vertical bar at left edge, full height, [module-gradient]
Border-radius: 16dp
Padding:       24dp
Top-right:     48×48dp blurred decorative circle [module-color at 10%]

STAT CARD (KPI / numbers)
──────────────────────────────────────
Background:    bg-surface (#0F1117)
Border:        1px solid border-ghost (#111116)
Top-accent:    2dp gradient bar full width, [module-gradient]
Border-radius: 12dp
Padding:       16dp
Number text:   DM Mono 700 / Number-M / text-primary
Label text:    IBM Plex Sans 500 / Label-M / text-muted / UPPERCASE

GLASS CARD (overlays, modals, bottom sheets)
──────────────────────────────────────
Background:    rgba(14, 14, 18, 0.88)
Backdrop:      blur(28px) saturate(180%)
Border:        1px solid rgba(255,255,255,0.075)
Border-radius: 24dp (or top-only for bottom sheets)
Shadow:        0 24px 64px rgba(0,0,0,0.7)

FEATURE HIGHLIGHT CARD (used in onboarding, promo sections)
──────────────────────────────────────
Background:    bg-surface
Border:        1px solid border-subtle
Left-line:     3dp solid, module gradient, full height
Border-radius: 12dp
Padding:       16dp
Icon zone:     48×48dp, border-radius 12dp, module gradient at 15% bg

DANGER CARD (destructive confirmation)
──────────────────────────────────────
Background:    rgba(239,68,68,0.06)
Border:        1.5px solid rgba(239,68,68,0.28)
Border-radius: 14dp
Left-accent:   4dp solid #EF4444
```

### 3.2 Button System

```
PRIMARY BUTTON
──────────────────────────────────────
Background:    --grad-electric
Height:        52dp
Border-radius: 12dp
Padding:       0 24dp
Text:          IBM Plex Sans 600 / 15sp / #FAFAFA / letter-spacing: +0.01em
Shadow:        0 8px 28px rgba(37,99,235,0.38)
Pressed:       scale(0.968), shadow → 0 4px 14px rgba(37,99,235,0.22)
Hover:         --grad-electric-hover
Loading:       shimmer left-to-right over gradient, 1.2s infinite
Disabled:      bg-muted, text-disabled, no shadow

MODULE-SPECIFIC PRIMARY BUTTON
  Inherits PRIMARY. Replace --grad-electric with module gradient.
  Replace shadow color with module RGB at 0.35 opacity.

SECONDARY BUTTON
──────────────────────────────────────
Background:    transparent
Border:        1.5px solid border-strong (#3F3F46)
Height:        52dp
Border-radius: 12dp
Text:          IBM Plex Sans 500 / 15sp / text-secondary (#A1A1AA)
Pressed:       bg → bg-muted (#27272A), border → border-accent (#52525B)
Focus:         border → #3B82F6, glow 0 0 0 3px rgba(59,130,246,0.12)

GHOST BUTTON
──────────────────────────────────────
Background:    transparent  Border: none  Shadow: none
Text:          IBM Plex Sans 500 / 14sp / text-muted
Pressed:       text → text-primary, underline 1px text-primary

DANGER BUTTON
──────────────────────────────────────
Background:    rgba(239,68,68,0.10)
Border:        1.5px solid rgba(239,68,68,0.32)
Text:          #F87171 / IBM Plex Sans 600 / 15sp
Pressed:       bg → rgba(239,68,68,0.18)
Shadow:        0 4px 16px rgba(239,68,68,0.15) on hover

ICON BUTTON
──────────────────────────────────────
Size:          48×48dp  Border-radius: 14dp
Background:    bg-elevated  Border: 1px solid border-default
Icon:          20dp, text-secondary
Pressed:       bg → bg-muted, icon → text-primary
Active state:  border → [module-color at 40%], icon → module-color

FLOATING ACTION BUTTON (FAB)
──────────────────────────────────────
Size:          56×56dp  Border-radius: 16dp
Background:    --grad-electric
Shadow:        0 8px 36px rgba(37,99,235,0.45)
Icon:          24dp, #FAFAFA
Pressed:       scale(0.94), shadow reduces 40%

SMALL FAB (secondary actions)
──────────────────────────────────────
Size:          44×44dp  Border-radius: 12dp
Background:    bg-elevated  Border: 1px solid border-default
Icon:          18dp, text-secondary
Pressed:       bg-muted
```

### 3.3 Input Fields

```
TEXT INPUT — DEFAULT STATE
──────────────────────────────────────
Background:    bg-surface (#0F1117)
Border:        1.5px solid border-default (#27272A)
Border-radius: 12dp  Height: 56dp  Padding: 0 16dp
Font:          IBM Plex Sans 400 / 15sp / text-primary
Placeholder:   text-muted (#71717A)
Label (floating):
  IBM Plex Sans 500 / 12sp / text-muted / UPPERCASE / letter-spacing: +0.06em
  Resting: center-left inside input at 15sp
  Focused: slides up -20dp, scales 0.82, color → #60A5FA

FOCUSED STATE
──────────────────────────────────────
Border:        1.5px solid #3B82F6
Background:    rgba(59,130,246,0.036)
Label:         #60A5FA
Glow:          0 0 0 3px rgba(59,130,246,0.11)

ERROR STATE
──────────────────────────────────────
Border:        1.5px solid #EF4444
Background:    rgba(239,68,68,0.036)
Helper text:   #F87171 / IBM Plex Sans 400 / 12sp (slides down 4dp on appear)
Glow:          0 0 0 3px rgba(239,68,68,0.11)
Icon trailing: error-circle 16dp, #F87171

SUCCESS STATE
──────────────────────────────────────
Border:        1.5px solid #10B981
Background:    rgba(16,185,129,0.036)
Icon trailing: checkmark 16dp, #10B981
Glow:          0 0 0 3px rgba(16,185,129,0.11)

PASSWORD STRENGTH METER (on registration)
──────────────────────────────────────
Track: 4 segments, 8dp gap, 3dp height each, border-radius: 2dp
Weak (1):    #EF4444  |  Fair (2): #F97316  |  Good (3): #3B82F6  |  Strong (4): #10B981
Label:       IBM Plex Sans 400 / 12sp / [matching segment color]

MULTILINE TEXTAREA
──────────────────────────────────────
Min-height: 120dp  Resize: vertical only
Char counter (bottom-right): DM Mono 400 / 11sp / text-muted
  → >90% capacity: #FB923C  → at 100%: #F87171 (counter pulsates)

SEARCH INPUT
──────────────────────────────────────
Height: 48dp  Border-radius: 12dp
Background: bg-elevated  Border: 1px solid border-default
Leading: search icon 16dp text-muted
Trailing: clear × icon (appears when non-empty), 16dp
Suggestions dropdown: Glass Card, border-radius: 12dp, max 5 rows
  Each row: 48dp, body-M text, left icon 16dp, separator: border-ghost
```

### 3.4 Navigation

```
BOTTOM NAVIGATION BAR
──────────────────────────────────────
Background:      rgba(9,9,11,0.94)
Backdrop-filter: blur(24px) saturate(160%)
Top border:      1px solid border-ghost (#111116)
Height:          72dp + bottom safe area inset
Shadow (upward): 0 -8px 32px rgba(0,0,0,0.55)

INACTIVE ITEM
  Icon:  24dp / text-muted (#71717A)
  Label: IBM Plex Sans 500 / Label-XS / UPPERCASE / text-muted

ACTIVE ITEM
  Icon:  24dp / white (gradient-tinted via ColorFilter)
  Label: IBM Plex Sans 600 / Label-XS / text-primary
  Pill:  40×30dp, border-radius: 10dp
         bg: [module-gradient-muted]
         border: 1px solid [module-color at 22%]
  Animation: spring, stiffness MEDIUM, damping LOW_BOUNCY, 280ms

BADGE (notification)
  8×8dp filled circle, bg: --grad-score-fail
  Position: top-right of icon, offset (-3dp, -3dp)
  Border: 1.5px solid bg-base (to separate from background)

APP BAR / TOOLBAR
──────────────────────────────────────
Background:    bg-base (#09090B)
Border-bottom: 1px solid border-ghost (#111116)
Height:        56dp + status bar inset
Title:         DM Sans 600 / 18sp / text-primary
Back button:   chevron-left 22dp / text-secondary
Action icons:  22dp / text-secondary
Elevation:     0 (no shadow — border-only separation)

SCROLLED STATE
  Background → rgba(9,9,11,0.96)
  Backdrop: blur(20px)
  Border-bottom → border-subtle (#1A1A1F)

COLLAPSING TOOLBAR
  Expanded background: gradient from bg-surface (top) → bg-base (bottom)
  Collapse transition: title fades in as hero fades out, 200ms cross-fade
  Sticky threshold: 20dp before fully collapsed
```

### 3.5 Chips & Tags

```
STANDARD CHIP
  Height: 30dp  Padding: 0 12dp  Border-radius: 8dp
  Font: IBM Plex Sans 500 / Label-M
  bg: bg-muted (#27272A)  text: text-secondary  border: 1px solid border-default

FILTER CHIP (selectable)
  Unselected: bg-muted / text-muted / border-default
  Selected:   bg: [module-gradient-muted]
              border: 1px solid [module-color at 28%]
              text: [module-accent-text]
              leading: checkmark 12dp
  Transition: background flood-fill ripple 200ms

SKILL CHIP
  Height: 28dp  Padding: 0 10dp  Border-radius: 6dp
  Font: IBM Plex Mono 400 / 12sp (tokens feel)
  Colors: per Skill Level Chips table in §1.6

TAG CHIP (read-only labels)
  Height: 24dp  Padding: 0 8dp  Border-radius: 6dp
  Font: IBM Plex Sans 500 / 11sp
  bg: bg-surface  text: text-muted  border: border-subtle
```

### 3.6 Progress & Loading States

```
LINEAR PROGRESS BAR
  Height: 3dp  bg-track: bg-muted  fill: module gradient
  Border-radius: 2dp  Animation: cubic-bezier(0.4,0,0.2,1) 400ms

THICK PROGRESS BAR (section headers, score bars)
  Height: 6dp  Same as above with 3dp border-radius

CIRCULAR PROGRESS (indeterminate)
  Size: 40dp  Stroke: 3dp  Color: #3B82F6  Track: bg-muted
  Rotation speed: 1.2s linear infinite

SCORE DONUT CHART
  Size: 120dp  Stroke: 10dp  Track: bg-muted
  Fill arc: score gradient (from score-* tokens)
  Center value: DM Mono 700 / 24sp / text-primary
  Outer dashed ring: 1px dashed rgba(255,255,255,0.07), 4dp outset
  Fill animation: 0° → target angle, 1000ms cubic-bezier(0.2,0,0,1)

SHIMMER SKELETON
  Base: bg-surface (#0F1117)
  Wave: linear-gradient(90deg,
    transparent 0%,
    rgba(255,255,255,0.035) 30%,
    rgba(255,255,255,0.07)  50%,
    rgba(255,255,255,0.035) 70%,
    transparent 100%)
  Speed: 1.6s linear infinite, translateX(-100% → 200%)
  Shape: matches exact content element geometry

LOADING OVERLAY (full-screen blocking)
  Background: rgba(2,3,6,0.72) backdrop-blur(6px)
  Spinner: 44dp indeterminate blue
  Label: IBM Plex Sans 400 / 14sp / text-muted
         animated trailing dots (. .. ...)
```

---

## PART II — SCREEN SPECIFICATIONS

---

## 4. AUTH FLOW

---

### 4.1 SPLASH SCREEN

```
FULL SCREEN — bg-void (#020306)
Center-aligned content, vertically at 44% of screen height.

LOGO MARK
  Container:  72×72dp geometric hexagon SVG
  Fill:       --grad-electric (animated gradient cycle, 4s infinite)
  Inner icon: circuit/neural-network hybrid vector, white, 34dp
  Outer glow: radial-gradient from logo center
              #3B82F6 → transparent, 130dp radius, 35% opacity
  Pulse ring: 88dp ring, rgba(59,130,246,0.15), animates scale 1→1.18→1, 2.4s loop

APP NAME
  "Smart AI Interview" — DM Sans 800 / 28sp / text-primary
  Letter-spacing: -0.022em  Gap below logo: 16dp

TAGLINE
  "Interview Smarter. Land Faster." — IBM Plex Sans 400 / 14sp / text-muted
  Gap: 6dp below app name

VERSION LABEL (optional)
  "v2.0" — DM Mono 400 / 11sp / text-disabled / center
  32dp below tagline

LOADING DOTS (20% from bottom)
  3 dots: 8dp circles, bg-subtle (#3F3F46)
  Active dot: bg-white + box-shadow 0 0 8px rgba(59,130,246,0.8)
  Animation: sequential scale 1→1.5→1, stagger 200ms, loop

ENTRY SEQUENCE
──────────────────────────────────────
  0ms     All invisible, bg-void
  180ms   Logo scales 0.55→1.0 + fade 0→1 (spring, 500ms)
  480ms   Logo glow fades 0→full (600ms)
  680ms   Pulse ring appears, starts looping
  750ms   App name slides +10dp→0 + fade (300ms ease-out)
  940ms   Tagline fades in (260ms)
  1180ms  Loading dots appear
  2400ms  Transition → Login (fade) or Home (if authed)
```

---

### 4.2 ONBOARDING SCREENS

```
STRUCTURE — 3-page ViewPager2, full screen, swipe-to-advance.

EACH PAGE LAYOUT
  Upper 56%: Illustration zone (full-bleed, 0 padding)
    Background: radial gradient from page accent at 7% → bg-base
    Lottie animation: 290dp wide, centered, looping gently
  
  Lower 44%: Content zone
    Background: bg-surface (#0F1117)
    Top corners: border-radius 32dp (card rising from bottom)
    Top border: 1px solid border-subtle
    Padding: 32dp horizontal / 28dp top / 32dp bottom

PAGE INDICATOR (inside content zone, top)
  Active: 18dp wide pill, 6dp tall, bg-white, border-radius 3dp
  Inactive: 6×6dp circle, bg: #3F3F46 (Zinc-700)
  Gap: 6dp between dots
  Transition: width animates 6→18dp (spring 300ms)

TEXT BLOCK
  Headline: DM Sans 700 / 28sp / text-primary / line-height: 1.2 / max 2 lines
  Body:     IBM Plex Sans 400 / 15sp / text-secondary / line-height: 1.6 / max 3 lines
  Gap:      20dp between headline and body

FOOTER (persistent, bottom of content zone)
  [Get Started] — Primary button, full width, uses current page gradient
  [I already have an account] — Ghost button, text-muted, 12dp gap above
  Bottom safe area: 24dp

PAGE 1 — "AI Interview"
  Accent gradient: --grad-interview
  Headline: "AI That Knows What Interviewers Want"
  Body: "Practice with questions tailored to your resume and target role. Get real-time AI feedback after every answer."

PAGE 2 — "Video Analysis"
  Accent gradient: --grad-video
  Headline: "See Yourself the Way Interviewers Do"
  Body: "Posture, eye contact, emotion — analyzed frame by frame. Improve faster than any textbook can teach."

PAGE 3 — "Job Matches"
  Accent gradient: --grad-jobs
  Headline: "Roles Built Around Your Actual Skills"
  Body: "Every recommendation is scored against your profile, not just keywords on a page."
```

---

### 4.3 LOGIN SCREEN

```
BACKGROUND
  bg-base + ambient mesh overlay (3 radial blobs):
    top-right:   radial(rgba(59,130,246,0.08), transparent 55%)
    center-left: radial(rgba(99,102,241,0.05), transparent 50%)
    bottom:      solid bg-base fade
  SVG noise texture at 2% opacity

LAYOUT — ScrollView wrapping ConstraintLayout (keyboard avoidance)
Horizontal padding: 32dp

HEADER (64dp from status bar)
  Logo mark: 44×44dp, --grad-auth fill
  "Welcome back." — DM Sans 700 / 36sp / text-primary / tracking: -0.025em
  "Log in to your account." — IBM Plex Sans 400 / 15sp / text-muted
  8dp between lines

FORM (28dp top margin from header)
  Email field
    Leading icon: envelope 16dp, text-muted
    Label: "EMAIL ADDRESS"
  Gap: 16dp
  Password field
    Leading icon: lock 16dp, text-muted
    Trailing: eye/eye-off toggle 16dp, text-muted
  "Forgot password?" — TextButton below password field, right-aligned
    IBM Plex Sans 500 / 13sp / #60A5FA

CTA SECTION (24dp top margin)
  "Sign In" — Primary button, full width, --grad-auth
    Height: 52dp  Border-radius: 12dp
    Shadow: 0 8px 28px rgba(59,130,246,0.32)
  
  OR DIVIDER (16dp margins)
    Two 1px horizontal lines, border-default
    "or continue with" — IBM Plex Sans 400 / 13sp / text-muted (centered)
  
  Google Sign-In button
    Height: 52dp  bg-elevated  border: 1px solid border-default
    Border-radius: 12dp
    Google icon (full-color, 20dp) + "Continue with Google"
    IBM Plex Sans 500 / 15sp / text-primary
    Pressed: bg → bg-muted

FOOTER
  "Don't have an account? " (text-muted) + "Create one" (#60A5FA, weight 500)
  Center-aligned, 24dp from bottom safe area

KEYBOARD AVOIDANCE
  Form scrolls up, header compresses (logo hides, title stays), CTA sticks above keyboard
```

---

### 4.4 REGISTER SCREEN

```
BACKGROUND — Same ambient mesh as Login.

HEADER
  "Create Account" — DM Sans 700 / 32sp / text-primary
  "Start your interview journey." — IBM Plex Sans 400 / 15sp / text-muted

FORM FIELDS (stacked, 16dp gaps)
  Full Name     → leading: user icon
  Email         → leading: envelope icon
  Password      → leading: lock / trailing: eye toggle + strength meter below
  Confirm Pass  → leading: shield icon + real-time match checkmark/x in trailing

ROLE SELECTOR
  Label: "I AM A..." — Label-L / text-muted / UPPERCASE
  3-chip row (equal width, 8dp gaps):
    Student | Professional | Career Changer
  Chip selected state: --grad-auth-muted bg + colored border
  Unselected: standard chip

TERMS ROW
  Custom checkbox: 20dp / bg-surface / border-default / border-radius: 6dp
  Checked: bg = --grad-primary / border: transparent / white checkmark (path animation)
  Text: IBM Plex Sans 400 / 13sp / text-secondary
  "Terms of Service" + "Privacy Policy" → inline #60A5FA links

CTA
  "Create Account" — Primary button, --grad-auth, full width
  "Sign in instead" — Ghost button, text-muted, centered below, 12dp gap
```

---

### 4.5 OTP VERIFICATION SCREEN

```
BACKGROUND — bg-base
LAYOUT — Center-card design (not full-screen form)

CARD
  bg-elevated / border: border-default / border-radius: 20dp
  Padding: 32dp
  Max-width: 340dp (centered, 32dp side margins)

CARD HEADER
  Icon circle: 64×64dp / bg-surface / border: 2px solid rgba(139,92,246,0.22)
    Inner: shield-check 28dp / --grad-auth gradient fill
  "Verify Your Email" — DM Sans 600 / 24sp / text-primary / center
  "Enter the 6-digit code sent to" — IBM Plex Sans 400 / 14sp / text-muted
  Email address (truncated) — IBM Plex Sans 500 / 14sp / text-primary

OTP BOXES (24dp top margin)
  6 boxes, 8dp gaps, full-width distributed
  Each box: 48×56dp / bg-surface / 1.5px solid border-default / border-radius: 12dp
  Digit: DM Mono 700 / 22sp / text-primary / center

  STATES
    Focused:  border → #3B82F6 / glow: 0 0 0 3px rgba(59,130,246,0.14) / scale: 1.04
    Filled:   border → border-accent (#52525B)
    Error:    border → #EF4444 / bg → rgba(239,68,68,0.05) / shake animation 200ms
    Success:  border → #10B981 / bg → rgba(16,185,129,0.05)
  
  Behavior: auto-advance on digit, auto-submit on 6th digit (200ms delay for UX)
  Backspace: clears current, moves to previous box

RESEND TIMER
  "Resend code in 02:47" — DM Mono 400 / 13sp / text-muted / center
  Expired → "Resend OTP" — IBM Plex Sans 500 / 13sp / #60A5FA / tappable

CTA
  "Verify" — Primary button / --grad-auth / full width inside card
  Auto-triggered on 6th digit if format valid
```

---

### 4.6 FORGOT PASSWORD SCREEN

```
BACKGROUND — bg-base + subtle mesh

CARD (centered, 32dp margins)
  bg-elevated / border: border-default / border-radius: 20dp / padding: 32dp

CONTENT
  Icon: 64×64dp circle / bg-surface / key icon 28dp / --grad-auth fill
  "Reset Password" — DM Sans 600 / 24sp / text-primary
  Description — IBM Plex Sans 400 / 14sp / text-muted / center / 2 lines

  Email TextInput (standard spec)
  
  "Send Reset Link" — Primary button / --grad-auth / full width
  "Back to Login" — Ghost button / centered / text-muted

SENT STATE (replaces form)
  Checkmark circle: 72dp / rgba(16,185,129,0.15) bg / #10B981 border
  Checkmark draws via path animation 400ms
  "Check your inbox." — DM Sans 600 / 20sp / #10B981
  Instruction text: IBM Plex Sans 400 / 14sp / text-muted
  "Resend email" — Ghost button / text-muted
```

---

## 5. HOME MODULE

---

### 4.7 HOME / DASHBOARD SCREEN

```
BACKGROUND — bg-base (#09090B) + ambient mesh overlay

COLLAPSING TOOLBAR (expanded: 200dp → collapsed: 56dp)

  EXPANDED STATE
    Background: gradient from bg-surface (top) → bg-base (bottom)
                + noise texture 2%
    
    LEFT: User info
      Avatar: 52×52dp circle
        bg-surface base / 2px solid bg-base ring / 2px --grad-electric outer ring
        Photo (Glide) or initials: DM Sans 600 / 20sp / text-muted
      "Good morning," — IBM Plex Sans 400 / 13sp / text-muted
      "[First Name]" — DM Sans 600 / 22sp / text-primary
      "[Role · Job Title]" — IBM Plex Sans 400 / 12sp / text-muted
    
    RIGHT: Actions
      Notification bell: icon button 44×44dp
        Badge: 8dp circle / --grad-score-fail bg if unread
      Settings icon: icon button 44×44dp (optional)
  
  COLLAPSED STATE
    "Dashboard" — DM Sans 600 / 18sp / text-primary (center)
    Notification bell (right)

STATS ROW (16dp horizontal padding, 16dp top gap)
  3 Stat Cards in a row, 8dp gaps
  
  Card 1 — Sessions
    Icon: target 16dp / text: #818CF8 (indigo-400)
    Value: Number-M / text-primary
    Label: "SESSIONS" / Label-M / text-muted
    Top accent: --grad-interview (2dp)
  
  Card 2 — Avg Score
    Icon: chart-line 16dp / #60A5FA (blue-400)
    Value: Number-M / [score gradient text color based on value]
    Label: "AVG SCORE"
    Top accent: --grad-primary
  
  Card 3 — Day Streak
    Icon: flame 16dp / #FCD34D (amber-300)
    Value: Number-M / #FCD34D
    Label: "STREAK"
    Top accent: --grad-sessions

QUICK ACTIONS GRID (24dp top, 16dp horizontal)
  Header: "Quick Start" — IBM Plex Sans 600 / 15sp / text-secondary
          "See all →" — right-aligned / 13sp / #60A5FA
  
  2×2 grid, 12dp gaps, 8dp below header

  EACH ACTION CARD
    Size: (screen – 32dp – 12dp) / 2 × auto-height
    Border-radius: 16dp  Padding: 20dp
    Background: bg-elevated + [module-gradient-muted] overlay
    Border: 1px solid [module-color at 14%]
    
    DECORATIVE
      Top-right: 52×52dp blurred circle, module-color 12% opacity
      Left edge: 3dp vertical bar (bottom 50% only), module gradient
    
    CONTENT
      Icon container: 48×48dp / border-radius: 12dp / module gradient 18% bg
        Icon: 26dp SVG, white
      Title: DM Sans 600 / 15sp / text-primary / 12dp top
      Subtitle: IBM Plex Sans 400 / 12sp / text-muted
      Arrow: chevron-right 14dp / text-muted / bottom-right corner
    
    CARDS
      1. "AI Interview"     → --grad-interview  / mic icon
      2. "Video Interview"  → --grad-video       / video-camera icon
      3. "Take a Quiz"      → --grad-quiz        / brain icon
      4. "Browse Jobs"      → --grad-jobs        / briefcase icon

RECENT SESSIONS (24dp top margin)
  Header: "Recent Sessions" / DM Sans 600 / 16sp / text-primary
          "View all" / IBM Plex Sans 500 / 13sp / #60A5FA

  SESSION CARD (list item)
    Layout: horizontal / bg-elevated / border-default / border-radius: 12dp / 16dp padding
    
    LEFT: Module icon in 40×40dp rounded square (bg-surface, module-icon inside)
    
    CENTER (flex):
      Role name: IBM Plex Sans 600 / 14sp / text-primary
      Row: type badge chip + date text (Body-S, text-muted)
    
    RIGHT: Score circle
      44×44dp filled circle / score gradient background
      Score: DM Mono 700 / 14sp / white
      "/100": DM Mono 400 / 10sp / rgba(255,255,255,0.55) below

JOB HIGHLIGHTS (24dp top margin)
  Header: "For You" + "See all jobs →"
  
  Horizontal RecyclerView, snap-to-item, 16dp horizontal padding
  
  JOB CARD (260dp wide × 140dp tall)
    bg-elevated / border-default / border-radius: 14dp
    Top-right: match badge (DM Mono 600 / 12sp / white, score gradient bg)
    Company: IBM Plex Sans 500 / 13sp / text-muted
    Role: DM Sans 600 / 16sp / text-primary (2 lines max)
    Bottom row: salary chip + location chip (bg-muted style, 8dp gap)

NOTIFICATION BADGE COUNT
  If unread > 0: number shows in bell badge
  Bell animation: gentle ring shake on new notification (200ms, 2 cycles)
```

---

## 6. RESUME MODULE

---

### 4.8 RESUME LIST SCREEN

```
BACKGROUND — bg-base

HEADER AREA (16dp padding)
  "My Resumes" — DM Sans 700 / 24sp / text-primary
  Subtitle: "Upload and manage your resumes" / IBM Plex Sans 400 / 14sp / text-muted

RESUME CARD (list item)
  bg-elevated / border-default / border-radius: 14dp / padding: 16dp
  Left-accent: 4dp / --grad-resume
  
  LEFT: Document icon 40×40dp / bg-surface / --grad-resume gradient fill
  
  CENTER:
    Filename: IBM Plex Sans 600 / 14sp / text-primary (truncated 1 line)
    Upload date: IBM Plex Sans 400 / 12sp / text-muted
    Tag chips row: file size + page count (small tags)
  
  RIGHT:
    ATS score donut: 48dp / 5dp stroke / score gradient
    Score: DM Mono 600 / 13sp / text-primary (center)
  
  SWIPE ACTIONS
    Swipe left → Delete (danger red, trash icon)
    Swipe right → Set as Default (blue, star icon)

FAB — "Upload Resume" / bottom-right / --grad-resume gradient / 56dp / border-radius: 16dp

EMPTY STATE
  Illustration: floating document with sparkle animation (Lottie, 180dp)
  "No Resumes Yet" — DM Sans 600 / 20sp / text-primary
  "Upload your first resume to start practicing with AI." — Body-M / text-muted
  "Upload Resume" button — Primary / --grad-resume
```

---

### 4.9 RESUME UPLOAD SCREEN

```
APPBAR — "Upload Resume" + back chevron

UPLOAD DROP ZONE (primary interaction, upper section)
  Container: 16dp horizontal margin
  Shape: border-radius: 20dp
  Border: 2px dashed #3F3F46 (zinc-700)
  Background: bg-surface + --grad-resume at 4% overlay
  Height: 220dp

  CENTER CONTENT
    Icon container: 72×72dp / bg-elevated / border: border-default / border-radius: 18dp
      PDF icon: 32dp / --grad-resume gradient fill
    "Drop your PDF here" — DM Sans 600 / 18sp / text-primary (16dp top)
    "or" — IBM Plex Sans 400 / 13sp / text-muted (8dp)
    "Browse files" — IBM Plex Sans 500 / 14sp / #38BDF8
    "PDF only · Max 10 MB" — Label-M / text-disabled

  DRAG-ACTIVE STATE
    Border: 2px dashed #0EA5E9 (solid glow pulse)
    Background: rgba(14,165,233,0.055)
    Box glow: 0 0 0 4px rgba(14,165,233,0.12), 0 0 32px rgba(14,165,233,0.08)
    Icon: scale 1→1.08→1 pulse 600ms loop

UPLOAD PROGRESS (replaces drop zone after file selected)
  File row: file-icon 16dp + filename (IBM Plex Mono 400 / 14sp) + size (text-muted) + × dismiss
  
  Progress bar: full width / 4dp / --grad-resume fill
  Percentage: right-aligned / DM Mono 400 / 13sp / text-secondary
  Status: "Uploading..." → "Parsing..." → "Analyzing..." (animated trailing dots)

PARSE STATUS CARD (during polling)
  bg-surface / border-default / border-radius: 14dp / padding: 16dp
  
  3-step indicator row:
    Circle: 28dp / done=emerald filled / current=blue pulsing / pending=zinc-700
    Connector line: 1px border-subtle between circles
    Labels: IBM Plex Sans 400 / 11sp / text-muted / center below each circle
    Steps: "Upload" → "Parse" → "Analyze"

SUCCESS STATE
  Draw-on checkmark animation (SVG stroke path, 400ms ease-in-out)
  Circle: 72dp / rgba(16,185,129,0.14) bg / rgba(16,185,129,0.32) border
  "Resume Processed!" — DM Sans 600 / 20sp / #10B981
  "Your resume is ready for AI analysis." — IBM Plex Sans 400 / 14sp / text-muted
  "View Resume →" — Primary button / --grad-resume / centered (24dp top)
```

---

### 4.10 RESUME DETAIL SCREEN

```
BACKGROUND — bg-base
STRUCTURE — CollapsingToolbar + ViewPager2 with sticky TabLayout

COLLAPSING HEADER (expanded: 180dp)
  Background: --grad-resume at 12% overlay over bg-surface
  Border-bottom: TabLayout (sticky after collapse)

  LEFT: Document icon 52×52dp / --grad-resume 20% bg / border-radius: 14dp
  CONTENT: Filename (DM Sans 600 / 20sp / text-primary)
           Upload date (IBM Plex Sans 400 / 12sp / text-muted)
  RIGHT: ATS Score Donut
    Size: 72dp / stroke: 8dp / score gradient fill
    Center: DM Mono 700 / 18sp (score) + "ATS" Label-M text-muted

TAB BAR (sticky)
  Background: bg-elevated
  Tabs: "Overview" | "Sections" | "Skills"
  Indicator: 3dp / --grad-resume / border-radius: 2dp
  Active: IBM Plex Sans 600 / 14sp / text-primary
  Inactive: IBM Plex Sans 400 / 14sp / text-muted

TAB 1 — OVERVIEW
  ATS Breakdown Card (Hero Card style, --grad-resume)
    Title: "ATS Score Breakdown"
    5 metric rows: Formatting / Keywords / Sections / Length / Readability
    Each row: label (IBM Plex Sans 500 / 14sp) + bar (120dp, score gradient) + value (DM Mono / 14sp)
  
  Improvement Alerts
    Each: horizontal card / left 3dp accent bar (red/orange/blue by severity)
    bg-surface / border-default / border-radius: 12dp
    Icon 16dp + alert text + "Fix it →" link (#60A5FA)

TAB 2 — SECTIONS
  Expandable accordion list
  Each section card: bg-elevated / border-default / border-radius: 12dp
  Header: section name + completeness chip + chevron (rotates 0→180° on expand)
  Expanded: IBM Plex Sans 400 / 13sp / text-secondary / 16dp padding
  Expand animation: height animates cubic-bezier(0.4,0,0.2,1) 280ms

TAB 3 — SKILLS
  FlexboxLayout chip grid
  Group labels: "Technical" / "Soft Skills" / "Tools & Frameworks"
    DM Sans 600 / 13sp / text-secondary (8dp below each group)
  Chips: IBM Plex Mono 400 / 12sp (Skill Level Chip spec §1.6)
  
  ADD SKILL FAB (bottom-right): small, --grad-resume, + icon
```

---

## 7. INTERVIEW MODULE

---

### 4.11 INTERVIEW SETUP SCREEN

```
APPBAR — "New Interview Session"
BACKGROUND — bg-base, 24dp horizontal padding

HERO CARD (top, 16dp top margin)
  Hero Card spec + --grad-interview-muted overlay
  Left accent: 4dp / --grad-interview
  Icon: 48×48dp / --grad-interview 20% bg / border-radius: 12dp / mic 24dp white
  "Configure Your Session" — DM Sans 600 / 20sp / text-primary
  "Tailored to your resume and target role." — IBM Plex Sans 400 / 14sp / text-muted

FORM SECTIONS (16dp gaps between each)

  1. RESUME SELECTOR
     Label: "INTERVIEW AGAINST" — Label-L / text-muted
     Selector card: bg-elevated / border-default / border-radius: 12dp
     Content: file-icon + resume name + ATS score chip / chevron-down (right)
     Tap → bottom sheet resume picker
  
  2. TARGET ROLE
     TextInput with autocomplete
     When focused: recent roles appear as chips below input
     Suggestion chip: bg-elevated / border-default / text-secondary
  
  3. INTERVIEW TYPE
     Label: "INTERVIEW TYPE"
     2×2 chip grid (Technical / Behavioral / System Design / HR)
     Selection: single-select / uses type badge colors (§1.6)
     Selected chip: fill with type-bg color / border / colored text / scale 1.03
  
  4. DIFFICULTY SLIDER
     Label: "DIFFICULTY"
     Custom slider: 56dp tall container / 4dp track / 24dp thumb
     Thumb: white circle / 2dp module-color ring / no shadow
     Track fill: --grad-interview from 0 to thumb position
     4 step labels: Easy | Medium | Hard | Expert
     Step snap + haptic feedback (Android VibrationEffect)
  
  5. QUESTION COUNT STEPPER
     Label: "QUESTIONS"
     Row: [–] 36×36dp ghost | [10] DM Mono 600 / 18sp / text-primary / 80dp wide | [+] 36×36dp ghost
     Tap – / +: counter bounces (scale 1→1.15→1, spring 200ms)
     Range: 5 – 30

CTA
  "Start Interview Session" — Primary button / --grad-interview / full width
  Height: 56dp / Border-radius: 14dp
  Shadow: 0 8px 36px rgba(99,102,241,0.38)
  Trailing icon: arrow-right 18dp
```

---

### 4.12 INTERVIEW SESSION SCREEN

```
BACKGROUND — bg-base
LAYOUT — Full screen, immersive, minimal chrome.

TOP BAR (56dp, 16dp horizontal padding, transparent background)
  Border-bottom: 1px solid border-ghost

  LEFT: Question counter chip
    "Q 3 / 10" — DM Mono 500 / 12sp
    bg-surface / border-default / border-radius: 8dp / padding: 6dp 12dp
  
  CENTER: Session timer chip
    "[MM:SS]" — DM Mono 600 / 15sp / text-primary
    bg-surface / border-default
    < 5 min: border → rgba(239,68,68,0.35) / text → #F87171
    < 1 min: bg pulsates rgba(239,68,68,0.10)↔transparent, 800ms loop
  
  RIGHT: Thin circular progress (32dp)
    Track: bg-muted / Fill: --grad-interview / stroke: 3dp
    Shows overall session progress (not question timer)

QUESTION PROGRESS BAR (4dp full-width, below top bar)
  Track: bg-muted / fill: --grad-interview
  Animates to new value on question advance (400ms)

QUESTION CARD (16dp margin, 12dp below progress bar)
  bg-elevated / border: border-default / border-radius: 16dp
  Padding: 20dp
  Top-left decoration: 8dp circle, --grad-interview, positioned at card corner

  CHIPS ROW: question type badge + difficulty badge (§1.6)
  
  QUESTION TEXT
    DM Sans 500 / 17sp / text-primary / line-height: 1.5
    Max 4 visible lines; "Show more" if truncated (#60A5FA / 12sp)
  
  HINT PANEL (collapsed by default)
    "💡 Hint" — IBM Plex Sans 500 / 12sp / text-muted (bottom-right of card)
    Tap → slides down panel below card
    Panel: bg-surface / border: 1px solid rgba(59,130,246,0.18) / border-radius: 0 0 16dp 16dp
    Hint text: IBM Plex Sans 400 / 13sp / text-secondary / italic
    Slide-down: height 0→auto, 280ms cubic-bezier(0.4,0,0.2,1)

ANSWER INPUT (16dp margin, 12dp below question card)
  Multiline TextInput (§3.3 spec)
  Label: "YOUR ANSWER"
  Min-height: 160dp / Max: 240dp (inner scroll)
  Char counter per spec
  
  VOICE INPUT MINI-FAB (bottom-right corner of input area)
    36×36dp / bg-elevated / border-default / mic 16dp / text-muted
    Recording active:
      bg → rgba(239,68,68,0.14) / border → rgba(239,68,68,0.30)
      mic → #F87171
      Pulsing red dot: 8dp / top-right corner / scale 1→1.4→1, 900ms

BOTTOM ACTION ROW (fixed, 72dp, bg-base, border-top: border-subtle)
  Padding: 0 16dp
  Layout: [Skip 80dp] [Submit Answer flex-grow] [End 80dp]
  
  Skip: Ghost button / "Skip"
  Submit: Primary / --grad-interview / "Submit Answer"
  End: Ghost button / "End" / tap → confirmation dialog (Danger Card spec)

FEEDBACK BOTTOM SHEET (post-submission)
  Glass Card, peek: 56dp (drag handle), full: 65% screen
  Drag handle: 40×4dp / bg-muted / border-radius: 2dp / centered / 12dp top
  
  SCORE ROW (24dp top)
    "Answer Score" — IBM Plex Sans 600 / 14sp / text-muted
    Score value: DM Mono 700 / 40sp / [score gradient color]
    Score bar: 6dp / 200dp wide / score gradient / border-radius: 3dp
    Count-up animation: 0→score over 1200ms with overshoot
  
  FEEDBACK ACCORDION
    ✅ "What Worked" — IBM Plex Sans 600 / 14sp / #10B981
    ⚠️  "Could Improve" — IBM Plex Sans 600 / 14sp / #F59E0B
    💡 "Model Answer" — IBM Plex Sans 600 / 14sp / #60A5FA (truncated on free plan)
    
    Each: collapsible / content: IBM Plex Sans 400 / 14sp / text-secondary
    Stagger reveal: score (0ms) → strengths (80ms) → gaps (160ms) → suggestion (240ms)
  
  "Next Question →" — Primary / --grad-interview / full width (bottom of sheet)
```

---

### 4.13 INTERVIEW REPORT SCREEN

```
BACKGROUND — bg-base
STRUCTURE — ScrollView with hero at top

HERO SCORE CARD (16dp margin)
  bg-elevated + --grad-interview-muted overlay
  Border: 1px solid rgba(99,102,241,0.18)
  Border-radius: 20dp / Padding: 24dp

  Session title: DM Sans 600 / 18sp / text-primary
  Date + duration: IBM Plex Sans 400 / 13sp / text-muted

  SCORE DONUT (centered, 24dp top)
    Size: 140dp / Stroke: 12dp / fill: --grad-interview
    Inner: DM Mono 800 / 36sp (overall score)
    "/100": DM Mono 400 / 18sp / text-muted
    "Overall Score": IBM Plex Sans 400 / 12sp / text-muted (8dp below)
    Animate on enter: arc draws 0→score over 1000ms
  
  3 STAT CHIPS ROW (below donut, 16dp top, 8dp gaps)
    Each: bg-surface / border-ghost / border-radius: 8dp / padding: 8dp 14dp
    Value: DM Mono 500 / 13sp / text-primary
    Label: IBM Plex Sans 400 / 11sp / text-muted

RADAR CHART CARD (16dp margin, 16dp below hero)
  bg-elevated / border-default / border-radius: 16dp / padding: 20dp
  Title: "Performance Dimensions" — IBM Plex Sans 600 / 15sp / text-secondary

  RADAR CHART (custom RadarChartView, 260×260dp centered)
    Background rings: bg-surface at each level (20/40/60/80/100%)
    Grid lines: 0.5dp / rgba(255,255,255,0.05) / radial spokes
    Axis labels: DM Mono 400 / 11sp / text-muted (outside ring)
    Data polygon fill: --grad-interview at 18% opacity
    Data polygon stroke: 2dp / #6366F1
    Vertex dots: 8dp / #818CF8 center / 2dp white border
    5 Axes: Clarity | Depth | Structure | Relevance | Confidence
    Animate: all vertices 0,0,0,0,0 → values (spring 800ms)
  
  LEGEND (below chart)
    5 rows: 10dp colored dot + IBM Plex Sans 400 / 13sp / text-secondary + DM Mono 500 / 13sp (right)

QUESTION ACCORDION (below chart)
  Header: "Per-Question Review" + count badge
  
  EACH ITEM
    Collapsed: 64dp height
    bg-elevated / border-default / border-radius: 12dp / 8dp gap
    Row: score badge circle (44dp / score gradient) + question text (truncated 2 lines) + chevron
    
    Expanded: slides to reveal sections
      bg-surface inset within card
      "What Worked" (emerald left-bar) | "What Missed" (red) | "Model Answer" (blue)
      Each: 3dp left-bar + label (IBM Plex Sans 600 / 12sp) + content (IBM Plex Sans 400 / 13sp)
      Expand: height animation + content fade-in 200ms stagger

SHARE ROW (fixed bottom, bg-elevated, border-top: border-subtle, padding: 16dp)
  [Share Report] outlined | [New Session] primary --grad-interview
```

---

## 8. VIDEO INTERVIEW MODULE

---

### 4.14 VIDEO INTERVIEW SETUP SCREEN

```
BACKGROUND — bg-base

CAMERA PERMISSION CARD (if not granted)
  Center card: bg-elevated / border-default / border-radius: 20dp / padding: 32dp
  Camera icon: 64dp / --grad-video fill
  Title: DM Sans 600 / 22sp
  Body: IBM Plex Sans 400 / 14sp / text-secondary
  "Grant Camera & Mic Access" — Primary / --grad-video
  
DEVICE CHECK LIST (after permission)
  4 rows: Camera / Microphone / Lighting / Background
  Each: 56dp height / bg-elevated / border-default / border-radius: 12dp
  Left: icon 20dp + label / Right: status chip (Good/Check/Warning)
  Status colors: Good=emerald / Warning=amber / Error=red

CONFIGURATION
  Duration selector (radio group): 5 min / 10 min / 15 min / Custom
  Question type chips: same as interview setup
  
  "Begin Video Interview" — Primary / --grad-video / full width / 56dp
```

---

### 4.15 VIDEO INTERVIEW SESSION SCREEN

```
LAYOUT — Full screen immersive. CameraX PreviewView fills screen.
All UI layered as overlays on top.

CAMERA PREVIEW
  PreviewView: match_parent / scaleType: fillCenter
  bg-void while initializing
  Init skeleton: center spinner + "Preparing camera..." IBM Plex Sans 400 / 14sp / text-muted

QUESTION OVERLAY (top, 12dp inset, status-bar + 8dp top)
  Glass Card
    Background: rgba(9,9,11,0.80)
    Backdrop-filter: blur(16px) saturate(150%)
    Border: 1px solid rgba(255,255,255,0.07)
    Border-radius: 14dp / Padding: 14dp 16dp
  
  Question text: IBM Plex Sans 400 / 14sp / rgba(255,255,255,0.88) / max 3 lines
  Expand icon if truncated
  Bottom row: type chip (semi-transparent) + countdown timer (DM Mono 600 / 13sp)

REAL-TIME METRIC SIDEBAR (right edge, vertically centered)
  Width: 72dp
  Background: rgba(0,0,0,0.62) / border-radius: 14dp 0 0 14dp (left-open)
  Backdrop-filter: blur(10px)
  Padding: 12dp 8dp / Gap: 18dp between metrics

  EACH METRIC BLOCK
    Label: DM Mono 400 / 9sp / rgba(255,255,255,0.45) / UPPERCASE / center
    Mini bar: 48dp wide / 4dp / border-radius: 2dp
      Track: rgba(255,255,255,0.10) / Fill: metric gradient
      Posture:     --grad-quiz range (green)
      Eye Contact: --grad-interview range (indigo)
      Voice:       --grad-resume range (blue)
    Percentage: DM Mono 600 / 13sp / white / center
  
  EMOTION BLOCK (below metric bars, separated 8dp)
    Emoji icon: 20dp image asset
    Label: emotion name / 9sp / text-muted / center

AI COACH TIP (dismissible, above bottom controls)
  Bottom inset: 88dp from screen bottom / 12dp horizontal
  Design: chip
    bg: rgba(37,99,235,0.72) / backdrop-blur(10px)
    Border: 1px solid rgba(96,165,250,0.28)
    Border-radius: 12dp / Padding: 10dp 14dp
    Text: IBM Plex Sans 400 / 13sp / rgba(255,255,255,0.88) / max 2 lines
    Leading: lightbulb 14dp / #FDE047
    Trailing: × 14dp / rgba(255,255,255,0.45)
    Entrance: slides up + fade 300ms / Exit: slides down on × tap

BOTTOM CONTROLS (centered row, 24dp from bottom safe area)

  HOLD-TO-SPEAK FAB (primary)
    Size: 72×72dp / Border-radius: 20dp
    IDLE:      bg-elevated / border: 2px solid border-accent / mic 28dp / white
    RECORDING: bg pulsates rgba(239,68,68,0.22)↔rgba(239,68,68,0.38)
               Outer ring: animates scale 1→1.18→1 at 900ms / rgba(239,68,68,0.14)
               Mic: #F87171
               Shadow: 0 0 36px rgba(239,68,68,0.45)
  
  NEXT BUTTON (right of FAB, visible after answer)
    44dp height / bg-elevated / border-default / border-radius: 10dp
    "Next →" / IBM Plex Sans 500 / 13sp / text-primary
  
  END SESSION (top-right corner, absolute)
    Danger ghost / 36dp height / "End" + stop-circle icon

RECORDING INDICATOR (top-left corner)
  8dp pulsing red dot + "REC" DM Mono 400 / 10sp / #F87171
  Pulse: scale 1→1.35→1, 1200ms loop
```

---

### 4.16 VIDEO ANALYSIS REPORT SCREEN

```
BACKGROUND — bg-base
STRUCTURE — CollapsingToolbar + ScrollView

HERO CARD (top)
  bg-elevated + --grad-video-muted overlay
  Border: 1px solid rgba(139,92,246,0.18)
  
  Video thumbnail (16:9 rounded, border-radius: 12dp)
  Overlay: play button (48dp circle, white bg, module-color icon)
  
  Duration: DM Mono 400 / 13sp / text-muted
  Session title: DM Sans 600 / 18sp / text-primary
  Date: IBM Plex Sans 400 / 13sp / text-muted

OVERALL METRICS ROW
  4 stat cards (2×2 grid, 10dp gap)
  Eye Contact / Posture / Voice Clarity / Confidence
  Each: Stat Card spec / Top accent: --grad-video

EMOTION TIMELINE CHART
  Horizontal timeline, 60dp height, full width
  Color segments per emotion token (§1.6)
  Tap a segment → emotion chip + time tooltip appear
  X-axis: DM Mono / 10sp / time markers

FRAME-BY-FRAME HIGHLIGHTS
  Section: "Key Moments"
  Horizontal RecyclerView of moment cards (140dp wide × 160dp tall)
  Each: screenshot thumbnail (top) + timestamp + emotion chip (bottom)

PER-QUESTION ANALYSIS ACCORDION
  Each question: score badge + video timestamp chip + expand chevron
  Expanded: metric bars for that specific answer period
```

---

## 9. QUIZ MODULE

---

### 4.17 QUIZ BROWSE SCREEN

```
BACKGROUND — bg-base

HEADER
  "Practice Quizzes" — DM Sans 700 / 24sp / text-primary
  Search bar below (§3.3 search spec)

FILTER ROW (horizontal scrolling chips)
  All | Technical | Behavioral | System Design | HR
  Difficulty: Easy | Medium | Hard | Expert
  Filter chips: §3.5 spec / --grad-quiz for selected

QUIZ CARD (list item)
  bg-elevated / border-default / border-radius: 14dp / padding: 16dp
  Top accent: 3dp / --grad-quiz
  
  Right badge: difficulty badge (§1.6)
  Title: DM Sans 600 / 16sp / text-primary
  Subtitle: IBM Plex Sans 400 / 13sp / text-muted (question count + topic)
  
  Footer row: avg score chip + attempts count + time estimate
    All: bg-surface, border-ghost, border-radius: 6dp, 8dp padding

LEADERBOARD TEASER (at top of list, dismissible)
  Horizontal card, border: 1px solid rgba(250,204,21,0.22)
  --grad-quiz at 6% bg
  Top 3 avatars (overlapping, -8dp) + "See leaderboard →"
```

---

### 4.18 QUIZ ATTEMPT SCREEN

```
LAYOUT — Full screen, no scroll (fits one screen)

TOP SECTION
  Timer progress bar: 4dp / full width / top of screen
    Smooth countdown / --grad-quiz fill / orange at 30% / red at 10%
  
  TOP BAR (12dp horizontal padding, 56dp)
    Left: "Q 4 / 20" — DM Mono 500 / 14sp / text-primary
    Center: quiz title (DM Sans 600 / 16sp / truncated)
    Right: flag button (16dp icon / text-muted → amber when flagged)

QUESTION CARD (16dp margin, 16dp below top bar)
  bg-elevated / border-default / border-radius: 16dp / padding: 20dp
  Difficulty badge: top-right corner (§1.6)
  Question text: DM Sans 500 / 17sp / text-primary / line-height: 1.5

  CODE BLOCK (optional, within question card)
    bg: #0A0A0F (near-black) / border: border-default
    Border-left: 3dp solid --grad-interview
    Border-radius: 8dp / padding: 14dp
    Font: IBM Plex Mono 400 / 13sp / text-secondary
    Line numbers: text-muted / right-padded

ANSWER OPTIONS (16dp margin, 12dp gaps)
  4 options (A/B/C/D), full width
  
  EACH OPTION
    Min-height: 56dp / border-radius: 12dp / bg-elevated
    Border: 1.5px solid border-default / padding: 14dp 16dp
    
    Letter badge: 28×28dp / bg-surface / border-default / border-radius: 8dp
                  DM Mono 600 / 13sp / text-muted
    Option text: IBM Plex Sans 400 / 15sp / text-primary / flex-grow / left-margin 12dp
    
    STATES
      Default:   as above
      Hover:     border → border-accent / bg → bg-overlay
      Selected:  bg → rgba(99,102,241,0.09) / border → rgba(99,102,241,0.45)
                 letter badge: --grad-interview bg / white text
                 option text: IBM Plex Sans 500
      Correct:   bg → rgba(16,185,129,0.09) / border → rgba(16,185,129,0.45)
                 trailing: checkmark 16dp / #10B981
      Incorrect: bg → rgba(239,68,68,0.07) / border → rgba(239,68,68,0.32)
                 trailing: × 16dp / #F87171
      Missed:    bg → rgba(245,158,11,0.07) / border → rgba(245,158,11,0.32)
                 (correct option when user chose wrong)
    All transitions: 200ms ease

BOTTOM BAR (fixed, 72dp, bg-elevated, border-top: border-subtle)
  "Next →" primary / --grad-quiz / disabled until option selected
  Enabled shadow: 0 8px 28px rgba(16,185,129,0.32)
  "Flag" icon-button left (if mid-question review allowed)
```

---

### 4.19 QUIZ RESULT SCREEN

```
BACKGROUND — bg-base

SCORE HERO (top)
  Large donut: 160dp / --grad-quiz / score gradient fill
  Score value: DM Mono 800 / 44sp / text-primary (center)
  "Correct / Total" below: IBM Plex Sans 400 / 14sp / text-muted
  
  Performance label:
    < 50%:  "Keep Practicing" / #F87171
    50–79%: "Good Effort" / #60A5FA
    80–89%: "Well Done" / #10B981
    90%+:   "Outstanding!" / #FDE047 (gold)

STAT CHIPS ROW
  Time Taken | Accuracy | Rank | Points Earned
  Each: Stat Card spec, --grad-quiz top accent

QUESTION REVIEW LIST
  Filter chips: "All" | "Correct" | "Incorrect" | "Skipped" | "Flagged"
  
  Each question card: same as in attempt but showing result state
  Expandable to show explanation
  Explanation: IBM Plex Sans 400 / 13sp / text-secondary
               Left bar: 3dp emerald (correct) or red (incorrect)

RETAKE / NEXT QUIZ BUTTONS (bottom, fixed)
  [Retake Quiz] outlined | [Next Quiz →] primary --grad-quiz
```

---

## 10. LEADERBOARD MODULE

---

### 4.20 LEADERBOARD SCREEN

```
BACKGROUND — bg-base
APPBAR — "Leaderboard" + filter icon

TAB BAR
  TabLayout: bg-elevated / border-bottom: border-subtle
  Tabs: "Global" | "This Week" | "This Quiz"
  Active indicator: --grad-quiz / 3dp / border-radius: 2dp

PODIUM (top 3 — Global / Weekly)
  Layout: [2nd] [1st — taller] [3rd]
  24dp horizontal margin

  EACH POSITION
    Avatar circle:
      #1: 64dp / 3dp gold ring / gold glow
      #2: 48dp / 2.5dp silver ring / silver glow
      #3: 48dp / 2.5dp bronze ring / bronze glow
    
    Rank badge: crown (#1) / silver-medal (#2) / bronze-medal (#3)
      20dp / positioned above avatar / -8dp top offset
    
    Username: IBM Plex Sans 600 / 13sp / text-primary
    Score: DM Mono 500 / 12sp / text-secondary
    
    Podium block (below avatar+name):
      #1: 88dp / --grad-quiz at 14% bg / gold top border
      #2: 64dp / similar style
      #3: 52dp / similar
    
    All colors: §1.6 Leaderboard Podium tokens
    Entrance animation: podium blocks rise from bottom (spring 600ms, stagger 80ms)

RANK LIST (below podium, or full if "This Quiz")
  Each row (64dp height, 16dp padding):
    Rank number: DM Mono 500 / 15sp / text-muted / 32dp right-aligned
    Avatar: 40dp circle / bg-surface
    Name: IBM Plex Sans 600 / 14sp / text-primary
    Score: IBM Plex Sans 400 / 12sp / text-muted
    Badge: score badge 60dp wide (score gradient per §1.5)
    
    Divider: 1px border-ghost (between items, not at edges)
  
  YOUR ROW (sticky at bottom when out of view)
    bg: rgba(99,102,241,0.07)
    Border: 1px solid rgba(99,102,241,0.18)
    "You" chip: rgba(99,102,241,0.18) bg / #818CF8 text
    Name + rank: IBM Plex Sans 700 / text-primary
```

---

## 11. JOBS MODULE

---

### 4.21 JOBS LIST / BROWSE SCREEN

```
BACKGROUND — bg-base

HEADER
  "Job Matches" — DM Sans 700 / 24sp
  Search bar (§3.3 search input)

ACTIVE RESUME SELECTOR
  Compact bar: bg-elevated / border-default / border-radius: 10dp
  "Matching against:" + current resume name + chevron-down
  Tap → bottom sheet resume selector

FILTER ROW (horizontal scrolling)
  Role Type | Location | Salary Range | Experience Level | Remote Only
  Filter chips per §3.5

JOB CARD (list item)
  bg-elevated / border-default / border-radius: 14dp / padding: 16dp
  
  TOP ROW
    Company logo: 44×44dp / bg-surface / border: border-default / border-radius: 10dp
    Match badge (top-right): score gradient chip / DM Mono 600 / 13sp / "XX% Match"
  
  CONTENT
    Company name: IBM Plex Sans 500 / 13sp / text-muted
    Role title: DM Sans 600 / 16sp / text-primary (2 lines max)
    Location + salary row: small tag chips (bg-muted)
  
  SKILL PREVIEW ROW
    3–4 skill chips (IBM Plex Mono / 11sp) + "+N more" chip if overflow
  
  SAVE / APPLY ACTIONS
    [♡ Save] small outlined | [Quick Apply →] small primary --grad-jobs

SORT FAB (bottom-right area, above nav bar)
  Icon button 48×48dp / --grad-jobs at 15% bg / border --grad-jobs
  sort icon / tap → sort bottom sheet
```

---

### 4.22 JOB DETAIL SCREEN

```
BACKGROUND — bg-base
STRUCTURE — ScrollView + sticky bottom CTA

HERO HEADER
  bg-surface / padding: 24dp 16dp 32dp

  Company logo: 56×56dp / bg-elevated / border-default / border-radius: 14dp
  Company: IBM Plex Sans 500 / 14sp / text-muted
  Role title: DM Sans 700 / 26sp / text-primary (line-height: 1.2)
  
  CHIPS ROW (12dp top)
    Location | Job Type (Full-time/Part-time/Contract) | Remote/Onsite
    Salary range chip (bg-muted / text-secondary)
  
  Posted date: IBM Plex Sans 400 / 12sp / text-disabled
  
  ACTIONS ROW
    [♡ Save] icon-button | [Share ↗] icon-button

MATCH SCORE CARD (16dp margin, 8dp below header)
  bg-elevated / border: 1px solid rgba(244,200,80,0.18) / border-radius: 16dp / padding: 20dp

  LEFT: MatchGaugeView (custom, 100×100dp)
    Semi-circle gauge (180°) / 10dp stroke
    Track: rgba(255,255,255,0.055) / fill: gradient red→orange→green
    Center: DM Mono 700 / 22sp / [interpolated color]
    "MATCH" label: IBM Plex Sans 400 / 11sp / text-muted
  
  RIGHT STATS
    "X / Y Skills Matched" — DM Mono 600 / 16sp / #10B981 + text-muted denominator
    "Experience" label + status chip
    "Location" label + status chip

SKILL BREAKDOWN (16dp margin, 12dp below)
  Section header: "Skill Match Analysis"
  
  "✓ You have" — IBM Plex Sans 600 / 12sp / #10B981 (label above)
  Flexbox of matched skill chips (MatchChip spec §1.6)
  
  "✗ You're missing" — IBM Plex Sans 600 / 12sp / #F87171 (label above)
  Flexbox of missing skill chips

JOB DESCRIPTION (16dp margin)
  "About the Role" — Section header
  Text: IBM Plex Sans 400 / 14sp / text-secondary / line-height: 1.65
  Collapsed: 5 lines + gradient fade + "Read more →"
  Expand: height animation 300ms

REQUIREMENTS SECTION (16dp margin)
  Expandable accordion: "Requirements" / "Responsibilities" / "Benefits"
  Each: bg-elevated / border-default / border-radius: 12dp

COMPANY CARD (16dp margin)
  bg-elevated / border-default / border-radius: 14dp / padding: 16dp
  Company logo + name + industry chip + team size
  "View Company →" ghost link

STICKY BOTTOM CTA (88dp + safe area)
  bg-elevated / border-top: border-subtle / padding: 16dp
  [♡ Save Job] outlined (44%) | [Prepare for Interview] primary --grad-interview (52%)
```

---

## 12. ANALYTICS / SESSIONS MODULE

---

### 4.23 SESSIONS HISTORY SCREEN

```
BACKGROUND — bg-base

HEADER
  "My Sessions" — DM Sans 700 / 24sp
  Date range filter (dropdown chip, right-aligned)

SUMMARY STAT ROW (16dp margin)
  3 Stat Cards: Total Sessions | Best Score | Hours Practiced
  Top accent: --grad-sessions each

SESSION CARD (list item)
  Same spec as §4.7 Home screen session cards
  SWIPE LEFT → Delete (confirmation snackbar)
  SWIPE RIGHT → Share report

SECTION HEADERS (date grouping)
  "This Week" / "Last Month" / etc.
  IBM Plex Sans 600 / 13sp / text-muted / UPPERCASE / padding: 8dp 16dp

FILTER ROW
  All | Interview | Video | Quiz
  Difficulty filter
  Score range slider (optional)

EMPTY STATE (per filter)
  "No sessions found for this filter." — Body-M / text-muted / center
```

---

### 4.24 ANALYTICS / PROGRESS SCREEN

```
BACKGROUND — bg-base

STREAK CARD (top, 16dp margin)
  bg-elevated / border: 1px solid rgba(251,146,60,0.22) / border-radius: 16dp / padding: 20dp
  --grad-sessions at 5% overlay

  LEFT: Lottie flame animation (40dp, amber-400, flicker loop)
  RIGHT: Number-XL (48sp, text-primary) + "Day Streak" (IBM Plex Sans 500 / 14sp / text-muted)

  CALENDAR STRIP (below main content, 20dp top)
    Last 7 days, each 32×32dp circle
    Practice day: --grad-sessions fill / Rest day: bg-surface / border-subtle
    Today: 2dp ring in sessions accent color
    Day label below: DM Mono 400 / 10sp / text-muted

SCORE TIMELINE CHART CARD (16dp margin)
  bg-elevated / border-default / border-radius: 16dp / padding: 20dp

  HEADER ROW
    "Score Progress" — IBM Plex Sans 600 / 15sp / text-secondary
    Range chips (right): 1W | 1M | 3M | All (filter chips, --grad-sessions when selected)
  
  LINE CHART (MPAndroidChart, custom themed)
    bg: transparent
    Grid lines: rgba(255,255,255,0.035) dashed
    X axis: DM Mono 400 / 10sp / text-muted (dates)
    Y axis: DM Mono 400 / 10sp / text-muted (0–100)
    Line: 2.5dp / #6366F1
    Fill: rgba(99,102,241,0.11) → transparent (under line)
    Data points: 8dp / bg-base / #6366F1 ring / 2dp stroke
    Press tooltip: Glass Card / DM Mono 600 / 14sp score + IBM Plex Sans 400 / 12sp date

SKILL PERFORMANCE (16dp margin)
  Header: "Skill Breakdown" (expandable)
  Horizontal bar chart per topic:
    Label (IBM Plex Sans 400 / 13sp / text-secondary) + progress bar (--grad-sessions) + score right

WEAK AREAS + STRENGTHS (2-column grid, 12dp gap)
  Left: "Work On" cards / Right: "Strong At" cards

  EACH CARD
    bg-elevated / border-default / border-radius: 12dp / padding: 14dp
    Left accent: 3dp / --grad-sessions (weak) or --grad-quiz (strength)
    Topic: IBM Plex Sans 600 / 14sp / text-primary
    Score: DM Mono 500 / 14sp / [score color]
    Sessions: IBM Plex Sans 400 / 12sp / text-muted
```

---

## 13. PROFILE MODULE

---

### 4.25 PROFILE SCREEN

```
BACKGROUND — bg-base
STRUCTURE — CollapsingToolbar + ScrollView

PROFILE HEADER (expanded: 220dp)
  Background: bg-surface + --grad-profile at 7% overlay + noise 2%

  AVATAR (centered)
    84×84dp circle
    bg-elevated / 3px bg-surface ring (visual gap) / 2.5px --grad-profile outer ring
    Photo (Glide) or initials (DM Sans 700 / 30sp / text-muted)
    Edit overlay on tap: camera icon 16dp / rgba(0,0,0,0.52) bottom half

  Name: DM Sans 700 / 24sp / text-primary (12dp below avatar)
  Title / Role: IBM Plex Sans 400 / 14sp / text-muted
  Member since: IBM Plex Sans 400 / 12sp / text-disabled

  3 STAT ROW (below name)
    Total Sessions | Average Score | Best Score
    Each: Number-L / text-primary above / IBM Plex Sans 400 / 11sp / text-muted below
    Dividers: 1px border-subtle (vertical)

ACHIEVEMENTS SECTION (16dp margin)
  Header: "Achievements" + trophy icon (#FCD34D amber)
  
  Horizontal RecyclerView, snap-to-group
  
  ACHIEVEMENT CARD (100×120dp)
    bg-elevated / border-default / border-radius: 14dp
    Icon container: 48×48dp / border-radius: 12dp / centered
      UNLOCKED: module gradient bg / white icon / full color
      LOCKED: bg-surface / grayscale ColorFilter / 40% opacity
    Title: IBM Plex Sans 600 / 12sp / text-primary / center
    Date: DM Mono 400 / 10sp / text-muted
  
  Locked state overlay: rgba(9,9,11,0.45) / lock icon 16dp center

SETTINGS LIST (16dp margin, 12dp top)
  "Account" section:
    Edit Profile / Change Password / Connected Accounts
  "Preferences" section:
    Notifications / Theme / Language
  "App" section:
    Help & Support / Privacy Policy / About
  
  Each row: 56dp / bg-elevated / border-default / border-radius: 12dp / 8dp gap
  Icon: 20dp / text-muted
  Label: IBM Plex Sans 500 / 14sp / text-primary
  Trailing: chevron-right 16dp / text-muted (or toggle for binary settings)

DANGER ZONE (bottom, 16dp margin)
  "Sign Out" — Ghost/Danger button / full width
  "Delete Account" — Ghost/Danger button / smaller / text-disabled
```

---

### 4.26 EDIT PROFILE SCREEN

```
BACKGROUND — bg-base
APPBAR — "Edit Profile" + "Save" text button (right, #60A5FA)

AVATAR EDIT (top, centered)
  84dp avatar with camera overlay
  Tap → bottom sheet: "Take Photo" | "Choose from Gallery" | "Remove Photo"

FORM SECTIONS (24dp horizontal padding, 16dp gaps)
  Full Name
  Professional Title
  Bio (multiline textarea, max 300 chars)
  Experience Level (chip selector: Fresher / 1–3yr / 3–5yr / 5yr+)
  Target Role (text input with autocomplete)
  Location (text input)
  LinkedIn URL (text input with leading link icon)

SAVE BUTTON (sticky bottom, 16dp padding)
  "Save Changes" — Primary / --grad-profile / full width
```

---

## 14. SETTINGS & SUPPORT SCREENS

---

### 4.27 NOTIFICATION SETTINGS SCREEN

```
GROUPED TOGGLE LIST
  "Interview Reminders" / "New Job Matches" / "Quiz Challenges" / "Weekly Reports"
  Each: label + description (text-muted, 12sp) + Material3 Switch
  
  Switch custom colors:
    Checked: --grad-primary track / white thumb
    Unchecked: bg-muted track / bg-subtle thumb
```

---

### 4.28 SUBSCRIPTION / PRO SCREEN

```
BACKGROUND — bg-base + premium mesh (gold accents at very low opacity)

HEADER
  Crown icon: 64dp / linear-gradient(135deg, #FCD34D 0%, #F59E0B 50%, #D97706 100%)
  "Upgrade to Pro" — DM Sans 700 / 30sp / text-primary
  Tagline — IBM Plex Sans 400 / 14sp / text-muted

PLAN CARDS (horizontal selection)
  Monthly | Annual (pre-selected, highlighted)
  
  SELECTED PLAN CARD
    Border: 2px solid rgba(250,204,21,0.45)
    Background: rgba(250,204,21,0.07)
    Top badge: "BEST VALUE" — Label-M / #FDE047 / centered
    Price: DM Mono 700 / 32sp / text-primary
    Period: IBM Plex Sans 400 / 13sp / text-muted
  
  UNSELECTED PLAN CARD
    Border: border-default / bg-elevated

FEATURES LIST
  Each: checkmark circle (16dp, --grad-quiz) + IBM Plex Sans 400 / 14sp / text-secondary
  
  "Unlimited AI Interview Sessions"
  "Full Model Answer Access"
  "Advanced Analytics & Insights"
  "Priority AI Processing"
  "Video Interview Analysis"

CTA
  "Start Free Trial" — Primary (full width, gold gradient)
    linear-gradient(135deg, #FCD34D 0%, #F59E0B 50%, #B45309 100%)
    Shadow: 0 8px 32px rgba(245,158,11,0.38)
  
  "Restore Purchase" — Ghost / text-muted / centered / 8dp below
```

---

## PART III — SYSTEM PATTERNS

---

## 5. MOTION & ANIMATION SYSTEM

### 5.1 Timing Functions

```
Standard:   cubic-bezier(0.2, 0, 0, 1)          Default transitions
Enter:      cubic-bezier(0.0, 0, 0.2, 1)         Elements appearing
Exit:       cubic-bezier(0.4, 0, 1, 1)           Elements leaving
Spring:     SpringForce stiffness=MEDIUM, damping=LOW_BOUNCY
Overshoot:  cubic-bezier(0.34, 1.56, 0.64, 1)   Score counters, FABs, stars
Smooth:     cubic-bezier(0.25, 0.46, 0.45, 0.94) General ease-in-out
```

### 5.2 Duration Scale

```
Instant:     100ms   Hover / toggle / ripple
Fast:        200ms   Chip select / icon change / snackbar appear
Standard:    300ms   Card expand / drawer / bottom sheet peek
Moderate:    400ms   Page transition / screen enter
Slow:        600ms   Splash logo / complex entrance
Elaborate:   800ms+  Radar chart / score reveal / podium entrance
```

### 5.3 Navigation Transitions

```
PUSH FORWARD (navigate deeper)
  New screen:  translateX(+100%) → 0 + opacity 0→1 / 300ms Standard
  Old screen:  scale 1→0.96 + opacity 1→0.30 / 300ms Standard

POP BACK
  Current:     translateX(0) → +100% + opacity 1→0.5 / 280ms Exit
  Previous:    scale 0.96→1 + opacity 0.30→1 / 280ms Enter

MODAL / BOTTOM SHEET
  Enter:  translateY(+100%) → 0 / 350ms Spring
  Exit:   translateY(0) → +100% / 250ms Exit

CROSS-FADE (tab switches, same-level navigation)
  Both:   opacity 0↔1 / 200ms Standard

SHARED ELEMENT (score cards to report)
  Container: bounds animate / 350ms Standard
  Content: opacity crossfade inside container
```

### 5.4 Element Entry Animations

```
LIST CARDS
  translateY(+20dp) → 0 + opacity 0→1
  Stagger: 55ms per item / Duration: 280ms Enter timing
  Max items animated: first 6 only

SCORE COUNTER (DM Mono number)
  Count 0 → value over 1200ms cubic-bezier(0.0,0,0.2,1)
  Overshoot +3–5 then settle to exact value at 1000ms

RADAR CHART POLYGON
  All vertices 0,0,0,0,0 → target values simultaneously
  800ms / Spring / subtle overshoot at each vertex

SCORE DONUT ARC
  0° → calculated angle over 1000ms cubic-bezier(0.2,0,0,1)
  Color transitions from track color → fill color simultaneously

BOTTOM SHEET FEEDBACK STAGGER
  Score:     0ms / opacity 0→1, translateY(+8dp)→0
  Strengths: 80ms / same
  Gaps:      160ms / same
  Suggestion: 240ms / same

PODIUM ENTRANCE (leaderboard)
  Blocks rise from 0dp to final height (spring 600ms)
  #2 enters first (80ms), then #1 (0ms), then #3 (160ms) — center first rule
  Avatars drop in with bounce after block (100ms delay)
```

### 5.5 Micro-interactions

```
Button press:     scale 1→0.965→1 / 150ms spring
Card press:       scale 1→0.983 on down, reverse on release
Checkbox tick:    SVG path stroke draws / 200ms ease-in-out
Star / Save:      scale 1→1.32→1 + fill color floods in / 250ms spring
Chip select:      ripple from center floods chip / 200ms + border transition
FAB recording:    outer ring: scale 1→1.22→1 loop / 900ms / rgba fade
Notification bell: ring oscillation ±8° / 2 cycles / 300ms on new item
Score badge:      glow intensifies on enter (0 → full → 60%) / 400ms
```

---

## 6. ELEVATION & DEPTH MODEL

```
LAYER Z-ORDER
──────────────────────────────────────
Z-0   bg-void    #020306    Absolute page floor
Z-1   bg-base    #09090B    Screen background
Z-2   bg-surface #0F1117    Inset sections, card interiors
Z-3   bg-elevated #18181B   Raised cards, primary content
Z-4   bg-overlay #1C1C21    Modals, drawers, tooltips
Z-5   bg-muted   #27272A    Highest surface, dropdown items

SHADOW USAGE (only for overlapping elements)
──────────────────────────────────────
Ambient:   0 2px 8px rgba(0,0,0,0.42)
Card:      0 4px 24px rgba(0,0,0,0.5), 0 1px 3px rgba(0,0,0,0.72)
Float:     0 8px 36px rgba(0,0,0,0.62)
Modal:     0 24px 64px rgba(0,0,0,0.72), 0 4px 16px rgba(0,0,0,0.5)
Accent:    0 8px 32px rgba([module-rgb], 0.30) (primary CTA buttons only)
Glass:     0 12px 48px rgba(0,0,0,0.55)

GLASS LAYER SPEC
──────────────────────────────────────
All bottom sheets / modals / overlapping surfaces:
  background:       rgba(12, 12, 16, 0.87)
  backdrop-filter:  blur(28px) saturate(165%)
  border:           1px solid rgba(255,255,255,0.068)
  "Frosted obsidian" — semi-opaque, dark, refined, metal-like.
```

---

## 7. SPACING & GRID SYSTEM

```
BASE UNIT: 4dp
──────────────────────────────────────
 4dp  Icon-to-label gap / chip internal padding
 8dp  Between chips / between small sibling elements
12dp  Card internal section gap / list item vertical padding
16dp  Standard horizontal screen padding / item card padding
20dp  Hero card padding / form section gaps
24dp  Section-to-section spacing / modal padding top
28dp  Generous section breaks
32dp  Major section / modal horizontal padding
40dp  Hero section vertical breathing room
48dp  Full hero vertical padding

HORIZONTAL MARGINS
──────────────────────────────────────
Standard content:    16dp left + right
Hero / wide cards:   16dp left + right
Full-bleed:          0dp (banners, camera, preview)

BOTTOM PADDING
  All scrollable screens: 80dp padding-bottom (nav bar clearance)

ICON SIZES
──────────────────────────────────────
 8dp  Decorative dot
10dp  Trailing action dots
12dp  Inline text icons
16dp  Form icons / chip icons / small actions
18dp  Button trailing icons
20dp  Bottom nav / toolbar icons
22dp  Standard toolbar actions
24dp  Standard feature icons
28dp  Card feature icons
32dp  Empty state icons
48dp  Module identity icons
64dp  Auth screen icon circles
72dp  Splash logo / large onboarding icons

TOUCH TARGETS
  Minimum: 48×48dp (all interactive elements)
  Invisible padding applied to all elements below 48dp physical size
  FABs: at minimum 56×56dp
```

---

## 8. EMPTY STATES

```
STANDARD PATTERN (centered, 60% from top, 32dp horizontal padding)

  Lottie animation: 180dp / module-specific / gentle loop
  Title: DM Sans 600 / 20sp / text-primary / center
  Body: IBM Plex Sans 400 / 14sp / text-muted / center / max 2 lines / line-height: 1.55
  CTA: Primary (module gradient) / 200dp wide / 52dp tall

SCREEN-SPECIFIC EMPTY STATES
──────────────────────────────────────
Resume list:
  "No Resumes Uploaded Yet"
  "Upload your first resume to unlock AI-powered practice."
  CTA: "Upload Resume" → --grad-resume

Session history:
  "No Sessions Yet"
  "Start a mock interview to track your performance over time."
  CTA: "Start Interview" → --grad-interview

Saved jobs:
  "Nothing Saved"
  "Browse matched jobs and save the ones you want to target."
  CTA: "Browse Jobs" → --grad-jobs

Quiz history:
  "No Quizzes Taken"
  "Test your knowledge with topic-specific practice quizzes."
  CTA: "Browse Quizzes" → --grad-quiz

Achievements (all locked):
  "No Achievements Yet"
  "Complete sessions and quizzes to unlock your first badge."
  CTA: "Go Practice" → --grad-interview

Search results empty:
  "No Results Found"
  "Try adjusting your filters or search with different keywords."
  CTA: "Clear Filters" → secondary button (no gradient, outlined)
```

---

## 9. ERROR & FEEDBACK PATTERNS

### 9.1 Snackbar / Toast

```
Position:      bottom / 16dp from nav bar / 16dp horizontal margins
Background:    bg-overlay (#1C1C21)
Border:        1px solid border-default
Border-radius: 12dp  Height: auto  Padding: 14dp 16dp
Max-width:     screen - 32dp  Entry: slide up 4dp + fade 200ms

TYPES
  Error:   4dp left bar #EF4444  + error-circle icon 16dp
  Success: 4dp left bar #10B981  + check-circle icon 16dp
  Info:    4dp left bar #3B82F6  + info-circle icon 16dp
  Warning: 4dp left bar #F59E0B  + alert-triangle icon 16dp

Text:     IBM Plex Sans 400 / 14sp / text-primary
Action:   IBM Plex Sans 600 / 13sp / [module accent] right-aligned (optional)
Duration: 4000ms auto-dismiss / swipe-to-dismiss
```

### 9.2 Inline Validation

```
Below form fields (8dp gap):
  IBM Plex Sans 400 / 12sp / #F87171
  Leading: error-circle 12dp / same color
  Animation: translateY(-4dp)→0 + opacity 0→1 / 200ms Enter timing

Success state: checkmark icon in field trailing / border → emerald
```

### 9.3 Network Error State (full screen)

```
Icon: wifi-off / 48dp / text-muted
"Connection Lost" — DM Sans 600 / 20sp / text-primary
"Check your network and try again." — IBM Plex Sans 400 / 14sp / text-muted
"Retry" — Primary button (small / --grad-primary / centered / 160dp wide)

Auto-retry indicator: thin blue progress bar across top of error card
  Fills over 10s then triggers auto-retry
```

### 9.4 Confirmation Dialog

```
Glass Card spec / width: screen - 48dp / max 360dp / border-radius: 20dp / padding: 24dp

Optional icon: 48dp circle / module or danger color
Title: DM Sans 600 / 20sp / text-primary
Body: IBM Plex Sans 400 / 14sp / text-secondary / line-height: 1.55

ACTION ROW (16dp top)
  [Cancel] outlined / [Confirm] primary (or danger)
  Equal width / 8dp gap
  For destructive: Confirm uses danger button style
  For positive: Confirm uses --grad-primary

Background scrim: rgba(2,3,6,0.7) / backdrop-blur(4px)
Entry: scale 0.92→1 + opacity 0→1 / 250ms Spring
```

---

## 10. ANDROID IMPLEMENTATION TOKENS

### 10.1 Material Design 3 Overrides (themes.xml — night)

```xml
<!-- themes.xml — Night (primary theme) -->
<item name="colorPrimary">            #3B82F6  </item>
<item name="colorOnPrimary">          #FFFFFF  </item>
<item name="colorPrimaryContainer">   #1E3A5F  </item>
<item name="colorOnPrimaryContainer"> #BFDBFE  </item>
<item name="colorSecondary">          #6366F1  </item>
<item name="colorOnSecondary">        #FFFFFF  </item>
<item name="colorTertiary">           #10B981  </item>
<item name="colorSurface">            #0F1117  </item>
<item name="colorOnSurface">          #FAFAFA  </item>
<item name="colorSurfaceVariant">     #18181B  </item>
<item name="colorBackground">         #09090B  </item>
<item name="colorOnBackground">       #FAFAFA  </item>
<item name="colorError">              #EF4444  </item>
<item name="colorOnError">            #FFFFFF  </item>
<item name="android:colorBackground"> #09090B  </item>
<item name="android:windowBackground">#09090B  </item>
<item name="windowLightStatusBar">    false    </item>
<item name="windowLightNavigationBar">false    </item>
<item name="android:statusBarColor"> @android:color/transparent </item>
<item name="android:navigationBarColor">#09090B</item>
```

### 10.2 Shape Tokens

```
Extra Small:    4dp   (chips, small badges)
Small:          8dp   (chips, code blocks)
Medium:         12dp  (inputs, standard cards, buttons)
Large:          16dp  (primary cards)
Extra Large:    20dp  (modals, bottom sheets)
Huge:           24dp  (large modals, onboarding cards)
Full:           999dp (pills, avatars)
```

### 10.3 Drawable Gradient Definitions (res/drawable)

```xml
<!-- grad_electric.xml -->
<shape android:shape="rectangle">
  <gradient android:type="linear" android:angle="135"
    android:startColor="#60A5FA" android:centerColor="#2563EB"
    android:endColor="#1E40AF" />
  <corners android:radius="12dp"/>
</shape>

<!-- grad_interview.xml -->
<shape android:shape="rectangle">
  <gradient android:type="linear" android:angle="135"
    android:startColor="#6366F1" android:centerColor="#4F46E5"
    android:endColor="#3730A3" />
  <corners android:radius="12dp"/>
</shape>

<!-- Pattern repeats for all module gradients -->
```

### 10.4 Custom View Contracts

```
RadarChartView (interview reports)
  attrs: axisCount, strokeColor, fillAlpha, animationDuration
  setData(scores: FloatArray, labels: Array<String>)
  Minimum size: 240×240dp

DonutChartView (ATS score, session overview)
  attrs: strokeWidth, trackColor, animationDuration, showLabel
  setScore(value: Int, maxValue: Int = 100)
  setGradient(startColor: Int, endColor: Int)

MatchGaugeView (job detail screen)
  attrs: strokeWidth, startAngle, sweepAngle
  setMatchPercentage(value: Int) — animates and interpolates color
  Minimum size: 80×80dp
```

### 10.5 Typography (res/font)

```
dm_sans.xml        → DM Sans, weights 400/500/600/700/800
ibm_plex_sans.xml  → IBM Plex Sans, weights 400/500/600
ibm_plex_mono.xml  → IBM Plex Mono, weights 400/500
dm_mono.xml        → DM Mono, weights 400/500/600/700/800

All registered in res/font/ and declared in themes.xml:
<item name="fontFamily">@font/ibm_plex_sans</item>
```

---

## 11. PERFORMANCE & QUALITY STANDARDS

```
IMAGE LOADING
  Library: Coil or Glide with memory + disk cache
  Placeholder: shimmer skeleton (§3.6)
  Error fallback: initials/icon placeholder
  Format: WebP preferred / PNG fallback
  Max dimension: 512dp for avatars, 1024dp for thumbnails

ANIMATION PERFORMANCE
  All animations: run on UI thread unless explicitly hardware-accelerated
  Lottie: use hardware acceleration for complex animations
  RecyclerView: pre-fetch items; stagger only first 6 visible items
  Charts: cache canvas paths; only redraw on data change

ACCESSIBILITY
  Content descriptions on all interactive elements
  Minimum contrast: 4.5:1 for body text, 3:1 for large text
  Touch targets: 48×48dp minimum (§7)
  Semantic roles: all buttons, inputs, lists labeled
  TalkBack navigation order: logical top-to-bottom, left-to-right
  Text scaling: layouts support up to 1.3× font scale without breaking
  Reduced motion: check WindowManager.ACCESSIBILITY_ANIMATION_SCALE
    If 0: disable all non-essential animations

DARK THEME ONLY
  This design system is dark-first. No light mode variant required.
  All colors tested against WCAG 2.1 AA on dark backgrounds.
  Status bar: always transparent, dark icons = false.
```

---

## 12. SCREEN INVENTORY SUMMARY

```
╔═══════════════════════════════════════════════════════════════════════╗
║  MODULE         SCREENS                                               ║
╠═══════════════════════════════════════════════════════════════════════╣
║  Auth           Splash, Onboarding (3 pages), Login, Register,       ║
║                 OTP Verification, Forgot Password         = 7 screens ║
║                                                                       ║
║  Home           Dashboard                                 = 1 screen  ║
║                                                                       ║
║  Resume         List, Upload, Detail (3 tabs)            = 3 screens  ║
║                                                                       ║
║  Interview      Setup, Session, Report                   = 3 screens  ║
║                                                                       ║
║  Video          Setup, Session, Analysis Report          = 3 screens  ║
║                                                                       ║
║  Quiz           Browse, Attempt, Result                  = 3 screens  ║
║                                                                       ║
║  Leaderboard    Leaderboard (3 tabs)                     = 1 screen   ║
║                                                                       ║
║  Jobs           Browse / List, Detail                    = 2 screens  ║
║                                                                       ║
║  Analytics      Sessions History, Analytics / Progress   = 2 screens  ║
║                                                                       ║
║  Profile        Profile, Edit Profile,                                ║
║                 Notification Settings, Pro Upgrade       = 4 screens  ║
║                                                                       ║
║  TOTAL                                              = 29 unique screens║
╚═══════════════════════════════════════════════════════════════════════╝

COMPONENT COUNTS
  Custom Views:       3  (RadarChartView, DonutChartView, MatchGaugeView)
  Bottom Sheet types: 6  (Feedback, Filters, Sort, Resume Select, OTP, Confirm)
  Unique gradients:  18  (8 modules × primary/hover/muted + system + score)
  Animation types:   12  (counter, radar, donut, stagger, podium, etc.)
```

---

*End of Smart AI Mock Interview Design System v3.0*
*Carbon Interface · Senior Frontend Specification · Production Grade*
ENDOFFILE
echo "✅ Done — $(wc -l < /mnt/user-data/outputs/design.md) lines written"
Output

✅ Done — 2488 lines written
