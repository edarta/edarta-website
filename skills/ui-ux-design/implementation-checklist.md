# Implementation Checklist

Run this checklist before claiming any UI implementation is done.
Every item must pass. Document failures and fix them.

---

## Visual Quality

### Color & Palette
- [ ] No generic plain colors (pure `red`, `blue`, `green`) — use curated HSL or hex values
- [ ] All colors defined as CSS custom properties (`--color-*`)
- [ ] Color contrast passes WCAG AA: text ≥ 4.5:1, UI elements ≥ 3:1
- [ ] Color is never the ONLY means of conveying information (add icon/text alongside color for errors, status, etc.)

### Typography
- [ ] Google Font (or equivalent) loaded — no browser default sans-serif
- [ ] Font sizes use the design token scale (`--font-size-*`), not magic pixel values
- [ ] Heading hierarchy is logical: one `<h1>`, then `<h2>`, `<h3>` in order
- [ ] Line height comfortable for body text (1.5–1.7 for paragraphs)
- [ ] Text doesn't exceed ~75 characters per line on wide screens (use `max-width`)

### Spacing & Layout
- [ ] Consistent spacing scale used (prefer multiples of 4px or 8px)
- [ ] Adequate white space — content isn't cramped
- [ ] Visual hierarchy is clear: most important element draws the eye first
- [ ] Grid/layout is aligned — no rogue elements offset from the grid

### Gradients & Depth
- [ ] Gradients are smooth (at least 2 color stops, consider angle)
- [ ] Box shadows use soft values (avoid harsh black shadows)
- [ ] Dark mode: shadows may need to be replaced with subtle borders

---

## Interactivity & Motion

### Hover & Focus States
- [ ] Every interactive element (button, link, card, input) has a visible hover state
- [ ] Focus indicator visible for keyboard navigation (do NOT use `outline: none` without a custom replacement)
- [ ] Active/pressed state on buttons (slight scale or background shift)
- [ ] Disabled state visually distinct and non-interactive

### Transitions
- [ ] All transitions between states use CSS `transition` (not instant snap)
- [ ] Transition duration 150–400ms (shorter for subtle, longer for expressive)
- [ ] `transition` uses `ease` or `ease-out` (avoid `linear` for UI elements)
- [ ] `prefers-reduced-motion` media query respected:
  ```css
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
      animation-duration: 0.01ms !important;
      transition-duration: 0.01ms !important;
    }
  }
  ```

### Micro-animations
- [ ] Card/panel hover lift implemented (if in design brief)
- [ ] Toast/notification has entry animation
- [ ] Loading skeleton used instead of empty space while fetching data (if applicable)

---

## UX Fundamentals

### Feedback States
- [ ] **Loading state** exists for every async operation > 300ms
- [ ] **Empty state** exists — never shows a blank panel (add illustration, explanation, and primary action)
- [ ] **Error state** exists — plain language message + what to do next
- [ ] **Success state** exists for form submissions and key actions

### Forms (if applicable)
- [ ] Required fields clearly marked (before submission)
- [ ] Input format hints provided where needed (e.g. "MM/DD/YYYY")
- [ ] Validation errors appear near the relevant field (not only at top of page)
- [ ] Form state preserved on failed submission (user doesn't re-type everything)
- [ ] Each input has an associated `<label>` (not just placeholder text)
- [ ] Submit button disabled during processing (prevent double-submission)

### Navigation & Orientation
- [ ] User always knows where they are (active nav item highlighted, breadcrumb if deep)
- [ ] Back navigation works and doesn't break state
- [ ] Page `<title>` is descriptive and unique per page

---

## Responsive Design

### Breakpoint Testing (mental check at minimum)
- [ ] **375px (mobile)**: Single column, full-width inputs, hamburger nav if needed
- [ ] **768px (tablet)**: 2-column grid where appropriate, sidebar may collapse
- [ ] **1280px (desktop)**: Full layout as designed

### Mobile Specifics
- [ ] Touch targets ≥ 44×44px (buttons, links, icons)
- [ ] No horizontal scroll on any viewport
- [ ] Text remains readable without zooming (base font ≥ 16px)
- [ ] Images scale correctly (`max-width: 100%`)

---

## Code Quality

### HTML
- [ ] Uses semantic elements: `<nav>`, `<main>`, `<section>`, `<article>`, `<header>`, `<footer>`, `<button>` (not `<div>` for everything)
- [ ] Images have meaningful `alt` attributes (or `alt=""` for decorative)
- [ ] `<html lang="en">` (or correct language) declared
- [ ] No inline styles — all styles in CSS

### CSS
- [ ] Design tokens defined as CSS custom properties at `:root`
- [ ] No magic numbers for colors, spacing, or font sizes — use tokens
- [ ] No `!important` (except in `prefers-reduced-motion` reset)
- [ ] Class names are semantic (`.card`, `.nav-item`, not `.blue-box`, `.thing1`)

### Accessibility
- [ ] All form inputs have `<label>` with matching `for`/`id` or `aria-label`
- [ ] Decorative icons use `aria-hidden="true"`
- [ ] Interactive elements that aren't naturally focusable have `tabindex="0"` and keyboard event handlers
- [ ] Modal/dialog traps focus correctly and releases on close
- [ ] No content relies solely on color to convey meaning

---

## Content

- [ ] No lorem ipsum — all text is real or realistic representative content
- [ ] No placeholder images — use `generate_image` tool or real assets
- [ ] Microcopy is friendly and action-oriented (buttons say what they do: "Save changes", not "Submit")
- [ ] Error messages are in plain language with actionable guidance

---

## Final Gate

```
Before marking this UI as complete, confirm:

[ ] Ran through this entire checklist
[ ] All Critical items pass
[ ] Any skipped items are documented with reason

If any Critical item fails → fix it before declaring done.
```
