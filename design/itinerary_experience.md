# Itinerary Builder Experience System

## Vision
Design a cinematic, emotionally warm itinerary builder that feels like a travel companion guiding each decision. The product should balance conversational AI assistance with high agency for the traveler, transforming loose ideas into a living plan that can be refined in the moment and enjoyed after the trip.

## Brand Pillars
- **Calm confidence** – quiet optimism in tone, whitespace-led layouts, and reassuring microcopy.
- **Guided wonder** – each transition reveals the next step like turning pages in a travel magazine.
- **Tactile delight** – interactive elements respond with soft motion, subtle depth, and gentle color shifts.
- **Human-first intelligence** – AI offers suggestions, but the user is always in control.

---

## Visual Language
### Color System
| Role | Hex | Usage |
| --- | --- | --- |
| Background | `#FDFCF9` | Primary background across steps. |
| Primary Accent | `#FF6F61` | Key CTAs, progress dots, positive confirmations. |
| Secondary Accent | `#51B4A3` | Supporting actions ("show me more"), map pins, secondary chips. |
| Neutral Text | `#2B2B2B` | Core typography. |
| Supportive Neutral | `#6F6C66` | Secondary text, helper copy. |
| Highlight / Feedback | `#F5E5C0` | Focus states, selection glow, success ribbons. |
| Soft Shadow | `rgba(29, 23, 16, 0.08)` | Card elevation, floating buttons. |

### Typography
- **Headlines:** Circular Std / Inter Bold, 48–56px, -2% letter spacing, sentence case but conversational ("where are you headed?").
- **Body:** Circular Std / Inter Regular, 18px, +4% letter spacing, 160% line height for breathability.
- **Supporting:** Medium weight for button labels (16px), uppercase avoided; rely on friendly phrasing.

### Iconography & Illustration
- Line icons with rounded caps, 2px stroke, soft charcoal color.
- Destination vibe cards feature vector illustrations with muted gradients, overlaid film grain noise at 6% opacity.

### Imagery
- Full-bleed photography inside cards (16px radius). Apply warm film grade (temperature +4, saturation -6) to maintain consistent palette.

---

## Layout System
### Spacing
- Global grid: 12-column for large screens, but question screens are center-aligned flex layouts.
- Vertical rhythm: 24px base unit, headlines separated by 48px from inputs.

### Containers
- Cards radius 16px, glassmorphism overlay (background blur 18px) for floating elements like the Trip Stack dock.
- No hard borders; use shadow and color to indicate hierarchy.

### Motion Principles
- Forward navigation: 320ms fade-and-slide with cubic-bezier(0.4, 0, 0.2, 1).
- Reverse navigation: 280ms slide back with slight parallax (-12px content offset).
- Drag interactions: spring curve (stiffness 180, damping 20), 60ms delay before lift.
- Confetti: 0.7s radial burst, easing out with opacity fade.

---

## Conversational Flow Overview
1. **Landing ("let's plan your next escape.")**
   - Background travel cinemagraph with soft blur.
   - CTA: "start chatting".
2. **Destination Prompt**
   - Fullscreen question, text input chip with predictive tags (Paris, Kyoto, etc.).
   - Optional globe visualization; selecting location zooms with depth of field.
3. **Companion Selector**
   - Chips (Solo, Partner, Friends, Family, Custom). Chips animate with soft bounce and highlight color.
4. **Duration Selector**
   - Horizontal number picker for length (3 / 5 / 7 / custom). Shows supporting copy "we’ll match the pace".
5. **Dates**
   - Minimal calendar overlay (two months visible). Selected range animates with warm sand highlight.
6. **Trip Vibe**
   - Illustrated cards representing moods (Adventure, Slow mornings, Foodie trail, Culture dive).
   - Multi-select; each card expands slightly on hover/tap.
7. **Suggestion Primer**
   - AI prompt: "want me to scout standout spots?" with "yes please" and "i’ll add my own".
8. **Discovery**
   - Split view: left suggestion carousel + contextual map, right Trip Stack dock.
   - Map pins animate with soft drop shadow and numbered tags.
9. **Add Custom Spot**
   - Floating search chip, invoking overlay with results list and mini map.
10. **Stay Options**
   - Optional card stack (Hotels, Stays, Skip for now).
11. **Organization Prompt**
   - "want me to group everything by day?" yes/no.
12. **Itinerary Timeline**
   - Day cards, drag-and-drop, inline editing for notes.
13. **Map Mode**
   - Full map with day filter, mini timeline sliding panel.
14. **Save & Share**
   - Success state with confetti, CTA "send to your inbox".
15. **Memory Mode**
   - Post-trip timeline, stats summary, "relive your trip" playback button.

Each step is fullscreen with a single intent and accessible back navigation (top-left ghost button labeled "go back").

---

## Detailed Screen Specs
### 1. Landing
- Hero copy: "let's plan your next escape." (56px).
- Subcopy: "we’ll ask a few questions to build something beautiful." (24px).
- Primary button: "start chatting" (pill, 56px height, gradient from `#FF6F61` to `#F9D7B8`).
- Motion: background video slow zoom, CTA bounces subtly every 4s.

