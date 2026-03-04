# Design Principles Reference

## Nielsen's 10 Usability Heuristics

Use this when running a REVIEW audit. Score each: `✅ Pass` / `⚠️ Partial` / `❌ Fail`

---

### 1. Visibility of System Status
The system should always keep users informed about what is going on, through appropriate feedback within reasonable time.

**Check for:**
- Loading indicators for operations > 300ms
- Progress bars for multi-step processes
- Success/error messages after form submission
- Active states on navigation items (user knows where they are)
- Real-time feedback (character counts, validation as-you-type)

**Common failures:**
- Button click has no visual response
- Long operation with no loading state
- Form submission with no confirmation
- No indication of current page in navigation

---

### 2. Match Between System and Real World
The system should speak the users' language, using words, phrases, and concepts familiar to the user, rather than system-oriented terms.

**Check for:**
- Labels use plain language, not technical jargon
- Icons are universally understood (or labeled)
- Dates/times in user's format and timezone
- Prices in correct currency
- Metaphors that make sense (e.g. trash can for delete)

**Common failures:**
- Error codes exposed to users ("Error 422")
- Technical field names ("userId" instead of "Your account")
- Ambiguous icons without labels

---

### 3. User Control and Freedom
Users often choose system functions by mistake and need a clearly marked "emergency exit" to leave the unwanted state.

**Check for:**
- Undo/redo available for destructive actions
- Cancel buttons on forms and dialogs
- Back navigation never breaks
- Confirmation dialog for irreversible actions (delete, publish)
- Easy way to dismiss modals (X button, Escape key, click outside)

**Common failures:**
- Delete with no confirmation and no undo
- Modal with no close button
- No back button on multi-step flow
- Can't cancel a long-running operation

---

### 4. Consistency and Standards
Users should not have to wonder whether different words, situations, or actions mean the same thing.

**Check for:**
- Same action always uses same label ("Save" not "Save"/"Submit"/"Confirm" interchangeably)
- Same component looks and behaves the same everywhere
- Primary action is always highlighted the same way
- Follows platform conventions (Ctrl+Z for undo, etc.)
- Error handling is consistent across forms

**Common failures:**
- Some pages use "Delete", others use "Remove"
- Primary button is blue on one page, green on another
- Some forms validate on blur, others on submit

---

### 5. Error Prevention
Even better than good error messages is a careful design which prevents a problem from occurring in the first place.

**Check for:**
- Required fields marked clearly (before submission)
- Input constraints visible upfront (max length, format)
- Confirmation step before irreversible actions
- Reasonable defaults pre-selected
- Dangerous actions separated from common actions (not adjacent to "Save")

**Common failures:**
- No indication which fields are required until you submit
- Can accidentally click "Delete Account" when reaching for "Save"
- Date field that silently rejects invalid formats

---

### 6. Recognition Rather Than Recall
Minimize the user's memory load by making objects, actions, and options visible.

**Check for:**
- Navigation always visible (not hidden behind a hamburger on desktop)
- Form values shown in review step before submitting
- Search shows recent or suggested queries
- Previously visited items marked (visited links)
- Context preserved when returning to a list after viewing detail

**Common failures:**
- User must remember to copy an ID before navigating away
- Wizard that doesn't show previous answers in review step
- Dashboard that doesn't show where a link leads

---

### 7. Flexibility and Efficiency of Use
Accelerators — unseen by novice users — may speed up interaction for experts.

**Check for:**
- Keyboard shortcuts for power users
- Search/filter for long lists
- Bulk actions for repeated operations
- Saved preferences or templates
- Quick actions accessible without many clicks

**Common failures:**
- No search on a list with 100+ items
- No way to bulk delete/assign
- Power user must click through 5 screens for a frequent action

---

### 8. Aesthetic and Minimalist Design
Dialogues should not contain irrelevant or rarely needed information. Every extra unit of information competes with the relevant information.

**Check for:**
- Each page has one clear primary action
- Information density appropriate for context
- Decorative elements don't compete with content
- White space used to create hierarchy
- No redundant labels or instructions

**Common failures:**
- Dashboard with 12 equal-weight KPI cards
- Form with instructions that explain the obvious
- Three CTAs competing for attention at same hierarchy level

---

### 9. Help Users Recognize, Diagnose, and Recover from Errors
Error messages should be expressed in plain language, precisely indicate the problem, and constructively suggest a solution.

**Check for:**
- Error messages explain what went wrong (not "An error occurred")
- Error messages explain what to do next
- Errors placed near the field that caused them
- Form state preserved after error (user doesn't re-enter everything)
- Error styling is clear (not just color — use icon + text)

**Common failures:**
- "Something went wrong. Please try again."
- Error shown at top of page, not near the field
- Form cleared after failed submission
- Error only indicated by red border (fails color-blind accessibility)

---

### 10. Help and Documentation
Even though it is better if the system can be used without documentation, it may be necessary to provide help.

**Check for:**
- Tooltips on complex or non-obvious fields
- Empty states explain what to do (not just "No items")
- Onboarding flow for first-time users
- Help text positioned near the field that needs it (not a separate page)
- FAQ or docs easily accessible

**Common failures:**
- Empty state: "No data found" with no guidance
- Complex feature with no tooltip or explanation
- Help buried in footer or settings

---

## WCAG Accessibility Quick Reference

### Contrast Ratios (WCAG AA)
- Normal text (< 18pt): **4.5:1** minimum
- Large text (≥ 18pt or 14pt bold): **3:1** minimum
- UI components (buttons, inputs, icons): **3:1** minimum
- Decorative elements: no requirement

### Interactive Elements
- All interactive elements reachable by keyboard (Tab order)
- Visible focus indicator (don't remove `outline: none` without replacement)
- Click targets ≥ 44×44px on touch devices
- Links distinguishable from body text (underline or sufficient contrast difference)

### Content
- Images have meaningful `alt` text (or `alt=""` for decorative)
- Form inputs have associated `<label>` elements
- Error messages associated with inputs via `aria-describedby`
- Page has a single `<h1>`, logical heading hierarchy
- Language declared on `<html lang="en">`

### Motion
- Animations respect `prefers-reduced-motion` media query
- No content flashes more than 3 times per second (seizure risk)
- Auto-playing media has a pause control

### Color
- Color is never the ONLY means of conveying information
- Error states use icon + text + color (not color alone)

---

## Useful Tools (for reference)
- Contrast checker: [webaim.org/resources/contrastchecker](https://webaim.org/resources/contrastchecker)
- Color palette generator: oklch.com, coolors.co
- WCAG guidelines: [w3.org/WAI/WCAG21/quickref](https://www.w3.org/WAI/WCAG21/quickref/)
