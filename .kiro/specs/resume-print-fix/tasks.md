# Implementation Plan

- [x] 1. Optimize page margins and container padding for single-page printing




  - Reduce `@page` margin from 0.5in to 0.4in
  - Reduce `.container` padding in print media from 1in to 0.5in
  - Verify total effective margin is 0.9in (0.4in + 0.5in)
  - _Requirements: 1.1, 1.2_

- [x] 2. Fix section title underlines to render in print





  - Replace `::after` pseudo-element approach with `border-bottom` property
  - Apply `border-bottom: 1px solid #000` to `.section-title`
  - Remove `::after` pseudo-element from print styles
  - Adjust padding-bottom to maintain visual spacing
  - _Requirements: 2.1, 2.2, 2.4_

- [x] 3. Reduce vertical spacing to fit content on one page





  - Reduce `.section` margin-bottom from 2rem to 1.5rem in print media
  - Reduce `.header` margin-bottom from 2rem to 1.5rem in print media
  - Reduce `.education-item` margin-bottom from 1.5rem to 1rem in print media
  - Reduce `.project-item` margin-bottom from 1.5rem to 1rem in print media
  - _Requirements: 1.1, 1.4_

- [x] 4. Fix color rendering properties




  - Remove deprecated `color-adjust` property
  - Keep `-webkit-print-color-adjust: exact`
  - Keep `print-color-adjust: exact`
  - Verify colors render in print preview
  - _Requirements: 2.3_

- [x] 5. Ensure clean print output without browser chrome





  - Verify `a[href]:after { content: none }` rule exists
  - Confirm `@page` rules suppress browser headers/footers
  - Test that document title is set correctly by existing JavaScript
  - _Requirements: 4.1, 4.2, 4.3, 4.4_

- [x] 6. Manual verification checkpoint





  - Test print preview in Chrome
  - Test print preview in Firefox
  - Verify all content fits on one page
  - Verify section title lines are visible
  - Verify spacing matches screen layout
  - Verify no browser URLs in output
  - Document any browser-specific issues
  - _Requirements: 1.1, 2.1, 3.1, 3.2, 3.3, 3.4, 4.1_
