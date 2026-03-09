# Reflection

## 1. flex-direction: row vs flex-direction: column

`flex-direction: row` lines things up side by side, left to right. So if you have a logo and some nav links inside a flex container, they'll sit next to each other on the same horizontal line. That's what I used for the navbar on desktop.

`flex-direction: column` stacks things on top of each other instead. So those same nav links would each be on their own line going downward. That's what I switched to inside the media query so the navbar looks good on mobile.

The easiest way to think about it: row = horizontal, column = vertical.

## 2. Why use relative units instead of fixed pixels?

If you write something like `width: 400px`, that size is locked in no matter what screen the user is on. On a small phone screen that might take up the whole width and break the layout. On a huge monitor it might look tiny.

Relative units like `%`, `vh`, or `rem` scale based on something else — the screen size, the parent element, or the base font size. So your layout adjusts automatically to fit whatever device is viewing it. That's basically the whole point of responsive design: you write the CSS once and it works everywhere instead of needing a separate stylesheet for every screen size.

## 3. AI Attribution

I used the following prompt with Claude (GenAI):

> "Build a flexbox navigation bar with the logo on the left and nav links on the right. Keep the CSS beginner level."

One piece of CSS the AI gave me was this for the navbar:

```css
#navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 24px;
}
```

The AI originally had `padding: 16px 24px` on the navbar, but that made the navbar too tall and pushed the logo and links too far apart vertically. I changed it to `padding: 0 24px` so the vertical spacing was controlled by the link padding instead, which gave it a cleaner look.
