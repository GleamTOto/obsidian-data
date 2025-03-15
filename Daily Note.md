---
aliases: []
tags:
  - daily-note
  - frontend-learning
created: 2025-03-04T22:06
updated: 2025-03-04T22:08
---
# 2025-03-04 - Daily Note

**Created:** 2025-03-04 15:58
**Author:** GleamTOto

## Summary
Today I focused on CSS layout systems, particularly the differences between Flexbox and Grid, and when to use each one for frontend development.

## Today I Learned
- The fundamental difference between Flexbox (1D) and Grid (2D) layout systems
- Common use cases for Flexbox: navigation bars, card layouts, centering
- Common use cases for Grid: page layouts, complex alignments, overlapping elements
- How to combine both systems effectively in the same project

## Code I Wrote
```css
/* Navigation bar using Flexbox */
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
}

/* Page layout using Grid */
.page {
  display: grid;
  grid-template-columns: 1fr 3fr 1fr;
  grid-template-rows: auto 1fr auto;
  grid-template-areas: 
    "header header header"
    "sidebar content aside"
    "footer footer footer";
  min-height: 100vh;
}
````

## Questions

- How do browsers handle Flexbox/Grid fallbacks for older browsers?
- What's the current browser support for subgrid?
- Are there performance differences between complex Grid layouts and table layouts?

## Insights

- I realized that my approach of using Flexbox for everything isn't optimal. Grid is much better for overall page structure, while Flexbox excels at component-level layouts.
- The mental model of thinking in terms of tracks (Grid) vs axes (Flexbox) helps decide which to use.

## Action Items

- [x]  Create notes on Flexbox and Grid
- [ ]  Practice building a complete page layout using Grid
- [ ]  Update my portfolio site to use proper Grid layout
- [ ]  Study subgrid examples

## Resources

- [CSS Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Tricks - A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Flexbox Froggy](https://flexboxfroggy.com/)
- [Grid Garden](https://cssgridgarden.com/)

## Mood

Excited about the possibilities of creating more complex layouts. Feel like I've been underutilizing Grid all this time.

## Tomorrow's Focus

- Responsive design techniques with Flexbox and Grid
- Media queries and breakpoints
- Start implementing Grid layout in my portfolio project

---

## Metadata

- Status: #status/active
- Topics: #frontend #css #daily-learning #layout