```markdown
# Chapter 4: CSS Units

## Introduction to Units
Units determine the size of everything on your web page. There are many different CSS units, but this chapter focuses on the most commonly used absolute, relative, and viewport-based units.

## Absolute Length Units
*   **Pixels (`px`):** The most common absolute unit, where 1px is basically 1/96th of an inch. Pixels are excellent for strict boundaries like border widths (e.g., `border: 2px solid red`) because they remain the same absolute size regardless of screen size. 
*   **Accessibility Warning:** You should generally avoid using `px` for font sizes. Browsers have a default font size (usually 16px), but users can change this in their browser settings if they need larger text. Hardcoding pixel values for your fonts will override the user's preference and harm your site's accessibility.

## Percentages (`%`)
*   Percentages represent a fraction of another quantity, meaning they are always relative to the parent container's available space.
*   If you set a child element to `width: 50%`, it will take up exactly half the width of whatever space its parent element is currently occupying. Note that block-level elements automatically take up `100%` of their available width by default.

## Relative Length Units (`rem`, `em`, and `ch`)
Relative length units are much safer to use for typography and spacing than absolute units:
*   **`rem` (Root em):** This unit is relative to the root element's font size (the browser's default 16px). Setting a paragraph to `2rem` makes it 32px (2 * 16px). This is the **highly recommended unit for setting font sizes** because it respects user preferences and scales safely without compounding.
*   **`em`:** This unit is relative to the font size of the *element itself* or its parent. 
    *   *Warning:* Avoid using `em` for font sizing. Because it looks at nested parent sizes, `em` values can accidentally amplify and result in massive or microscopic text. 
    *   *Best Use Case:* Use `em` for `padding` and `margin`. If a button has `padding: 1em`, the padding will always perfectly scale proportionally with the button's font size.
*   **`ch` (Character):** This is based on the width of the "0" (zero) character in the element's font. It comes in handy for editorial layouts—for example, setting a paragraph width to `40ch` ensures the line wraps after approximately 40 characters for optimal reading readability.

## Browser Defaults and CSS Resets
*   **User Agent Stylesheet:** By default, browsers add their own hidden margins and padding to elements like `h1` or paragraphs. You can view these hidden defaults using Chrome Dev Tools by inspecting elements.
*   **CSS Reset:** Because these browser defaults can add unwanted spacing, developers often use a basic "CSS reset" applying a universal wildcard selector (`*`) to set `margin: 0` and `padding: 0` across everything, giving them a clean slate to style from.

## Viewport Units (`vw` and `vh`)
Viewport units are tied directly to the size of the browser window (the viewport). 
*   **`vw` (Viewport Width):** 1vw equals 1% of the viewport's total width.
    *   *Warning:* Setting an element to `width: 100vw` can be problematic. Viewport width does not account for the vertical scrollbar that appears when content is long. Setting `100vw` often pushes content *under* the scrollbar, creating an annoying horizontal scrollbar at the bottom of the page. It is usually better to stick to `100%` for widths.
*   **`vh` (Viewport Height):** 1vh equals 1% of the viewport's total height. A very common and useful trick is setting `min-height: 100vh` on the `body` element. This ensures the background and body stretch to the very bottom of the user's screen, even if the page barely has any content.


# Difference Between Viewport Units (vw/vh) and Percentages (%)

The main difference lies in what they use as their reference point to calculate size. 

## Percentages (`%`)
*   **How it works:** A percentage represents a fraction of the available space inside an element's parent container.
*   **Example:** If you set a parent container (like a `<header>`) to take up 50% of the page width, and then you set a child element inside it to `width: 50%`, that child will only take up half of the header's space, which equals 25% of the total page.

## Viewport Units (`vw` and `vh`)
*   **How it works:** These units ignore parent containers and are tied directly to the size of the user's browser window (the viewport). `1vw` equals exactly 1% of the viewport's total width, and `1vh` equals exactly 1% of the viewport's total height.

## The Crucial Difference in Practice: The Scrollbar Issue
The difference becomes very obvious when you set an element to take up the full width of a screen that has a lot of vertical content. When content outgrows the height of the page, the browser automatically adds a vertical scrollbar on the right side.
*   **Using `100vw`:** If you set an element to `width: 100vw`, it takes up 100% of the browser window's width but **does not account for the vertical scrollbar**. Because the scrollbar takes up some width, `100vw` pushes your content *under* the scrollbar, creating an annoying horizontal scrollbar at the bottom of the page.
*   **Using `100%`:** If you set the element to `width: 100%`, it behaves much better because it only takes up 100% of the *available* space, automatically leaving room for the vertical scrollbar without creating horizontal scrolling.

Because of this horizontal scrollbar issue, developers generally prefer using `%` for widths. However, viewport units are incredibly useful for height. A common CSS trick is applying **`min-height: 100vh`** to the `body` element. This guarantees that the background and body will always stretch to the very bottom of the user's screen, even if the web page barely has any content.