### 2. Question Template
- Layout: question text centered at 40% viewport height.
- Input area: either text field, chip row, or carousel depending on question.
- Progress indicator: 6 dots near bottom, active dot filled with primary accent.
- Microcopy example: "you can change anything later." (supportive text below inputs).

### 3. Discovery Screen
- Left column (70% width):
  - Map occupying top 60%, interactive with pastel style (land #FFF6EB, water #E7F4F1).
  - Suggestion carousel below, 3 cards visible, parallax offset 12px.
- Right column (30% width):
  - Trip Stack dock pinned to bottom, glass surface.
  - Each added spot shown as mini card with thumbnail, day placeholder.
- Interaction: tapping "add" triggers card scale to 102%, confetti, then card floats into dock.

### 4. Trip Stack Dock
- Glass container: `rgba(253, 252, 249, 0.82)` with background blur 22px.
- Shows count badge (rounded, warm sand background).
- Buttons: "review day plan" (primary) and "keep exploring" (secondary text link).

### 5. Timeline View
- Days shown as sticky headers with day count + optional weather icon.
- Cards contain: place name, timeframe pill (e.g., 9:00–11:00), notes snippet, tags (Food, Relax).
- Drag handle (6 dots) indicates reorder; on drag, card lifts with drop shadow and highlight border.
- AI chip surfaces contextual hints: "looks like day 2 is packed — want to balance it?".

### 6. Map Mode
- Map takes full screen; top overlay shows day selector chips (Day 1, Day 2...).
- Right side slides in mini itinerary list; each list item highlights corresponding pin when focused.
- Transitions between days animate camera pan and zoom with easing.

### 7. Save & Memory Mode
- Save success: minimal fireworks animation, copy "trip tucked away!".
- Memory timeline: horizontal scroll of polaroid cards (shadow, film grain overlay). Stats banner includes total distance, sunsets, and curated highlights.
- "Relive your trip" triggers map playback with path drawing and photo overlays.

---

## Component Library
| Component | Description | Interaction |
| --- | --- | --- |
| **Question Shell** | Fullscreen container with headline, body, input slot, progress dots, and CTA. | Enter transitions fade in; exit slides left. |
| **Input Chips** | Rounded chips 48px height, text center, optional icon. | Hover brightness +5%, on select fills with primary accent and white text. |
| **Carousel Card** | 280x360px, full-bleed image, title + emoji, subtle gradient overlay bottom. | Parallax on scroll, expands to 110% for 200ms when tapped. |
| **Trip Stack Item** | 72px height mini card, thumbnail, title, day tag. | Reorder via drag, swipe left to remove. |
| **AI Suggestion Chip** | Floating pill with sparkle icon. | Appears with scale + fade, dismissible via swipe. |
| **Timeline Card** | 320x200px (desktop), flexible on mobile. Contains header, note field, attachments. | Tapping expands to full card editing modal. |
| **Confetti Burst** | Particle overlay triggered on add-to-stack and save events. | 0.7s fade out, uses warm sand + accent tones. |

---

## Interaction States
- **Focus**: highlight ring using warm sand, subtle inner glow.
- **Error**: minimal usage; copy-driven ("hmm, i didn’t catch that location. try again?") with underlined input.
- **Loading**: shimmering placeholder cards, copy "scouting dreamy spots...".
- **Empty States**: friendly illustration with prompts ("no spots yet — add a few gems to get started").

---

## Accessibility
- Minimum contrast ratio 4.5:1 for core text.
- Motion reduction setting disables parallax and confetti, replacing with simple fades.
- Keyboard navigation: visible focus states (4px outline, secondary accent).
- Screen reader copy uses sentence case and descriptive labels (e.g., "Add Kyoto Tea Ceremony to Day 1").

---

## Responsive Guidance
- **Mobile:** Question screens remain fullscreen; CTA anchored bottom with safe-area padding. Timeline becomes vertical stack with swipe to reorder.
- **Tablet:** Two-column layout introduced during discovery; Trip Stack moves to right edge.
- **Desktop:** Full split views, map + timeline side-by-side.

---

## Implementation Notes
- Use component-driven architecture (React/Next). Each step is a route with shared layout transitions powered by Framer Motion or React Spring.
- Global state machine (XState) orchestrates conversational flow and ensures one-intent-per-screen.
- AI integration through suggestion service; maintain editable history of user choices.
- Persist itinerary via local storage and optional backend sync.

---

## Sample Microcopy Inventory
| Context | Primary copy | Secondary copy |
| --- | --- | --- |
| Destination prompt | "where are you headed?" | "type a city or pick from the globe." |
| Companion selector | "who’s coming along?" | "we’ll tailor the vibe." |
| Vibe selector | "what mood are you chasing?" | "choose as many as you like." |
| Organization prompt | "want me to group everything by day?" | "you can reshuffle anytime." |
| Save success | "trip tucked away!" | "we emailed the magic." |

---

## Future Enhancements
- Collaborative planning with shared Trip Stack.
- Integrations with calendar & weather for contextual nudges.
- Photo import in Memory Mode with auto-generated highlight reel.

