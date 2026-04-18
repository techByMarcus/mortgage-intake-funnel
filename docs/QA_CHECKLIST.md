# QA Checklist

**Last Updated:** April 17, 2026  
**Project:** Mortgage Intake Funnel v1.0.0  
**Test Environment:** Local (file://) and GitHub Pages (https://)

---

## Pre-Testing Setup

### Environment Verification
- [ ] Background image placed at `assets/purchase-hero.png`
- [ ] README.md exists in root folder
- [ ] privacy.html exists and accessible
- [ ] terms.html exists and accessible
- [ ] Browser developer console accessible (F12 or Cmd+Option+I)
- [ ] Multiple browser tabs available for cross-testing

### Test Devices/Browsers
- [ ] Chrome/Edge (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Mobile Chrome (Android)
- [ ] Mobile Safari (iOS)

---

## Section 1: Initial Load & Page 1

### Load & Render
- [ ] Page opens without errors
- [ ] Hero section displays with background image
- [ ] Identity tag visible (Marcus Albright | Senior Loan Officer)
- [ ] Logo/branding displays correctly
- [ ] No console errors on load
- [ ] Page is fully responsive (resize browser, check layout)

### Page 1 Elements
- [ ] Page 1 title visible: "Let's find the right program for you"
- [ ] Consent disclosure text visible and readable
- [ ] Required field label appears on inputs
- [ ] Email input field works (accepts valid email)
- [ ] Phone input field works (accepts phone format)
- [ ] "Continue" button is enabled and clickable
- [ ] Back button is either hidden or disabled
- [ ] Blue progress indicator shows "1 of 9"

### Form Validation (Page 1)
- [ ] Clicking Continue with empty fields shows error
- [ ] Invalid email rejected with error message
- [ ] Invalid phone rejected with error message
- [ ] Page scrolls to first invalid field if multiple missing
- [ ] After fixing, Continue button becomes active again

---

## Section 2: Navigation Flow (Pages 2-9)

### Page 2 - Mortgage Goal
- [ ] Page title: "What brings you here?"
- [ ] 3 radio options visible: Purchase, Refinance, Investment Property
- [ ] Selection highlights and shows as selected
- [ ] Can deselect and reselect different options
- [ ] Back button returns to Page 1 (without losing data)
- [ ] Continue button advances to Page 3
- [ ] Progress bar shows 2/9

### Page 3 - Timeline
- [ ] Page title: "What's your timeline?"
- [ ] 3 radio options visible: As soon as possible, 30-60 days, Just exploring
- [ ] Selections work correctly
- [ ] Back button returns to Page 2 (data preserved)
- [ ] Forward navigation works

### Page 4 - Property Type
- [ ] Page title: "What type of property?"
- [ ] 4 radio options visible: Single-family, Condo, Multi-unit, Unsure
- [ ] Selections respond to clicks
- [ ] Back navigation preserves previous answers
- [ ] Continue advances to Page 5

### Page 5 - Financial Picture
- [ ] Page title: "Financial Picture"
- [ ] Income bracket dropdown functional (5+ options)
- [ ] Employment type dropdown functional (4+ options)
- [ ] Both dropdowns allow selection and deselection
- [ ] Progress shows 5/9

### Page 6 - Starting Position
- [ ] Page title: "Where are you starting from?"
- [ ] Down payment % dropdown functional (6+ options)
- [ ] Credit range dropdown functional (5+ options)
- [ ] Selections persist when navigating back/forward
- [ ] Continue button works

### Page 7 - Lender Education
- [ ] Page title: "Why work with a mortgage loan officer?"
- [ ] Educational content displays (3+ paragraphs or bullet points)
- [ ] Styling is readable with good contrast
- [ ] Continue button appears at bottom
- [ ] Progress shows 7/9

### Page 8 - Situation Details
- [ ] Page title: "Tell us more about your situation"
- [ ] Scenario type options clearly visible (radio or checkbox)
- [ ] Optional notes textarea is functional
- [ ] Textarea allows multi-line input
- [ ] Back navigation works
- [ ] Continue to Page 9 works

---

## Section 3: Page 9 Routing & Dynamic Content

### Routing Verification (Test All 3 Paths)

**Path A: "Exploring" Route** (Timeline: Just exploring, Goal: Investment or Refinance)
- [ ] Navigate to Page 9 via Exploring path
- [ ] Dynamic content displays with Exploring-specific messaging
- [ ] CTA button says "Schedule Expert Consultation" or similar
- [ ] Program suggestions lean toward educational/informational
- [ ] Phone number displays prominently
- [ ] Back button returns to Page 8

**Path B: "Ready" Route** (Timeline: 30-60 days, Goal: Purchase or Refinance)
- [ ] Navigate to Page 9 via Ready route
- [ ] Dynamic content shows Ready-specific messaging
- [ ] CTA button says "Get Pre-Qualified Now" or similar
- [ ] Program suggestions show actionable options
- [ ] Phone number and email both visible
- [ ] Terms modal link appears (see Section 4)

**Path C: "Complex" Route** (Timeline: As soon as possible, Goal: Investment or complex scenario)
- [ ] Navigate to Page 9 via Complex route
- [ ] Dynamic content displays with Complex-specific messaging
- [ ] CTA button says "Talk to a Specialist" or similar
- [ ] Program suggestions reference specialized programs
- [ ] Additional resources/documents link appears
- [ ] Phone number prominently displayed

### Page 9 Functionality
- [ ] Alert pops up when CTA button clicked
- [ ] Alert shows phone submission message
- [ ] Multiple visits to Page 9 show consistent data
- [ ] Modal dialog appears and closes properly (if present)
- [ ] Progress bar shows 9/9
- [ ] Style consistency across all 3 route variations

---

## Section 4: Links & Modal Functionality

### Privacy/Terms Links
- [ ] "Privacy Policy" link in footer is clickable
- [ ] Clicking opens privacy.html in same or new tab
- [ ] privacy.html displays correctly with formatting
- [ ] Back link in privacy.html returns to index.html
- [ ] No console errors on privacy page

- [ ] "Terms of Use" link in footer is clickable
- [ ] Clicking opens terms.html in same or new tab
- [ ] terms.html displays with proper sections
- [ ] Yellow disclaimer box is visible and prominent
- [ ] Back link works correctly
- [ ] No styling conflicts on terms page

### Terms Modal (if present on Page 9)
- [ ] Modal link/button visible on Page 9
- [ ] Clicking opens terms modal overlay
- [ ] Modal is readable and scrollable
- [ ] Close button (X) works and closes modal
- [ ] Clicking outside modal doesn't close it
- [ ] Background darkens appropriately

---

## Section 5: Form Data Persistence

### Back Navigation Data Retention
- [ ] Fill out Page 1 (email, phone)
- [ ] Advance to Page 2, then go back to Page 1
- [ ] Email and phone values are preserved
- [ ] Test this for all pages: 1→2, 2→5, 7→6, 8→3, etc.

### Multiple Navigation Cycles
- [ ] Complete all 9 pages (set all selections)
- [ ] Go back to Page 1
- [ ] Verify all previous answers are still there
- [ ] Navigate forward again
- [ ] Confirm data persists throughout

### Validation Persistence After Error
- [ ] Try to advance with empty required fields
- [ ] See error message appear
- [ ] Fill in fields
- [ ] Verify filled data persists
- [ ] Advance successfully

---

## Section 6: Responsive Design Testing

### Mobile Layout (375px width)
- [ ] Page loads correctly at 375px width
- [ ] Hero content repositioned (single column)
- [ ] Cards stack vertically
- [ ] Buttons are full-width and easily tappable
- [ ] Text is readable without horizontal scroll
- [ ] Touch targets are at least 44px tall
- [ ] No content is cut off or hidden
- [ ] Font sizes scale appropriately

### Tablet Layout (768px width)
- [ ] Layout adapts correctly at 768px
- [ ] Cards may be side-by-side or stacked (design-dependent)
- [ ] Navigation works with touch
- [ ] All content visible without excessive scrolling
- [ ] Images scale proportionally

### Desktop Layout (1200px+ width)
- [ ] Full hero image displays
- [ ] Split-screen layout may appear
- [ ] All buttons have hover effects
- [ ] No excessive whitespace
- [ ] Professional appearance maintained

### Orientation Testing (Mobile)
- [ ] Test portrait mode (Page 1-9 all viewable)
- [ ] Test landscape mode (no critical content hidden)
- [ ] Rotation between orientations preserves form data

---

## Section 7: Browser Compatibility

### Chrome/Edge
- [ ] All pages load and function correctly
- [ ] CSS animations smooth
- [ ] No layout bugs or rendering issues
- [ ] Console is clean (no error messages)

### Firefox
- [ ] All pages render correctly
- [ ] Dropdowns work properly
- [ ] Form validation functions as designed
- [ ] Animations are smooth

### Safari (Desktop)
- [ ] Background image displays correctly
- [ ] Glass-morphism effects render properly
- [ ] All interactive elements work
- [ ] No layout issues

### Safari (iOS Mobile)
- [ ] Buttons are easily tappable
- [ ] Scrolling is smooth
- [ ] Form inputs work (no iOS-specific bugs)
- [ ] Screen orientation changes handled

### Android Chrome
- [ ] Mobile responsiveness works correctly
- [ ] Form inputs function properly
- [ ] Animations smooth and not jumpy

---

## Section 8: Accessibility & Compliance

### Semantic HTML
- [ ] Inspect page in dev tools
- [ ] Form elements are properly labeled
- [ ] Buttons are actual `<button>` tags or have role="button"
- [ ] Links are actual `<a>` tags
- [ ] Heading hierarchy is logical (h1 > h2, etc.)

### Keyboard Navigation
- [ ] Tab through all form elements
- [ ] Tab order is logical (left to right, top to bottom)
- [ ] Can navigate back button with keyboard
- [ ] Can activate buttons with Enter/Space key
- [ ] Focus indicator is visible (browser default or custom)
- [ ] Can tab to and operate dropdowns

### Screen Reader Compatibility (if testable)
- [ ] Page title is descriptive
- [ ] Buttons have descriptive text (not just "Click here")
- [ ] Form labels are associated with inputs
- [ ] Error messages are announced

### Visual Design Compliance
- [ ] Color contrast is sufficient (WCAG AA standard)
- [ ] No text color issues or unreadable sections
- [ ] Required field indicators are clear
- [ ] Error messages use color + text/icon (not color alone)

---

## Section 9: Performance

### Load Time
- [ ] Page loads in under 2 seconds on fast connection
- [ ] No visual layout shift after initial load
- [ ] Images load quickly (no prolonged blank spaces)

### Animations
- [ ] Fade-in animations on page load
- [ ] Slide-up animations on cards
- [ ] Smooth transitions between elements
- [ ] No jank or stuttering (constant 60fps target)
- [ ] Animations don't cause layout thrashing

### Resource Usage
- [ ] Only 1 external request (purchase-hero.png background image)
- [ ] No unexpected network requests
- [ ] No console warnings about deprecated code
- [ ] JavaScript execution completes quickly

---

## Section 10: Error Handling & Edge Cases

### Invalid Input Handling
- [ ] Invalid email format rejected with clear error
- [ ] Empty required fields trigger validation error
- [ ] Invalid phone format shows error message
- [ ] User can fix error and proceed

### Back Navigation Edge Cases
- [ ] Back button on Page 2 is disabled/hidden
- [ ] Back button on Page 9 works correctly
- [ ] Back from Page 9 → Page 8 → back arrow restores Page 8 data
- [ ] Clicking back multiple times in sequence works

### Unusual Selection Combinations
- [ ] Goal: Investment + Timeline: As soon as possible → Complex route (verify correct path)
- [ ] Goal: Purchase + Timeline: Just exploring → Exploring route (verify)
- [ ] Goal: Refinance + Any timeline → Routes to appropriate path (verify)

### Rapid Clicking
- [ ] Multiple rapid clicks on Continue button don't duplicate submissions
- [ ] Multiple back/forward clicks don't cause navigation errors
- [ ] Form state remains consistent

### Browser Dev Tools Issues
- [ ] Open DevTools while on Page 5 → content still visible
- [ ] Resize window while modal open → modal remains centered
- [ ] Change browser zoom (90%, 110%, 150%) → layout adapts

---

## Section 11: Image & Asset Loading

### Background Image
- [ ] Background image loads from assets/purchase-hero.png
- [ ] Image displays at all breakpoints
- [ ] Image quality is good (not pixelated)
- [ ] Fallback overlay color visible (in case image fails to load)
- [ ] Image doesn't interfere with text readability
- [ ] On mobile, image scales appropriately (may crop, but not distorted)

### Missing Asset Handling
- [ ] If assets/purchase-hero.png not present, page still displays (graceful fallback)
- [ ] No 404 errors in console blocking page functionality
- [ ] Background overlay is still visible even without image

---

## Section 12: Footer & Global Elements

### Footer Elements
- [ ] Footer displays at bottom of all pages
- [ ] Marcus Albright identity tag is visible
- [ ] NMLS numbers #320841 and #1503465 display correctly
- [ ] Privacy Policy link works
- [ ] Terms of Use link works
- [ ] Footer styling is consistent across all pages
- [ ] Footer is not sticky (scrolls with page)

### Progress Bar
- [ ] Progress bar appears on all pages
- [ ] Indicator shows current page number (e.g., "3 of 9")
- [ ] Progress bar advances with each page
- [ ] On Page 9, bar shows "9 of 9"
- [ ] Progress bar styling is consistent (blue/teal color)

---

## Section 13: Use Cases & Real Scenarios

### Scenario 1: First-Time Homebuyer
- [ ] Goal: Purchase
- [ ] Timeline: 30-60 days
- [ ] Property Type: Single-family
- [ ] Income: $75k-$125k
- [ ] Employment: W-2 Employee
- [ ] Down Payment: 10-20%
- [ ] Credit: Good (720-759)
- [ ] **Expected Route:** Ready
- [ ] **Verification:** Page 9 content matches Ready-route messaging

### Scenario 2: Investment Property Inquiry
- [ ] Goal: Investment Property
- [ ] Timeline: Just exploring
- [ ] Property Type: Multi-unit
- [ ] Income: $125k+
- [ ] Employment: Self-employed
- [ ] Down Payment: 25%+
- [ ] Credit: Excellent (760+)
- [ ] **Expected Route:** Exploring
- [ ] **Verification:** Page 9 shows educational/consultation focus

### Scenario 3: Urgent Refinance
- [ ] Goal: Refinance
- [ ] Timeline: As soon as possible
- [ ] Property Type: Condo
- [ ] Income: $50k-$75k
- [ ] Employment: W-2 Employee
- [ ] Down Payment: 10% (existing equity)
- [ ] Credit: Fair (660-719)
- [ ] **Expected Route:** Complex
- [ ] **Verification:** Page 9 content emphasizes specialist consultation

---

## Section 14: Final Verification Checklist

### All Functionality
- [ ] All 9 pages navigate correctly
- [ ] All 3 routing paths work (tested with real scenarios)
- [ ] Form validation works on every page
- [ ] Back navigation preserves data
- [ ] Privacy/Terms links functional
- [ ] No console errors (F12 DevTools)
- [ ] No broken links
- [ ] Responsive on mobile/tablet/desktop
- [ ] Cross-browser tested (Chrome, Firefox, Safari)
- [ ] Performance acceptable (<2s load)

### Compliance & Legal
- [ ] NMLS credentials displayed correctly
- [ ] Privacy Policy page readable and complete
- [ ] Terms of Use page readable and complete
- [ ] Non-commitment disclaimer visible on Page 9
- [ ] Consent text present on Page 1
- [ ] No misleading claims or false commitments

### Professional Appearance
- [ ] Premium design/styling (glass-morphism, animations)
- [ ] Consistent branding throughout
- [ ] No typos or grammatical errors
- [ ] Proper color contrast and readability
- [ ] Professional tone in all copy

### Ready for Publication
- [ ] ✅ All 14 sections pass QA testing
- [ ] ✅ Documentation complete (README, STATUS, CHECKLIST, CHANGELOG)
- [ ] ✅ Assets folder prepared with background image
- [ ] ✅ No blocking issues or critical bugs
- [ ] ✅ Code is clean and optimized
- [ ] ✅ Ready to push to GitHub

---

## Sign-Off

**QA Tester:** [Your Name]  
**Date Tested:** [Date]  
**Result:** ☐ PASS ☐ FAIL (if fail, document issues below)

**Issues Found (if any):**
1. [Issue description]
2. [Issue description]

**Notes:**
[Additional observations or recommendations]

---

**Status:** Ready for GitHub publication upon successful QA completion.
