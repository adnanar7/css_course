```markdown
# Chapter 3: CSS Colors

## Basic Color Properties
CSS provides a few fundamental properties for applying colors to your web page elements:
*   **Background Color:** The `background-color` property sets the background color of an element. You can also use the shorthand property `background` to achieve the same result while typing less code.
*   **Text Color:** The `color` property is used specifically to change the font/text color of an element.

## Four Ways to Specify Color Values
There are multiple formats you can use to define colors in CSS:

1.  **Color Names:** HTML and CSS support 140 standard color names (e.g., `blue`, `papaya whip`, `darkblue`). Visual Studio Code provides an alphabetical drop-down list to help you select these.
2.  **RGB & RGBA:** 
    *   **RGB (Red, Green, Blue):** Uses the `rgb()` function, passing three comma-separated numbers ranging from `0` to `255`. For instance, `rgb(0, 0, 0)` is black, and `rgb(255, 0, 0)` is pure red. 
    *   **RGBA:** Adds an "Alpha" channel for transparency. It takes a fourth value ranging from `0` (completely transparent) to `1` (fully opaque). For example, `0.5` is 50% transparent.
3.  **Hexadecimal (Hex):** A widely used 6-character format using numbers `0-9` and letters `A-F` preceded by a hash symbol (`#`). 
    *   `#000000` is black (absence of color), and `#FFFFFF` is white (maximum value for red, green, and blue). 
    *   **Shorthand:** If the hex pairs match, you can abbreviate it to 3 characters. For example, `#000000` becomes `#000`, and `#333333` becomes `#333`.
4.  **HSL & HSLA:** Stands for Hue, Saturation, and Lightness.
    *   **Hue:** A degree on the color wheel from `0` to `360` (e.g., 0 and 360 are red).
    *   **Saturation:** A percentage where `100%` is the full color and `0%` is completely gray.
    *   **Lightness:** A percentage where `50%` is the normal color, `100%` is completely white, and `0%` is completely black.
    *   **HSLA:** Like RGBA, this adds an alpha channel value from 0 to 1 for transparency.

## Tools for Choosing Colors
*   **VS Code Color Picker:** Hovering over a color square in VS Code brings up an interactive color palette. You can drag a slider to change the hue, adjust transparency, and click the top bar of the palette to seamlessly swap between RGB, Hex, and HSL formats.

## Contrast and Accessibility
When picking colors, you must consider contrast ratios to ensure your text is legible and your site is accessible to everyone.
*   **WCAG Guidelines:** The Web Content Accessibility Guidelines dictate a minimum "AA" contrast ratio of **4.5 to 1 for normal text** and **3 to 1 for large text**. A stricter "AAA" standard requires a ratio of at least 7:1.
*   **Tools:** It is highly recommended to use resources to generate palettes and verify contrast. Two highly recommended tools are **Coolors.co** (for palette generation and contrast checking) and the **WebAIM contrast checker**. 