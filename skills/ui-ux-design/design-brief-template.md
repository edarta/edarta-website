# Design Brief Template

Use this template when producing a design brief on the CREATE path.
Present section by section — get confirmation after "Visual Direction" before continuing.

---

# Design Brief: [Feature / Page / Component Name]

## Audience & Purpose
**Who:** [Primary user — role, context, technical level]
**Goal:** [What they are trying to accomplish with this UI]
**Context:** [When/where they use this — desktop at work, mobile on the go, etc.]

---

## Visual Direction

### Color Palette
```
--color-primary:    [hex]   /* Main brand/action color */
--color-primary-hover: [hex]
--color-secondary:  [hex]   /* Supporting color */
--color-accent:     [hex]   /* Highlights, badges, tags */
--color-surface:    [hex]   /* Card/panel backgrounds */
--color-background: [hex]   /* Page background */
--color-text:       [hex]   /* Primary text */
--color-text-muted: [hex]   /* Secondary/helper text */
--color-border:     [hex]   /* Dividers and input borders */
--color-error:      [hex]   /* Error states */
--color-success:    [hex]   /* Success states */
```

### Typography
```
--font-family: '[Font Name]', sans-serif;   /* Google Font */
--font-size-xs:   0.75rem;   /* 12px — captions, labels */
--font-size-sm:   0.875rem;  /* 14px — secondary text */
--font-size-base: 1rem;      /* 16px — body */
--font-size-lg:   1.125rem;  /* 18px — lead text */
--font-size-xl:   1.25rem;   /* 20px — small headings */
--font-size-2xl:  1.5rem;    /* 24px — section headings */
--font-size-3xl:  1.875rem;  /* 30px — page headings */
--font-size-4xl:  2.25rem;   /* 36px — hero headings */
```

### Personality
[2-3 adjectives describing the feel, e.g.: "Clean, professional, confidence-building" or "Bold, energetic, modern"]

### Theme
- [ ] Light only
- [ ] Dark only  
- [ ] Both (light default + dark mode via `prefers-color-scheme`)

---

## Layout & Components

### Page Structure
[Describe high-level layout: top nav? Sidebar? Full-bleed hero? Content width? Grid columns?]

### Key Components Needed
- [ ] Navigation (top bar / sidebar / tabs)
- [ ] Cards / panels
- [ ] Data table
- [ ] Forms / inputs
- [ ] Modals / dialogs
- [ ] Buttons (primary, secondary, ghost, destructive)
- [ ] Badges / tags / pills
- [ ] Charts / data visualizations
- [ ] Notifications / toasts
- [ ] Loading skeleton
- [ ] Empty state
- [ ] Error state
- [x] [Other: ___]

### Responsive Behaviour
```
--breakpoint-sm:  640px;   /* Mobile → tablet */
--breakpoint-md:  768px;   /* Tablet portrait */
--breakpoint-lg:  1024px;  /* Tablet landscape / small desktop */
--breakpoint-xl:  1280px;  /* Desktop */
--breakpoint-2xl: 1536px;  /* Wide desktop */
```
Mobile-first: [ ] Yes  [ ] Desktop-first (existing app)

---

## Interaction & Motion

### Transition Speed
- [ ] Subtle (100–200ms) — business/professional feel
- [ ] Moderate (200–300ms) — balanced
- [ ] Expressive (300–400ms) — playful/consumer

### Micro-animations
- Hover lift on cards: [yes/no]
- Button press feedback: [yes/no]
- Page transitions: [yes/no, describe]
- Data loading skeleton: [yes/no]
- Toast/notification entry: [slide in / fade / scale]

### States to Design
- [ ] Default
- [ ] Hover
- [ ] Active/pressed
- [ ] Focus (keyboard)
- [ ] Disabled
- [ ] Loading
- [ ] Empty
- [ ] Error

---

## Constraints

### Technical
- **Framework/stack:** [React / Vue / plain HTML+CSS / Next.js / etc.]
- **Existing design system:** [None / Bootstrap / shadcn / Material / custom tokens]
- **Browser targets:** [Modern only / IE11 / etc.]

### Accessibility
- **Minimum standard:** WCAG AA (default)
- **Special requirements:** [Screen reader optimized? High contrast mode?]

### Other
[Brand guidelines to follow? Specific fonts/colors already mandated? Performance requirements?]

---

*Approved by user on: [date]*
*Saved to: [file path]*
