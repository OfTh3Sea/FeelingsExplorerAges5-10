# 🧭 Feelings Explorer
### Emotional Check-in Tool for Ages 5–10

> An interactive, read-friendly emotional check-in experience built for early elementary school children. Features flip-card emotion learning, multi-select feelings with intensity sliders, and a free-draw finger painting canvas.

---

## 📖 Overview

**Feelings Explorer** is a single-file, browser-based emotional check-in tool designed for children aged 5–10 who are beginning to read and can engage with more nuanced emotional concepts than toddlers, but still need age-appropriate language, visual cues, and playful interaction design.

Unlike a simple emotion picker, Feelings Explorer teaches emotional literacy alongside the check-in — every emotion card can be flipped to reveal a child-friendly definition and a relatable real-life example. Children can select multiple emotions simultaneously, rate how strongly they feel each one, and then draw a picture to express what words can't capture.

Designed for use in **elementary school classrooms, counseling offices, pediatric clinics, and at-home wellness routines.**

---

## ✨ Features

### 🃏 Flip Card Emotion System
- **Two-tap interaction:** first tap flips the card to reveal the emotion's definition and a relatable example sentence; second tap selects it
- Cards animate with a smooth 3D flip transition using CSS `perspective` and `rotateY`
- Selected cards glow with a color-matched border highlight
- Cards retain their state if the child navigates back

### 📊 Intensity Sliders
- Every selected emotion reveals a sliding scale (1–10) directly below its card
- Slider track and thumb are color-coded to match the emotion
- "A little → A lot!" labels for age-appropriate framing
- Multiple emotions can be selected and rated simultaneously
- Values are sorted by intensity on the summary screen

### 🎭 Two-Tier Emotion Library
- **8 core feelings** shown by default — approachable, well-known emotions
- **"＋ More feelings" button** expands to all 18 emotions for children who need more specific words
- Each emotion includes a face emoji, color, child-friendly definition, and example sentence

### 🎨 Free-Draw Canvas
- Full finger/stylus drawing on a touch-responsive canvas
- **10 colors** including white (for correction)
- **4 brush sizes** (S, M, L, XL) — large enough for small fingers
- Dedicated **eraser mode**, **undo** (up to 20 steps), and **clear all**
- "Next →" button to proceed; drawing is optional
- Drawing is captured and displayed on the summary screen

### 📋 Summary Screen
- Displays all selected emotions as color-coded chips
- Horizontal bar chart showing each emotion's intensity, sorted strongest first
- Drawing preview if one was created
- "Check in again" and "← Change feelings" actions

### 🌈 Progress Bar
- Thin gradient progress bar at the top of the screen tracks position through the 4-step flow

---

## 🧠 Pedagogical Design

Feelings Explorer is built around core principles of **social-emotional learning (SEL)** for early childhood:

| Principle | Implementation |
|-----------|---------------|
| **Emotional vocabulary building** | Every emotion card teaches its definition and a relatable example |
| **Validation of complexity** | Multi-select allows children to hold two feelings at once — "I can be happy AND nervous" |
| **Self-regulation support** | Rating intensity builds metacognitive awareness of emotional states |
| **Non-verbal expression** | Drawing canvas gives children an outlet when words aren't enough |
| **Age-appropriate language** | All definitions written at a 1st–3rd grade reading level |
| **No wrong answers** | The UI never rejects or corrects an emotional choice |

---

## 🎭 Emotions Library

### Tier 1 — Core Feelings (shown by default)

| Emotion | Emoji | Color | Definition (child-facing) |
|---------|-------|-------|--------------------------|
| Happy | 😊 | `#FFD93D` | "Happy means you feel good inside — like sunshine in your chest." |
| Excited | 🤩 | `#FF9F43` | "Excited means something great is about to happen and you can barely wait!" |
| Proud | 😤 | `#6BCB77` | "Proud means you did something great and feel really good about it." |
| Calm | 😌 | `#74B3CE` | "Calm means feeling peaceful and relaxed — like nothing can bother you." |
| Worried | 😟 | `#FFB347` | "Worried means your brain keeps thinking about something that might go wrong." |
| Frustrated | 😤 | `#FF6B6B` | "Frustrated means you tried really hard but something just isn't working." |
| Sad | 😢 | `#7B9FD4` | "Sad means you feel heavy or hurt inside, often because of something you lost or missed." |
| Scared | 😨 | `#B084CC` | "Scared means something feels dangerous or unknown and your body wants to protect you." |

