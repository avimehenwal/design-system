---
title: Style
tags:
  - style
  - css
---

# Style

<TagLinks />

## How to style web?

[CSS Timeline](../docs/art/css-timeline.png)

[how to organize behaviours styles and markups](../docs/art/behaviour-markup-styles.webp)

## [CSS-in-JS](https://en.wikipedia.org/wiki/CSS-in-JS)

> Dynamic styles?

- JS is parsed to CSS, usually `<style>` elements are attached to DOM in head
- Implementaions using tagged template literals
  - emotionsjs
  - styled components
  - JSS
- Modular, scoped CSS
- Abstracts CSS model to component level rather than webpage level
- [Use react to dynamically add styles @clinet](https://stackoverflow.com/questions/27530462/tag-error-react-jsx-style-tag-error-on-render)

- [generates not CSS files, all styles are added to head using JS](https://dev.to/alexsergey/css-modules-vs-css-in-js-who-wins-3n25)
- styles could not be rendered unless JS is fully parsed. fewtching -> Parsing -> hydration -> rendering
- caching is NOT possible
- [Pros of using CSS only solutions over CSS-in-JS](https://github.com/callstack/linaria/blob/master/docs/BENEFITS.md)

Don’t use runtime CSS-in-JS if you care about the load performance of your site.

> Simply less JS = Faster Site.

There isn’t much we can do about it.

Great developer experience shouldn’t come at the expense of the user experience. UX >> DX

## [CSS modules](https://www.javascriptstuff.com/what-are-css-modules/)

your browser doesn't have a concept of 'local scope' for CSS. If CSS rules are not unique globally, then they will overlap.

[how css modules scopes css locally](../docs/art/css-modules-diagram.png)

- https://www.javascriptstuff.com/css-modules-by-example/

### EmotionsJS

3 APIs to use

1. @emotion/css
2. @emotion/react
3. @emotion/styled

When using our JSX factories the support for css prop is being added only for components that accepts className prop as they take provided css prop, resolves it and pass the generated className to the rendered component.

Emotion has two ways of generating style definitions:

**Statically** where the style definition can be computed ahead of time. Example:- where styles do not change in response to some prop

**Dynamically** where the style definition gets computed on the client.

[CSS-in-JS (like emotion), generates className on every unique style.](https://stackoverflow.com/questions/62161888/using-emotion-new-style-is-getting-outputted-in-the-head-every-time-compone)

By frequently using a dynamic value like in your case, you will overflow your memory with such styles.

### Notes

- Performance test css frameworks?
  - [pure CSS | MUIv5 | MUIv4](https://codesandbox.io/s/zlh5w?file=/src/App.js)
  - render 100 Boxes component

| CSS strategy | Duration |
| ------------ | -------- |
| Pure CSS     | 7ms      |
| MUI v5       | 56ms     |
| MUI v4       | 964ms    |

Plain old CSS. No libs. No builds

- If you include multiple `<style>` and `<link>` elements in your document, they will be applied to the DOM in the order they are included in the document — make sure you include them in the correct order, to avoid unexpected cascade issues.
- CSS is treated as a [render-blocking resource](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css)
- [premature optimization](http://wiki.c2.com/?PrematureOptimization)

## Bleeding edge CSS features

- [prefer color schemes](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)
- [from page base to individual container queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries)

## Extend

- Multiple theme pressetns, why stick to dark and light mode only?, cobalt and gruvbox themes
- [Create your own CSS parser using tagged template literals](https://github.com/benjamminj/twirl-js)
- only react based solution
  - react abstracts cross-browser DOM Manipulation and Event processsing API
- [custom events with react](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events)
  - in Vue, you dispatch custom events using `$emit`
  - [react custom event](https://www.falldowngoboone.com/blog/talk-to-your-react-components-with-custom-events/)
  - [event vs customEvent](https://stackoverflow.com/questions/40794580/event-vs-customevent)
- Feature toggle provider pattern
- How to inject responsive layout styles into components itself?
- change theme automatically based on the time of the day, and color theme of system

## CSS Parsers

- http://glazman.org/JSCSSP/

## References

- https://www.webdesignmuseum.org/web-design-history/timeline-1990-1994
- https://web.dev/learn/css/
- https://stackoverflow.com/questions/2830296/using-style-tags-in-the-body-with-other-html
- https://developer.mozilla.org/en-US/docs/Web/CSS/@page

<iframe width="560" height="315" src="https://www.youtube.com/embed/MN3RWhGudvw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/jUQ2-C5ZNRc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<Footer />
