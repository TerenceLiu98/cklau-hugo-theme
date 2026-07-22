# cklau hugo theme

Fork from [Hugo ʕ•ᴥ•ʔ Bear Blog](https://github.com/janraasch/hugo-bearblog)

## Annotation shortcode

Use `annotation` for a short handwritten callout attached to inline content:

```go-html-template
{{< annotation note="no refresh needed" direction="n" color="amber" >}}real-time updates{{< /annotation >}}
```

- `note`: label text. Omit it to render a highlight without an arrow or label.
- `direction`: arrow direction. One of `n`, `ne`, `e`, `se`, `s`, `sw`, `w`, or `nw`; defaults to `n`.
- `color`: optional color. One of `amber`, `blue`, `green`, `red`, `purple`, or `rainbow`.
- `mark`: set to `false` to hide the target highlight while retaining the arrow and label.

Annotations are visual enhancements. Do not use `note` as the only source of essential instructions, status, or validation information. On viewports up to 700px wide, labels are placed in the text flow and arrows are hidden to prevent overflow.

# CHANGELOG

## 2026-07-22

### Added

- Added a local, JavaScript-free `annotation` shortcode based on `neat-annotations`, with eight arrow directions, six colors, highlight-only mode, dark-theme support, and a mobile inline fallback.

## 2026-05-10

### Added

- Added a site-wide light/dark mode toggle in the navigation bar.
- Added sun/moon SVG icons for the toggle without introducing an external icon dependency.
- Added an early head script that applies the saved theme before styles render, reducing theme flash on page load.
- Added `localStorage` persistence for the visitor's selected theme.
- Added support for the system `prefers-color-scheme` setting when the visitor has not made a manual choice.

### Changed

- Replaced the original hard-coded light palette and commented-out dark-mode media query with CSS variables.
- Added light and dark design tokens for body text, headings, links, code blocks, blockquotes, cards, research cards, post tags, and sidenotes.
- Updated navigation spacing to use a flex layout so menu links and the theme toggle align and wrap cleanly.
- Updated the GitHub shortcode from `getJSON` to `resources.GetRemote` plus `transform.Unmarshal` for compatibility with modern Hugo versions.

### Difference From Original Bear Blog

- The original theme does not include a manual theme switcher.
- The original dark-mode support was only a commented-out CSS media query, while this version supports manual switching, saved user preference, and system preference fallback.
- Theme colors are now centralized through CSS variables, making future palette changes easier and less error-prone.