### Tier 2 — Extended Feelings (tap "＋ More feelings")

| Emotion | Emoji | Color |
|---------|-------|-------|
| Grateful | 🥰 | `#A8E6CF` |
| Silly | 🤪 | `#FF6BB5` |
| Lonely | 🥺 | `#8AAAC8` |
| Confused | 😕 | `#C8A870` |
| Bored | 😑 | `#A0B8C0` |
| Jealous | 😒 | `#78C0A8` |
| Embarrassed | 😳 | `#FF8FA0` |
| Disappointed | 😞 | `#9090C0` |
| Nervous | 😬 | `#D4A847` |
| Hopeful | 🤞 | `#60C0A0` |

---

## 🚀 Getting Started

### Requirements
- Any modern browser (Chrome, Safari, Firefox, Edge)
- No server, build tools, or package manager required
- Works offline after initial load (only Google Fonts requires a connection)

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/feelings-explorer.git

# Navigate into the project
cd feelings-explorer

# Open directly in your browser — that's it
open feelings-explorer.html
```

Or simply **download `feelings-explorer.html`** and open it in any browser. No setup needed.

---

## 📱 Recommended Usage

| Setting | Device | Notes |
|---------|--------|-------|
| Elementary classroom (daily) | iPad or class tablet | Works best in portrait mode |
| School counselor's office | Tablet or laptop | Landscape also works well |
| Pediatric clinic waiting room | iPad on stand | Portrait, full-screen via Add to Home Screen |
| At-home morning routine | Phone or tablet | Any orientation |
| Telehealth session | Child's device or shared screen | Counselor walks through steps verbally |

**Tip:** On iOS, tap Share → "Add to Home Screen" to install as a full-screen app with no browser chrome, for the cleanest tablet experience.

---

## 🗂️ File Structure

```
feelings-explorer.html    ← Entire application (single file, zero dependencies)
README.md                 ← This file
```

This is a **single-file application** by design. All HTML, CSS, JavaScript, emoji data, definitions, and examples are bundled in one portable file that can be emailed, shared via USB, or hosted on any static server.

---

## 🔧 Customization

### Adding or editing emotions

All emotion data is defined in the `EMOTIONS` array in the `<script>` section:

```javascript
const EMOTIONS = [
  {
    id: 'happy',
    label: 'Happy',
    face: '😊',
    color: '#FFD93D',
    lt: '#FFFBEA',       // light background color (used on flip back)
    dk: '#a06800',       // dark text color
    tier: 1,             // 1 = shown by default, 2 = shown after "More feelings"
    def: 'Happy means you feel good inside — like sunshine in your chest.',
    ex: '"I felt happy when my best friend came over to play."'
  },
  // Add new emotions here following the same structure
];
```

### Changing the drawing colors

```javascript
const DRAW_COLORS = [
  '#2d3a4a',  // Dark (default)
  '#e84040',  // Red
  '#FF9F43',  // Orange
  '#FFD93D',  // Yellow
  '#6BCB77',  // Green
  '#4A90D9',  // Blue
  '#B084CC',  // Purple
  '#FF6BB5',  // Pink
  '#A8E6CF',  // Mint
  '#ffffff',  // White (eraser effect)
];
```

### Changing brush sizes

```javascript
const BRUSH_SIZES = [
  { size: 3,  label: 'S'  },
  { size: 6,  label: 'M'  },
  { size: 12, label: 'L'  },
  { size: 24, label: 'XL' },
];
```

### Adjusting the emotion tiers

Change `tier: 1` to `tier: 2` on any emotion to move it behind the "More feelings" button, or vice versa. The UI handles the rest automatically.

---

## 🖼️ App Flow

```
┌─────────────────────────────────────────────────────────┐
│                    WELCOME SCREEN                        │
│         Feelings Explorer · For ages 5–10               │
│              🧠💭  (wobbling animation)                  │
│   ✦ Pick your feelings  ✦ Rate how strong                │
│   ✦ Draw a picture      ✦ Learn what feelings mean       │
│              [ Start Check-in ✨ ]                       │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│               EMOTION PICKER SCREEN                      │
│         "How are you feeling today?"                     │
│   ┌──────────┐  ┌──────────┐  ┌──────────┐             │
│   │   😊     │  │   🤩     │  │   😌     │             │
│   │  Happy   │  │ Excited  │  │   Calm   │  ← tap once │
│   │ Tap more │  │ Tap more │  │ Tap more │    to flip  │
│   └──────────┘  └──────────┘  └──────────┘             │
│                                                          │
│   Selected → intensity slider appears below each card   │
│   [← A little ──────●────── A lot! →]  7               │
│                                                          │
│   [ ＋ More feelings ]  (expands to 18 total)           │
│   ──────────────────────────────────────────            │
│       [ Next: Draw a picture → (2 feelings) ]           │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│                  DRAW SCREEN                             │
│         "Draw how you feel 🎨"                          │
│   ┌─────────────────────────────────┐                   │
│   │                                 │                   │
│   │     [  free drawing canvas  ]   │                   │
│   │                                 │                   │
│   └─────────────────────────────────┘                   │
│   🔵🔴🟡🟢🟣  [ S ][ M ][ L ][XL ]                     │
│   [ ⌫ Erase ]  [ ↩ ]  [ 🗑️ ]  [ Done! ✓ ]             │
└────────────────────────┬────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│                 SUMMARY SCREEN                           │
│              "Your check-in 🌟"                         │
│   😊 Happy  🤩 Excited  (emotion chips)                 │
│   ──────────────────────────────────────                │
│   😊 Happy     ████████░░  8/10                         │
│   🤩 Excited   █████░░░░░  5/10                         │
│   ──────────────────────────────────────                │
│   [ Your drawing preview ]                               │
│   [ Check in again 🔄 ]  [ ← Change feelings ]          │
└─────────────────────────────────────────────────────────┘
```

---

## 💾 Data & Privacy

- **No data is stored** — Feelings Explorer does not use `localStorage`, cookies, or any backend
- Each session is completely fresh; nothing persists between visits
- **No accounts, logins, or tracking** of any kind
- No data is ever transmitted to any server

> This makes Feelings Explorer suitable for use in schools and clinical settings without any data privacy considerations beyond the device itself.

---

## ♿ Accessibility

- All interactive elements are `<div>` or `<button>` elements with click/touch events
- Large touch targets (minimum `160px` card height) for small hands
- Color is never the sole differentiator — each emotion has a distinct emoji, label, and color
- High-contrast text (Nunito 800–900 weight throughout)
- Progress bar provides spatial orientation in the flow
- Back button available on all screens after welcome
- `user-scalable=no` is set to prevent accidental zoom during touch interaction — remove this from the `<meta>` tag if accessibility zoom support is required for your setting

---

## 🧩 Part of a Larger Suite

Feelings Explorer is part of a multi-tool emotional wellness ecosystem:

| Tool | Ages | Key Features |
|------|------|-------------|
| **Feelings Friends** | 1–5 | Picture-based, no reading, sticker canvas, caregiver dashboard |
| **Feelings Explorer** *(this tool)* | 5–10 | Flip cards with definitions, multi-select, intensity sliders, finger drawing |
| **Check In** | 11–17 | Body map, triggers, journal, intensity tracking, optional counselor sharing |
| **Mindscape** | Adults | Full Plutchik emotion wheel, mood journal, CBT-inspired tools |

Each tool is a standalone HTML file — they can be deployed independently or linked together from a common landing page.
```

---

## 🙏 Acknowledgments

- Emotion definitions written to align with the **CASEL Social-Emotional Learning framework** for early elementary
- Intensity rating approach informed by research on **emotional granularity** in child development (Lindquist & Barrett)
- Flip card interaction inspired by flashcard-based vocabulary learning research
- Built for every child who has ever been asked "how are you feeling?" and not quite had the words

---

*Built with ❤️ for curious kids and the grown-ups who care about them.*
