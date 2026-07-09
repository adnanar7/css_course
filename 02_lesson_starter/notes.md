```markdown
# Chapter 2: CSS Selectors, Cascade, and Inheritance

## The Three Basic Selectors
There are three main levels of selectors commonly used in CSS:
1.  **Element Selector:** Targets all elements of a specific HTML tag (e.g., `body`, `p`, `h1`). For example, styling the `p` element changes every paragraph on the page.
2.  **Class Selector:** Denoted by a period before the name (e.g., `.gray`), classes are the most common type of selector. They are highly flexible because they can be reused on multiple different elements throughout your project. Classes are more specific than element selectors.
3.  **ID Selector:** Targets a specific, unique `id` attribute on an HTML element. While they have the highest specificity of the three, **it is considered bad practice to use ID selectors for styling in CSS**. IDs should be reserved for linking HTML form inputs to labels or for JavaScript.

## Grouping and Descendant Selectors
*   **Grouping Selectors:** You can apply the same style rule to multiple, distinct selectors by separating them with a comma (e.g., `h1, h2`). 
*   **Descendant (Nested) Selectors:** If you remove the comma (e.g., `h1 h2`), you are targeting an element only when it is nested *inside* the first element. For example, `p span` targets only `span` elements inside paragraphs. However, creating a reusable class like `.highlight` is usually a cleaner and more flexible approach.
*   **Universal Selector:** This selects absolutely everything on the page. It applies styles directly to all elements rather than relying on inheritance. It is rarely used for general styling and is typically reserved for a "CSS reset".

## The Cascade and Specificity
*   **The Cascade:** CSS reads from the top down. If there is a conflict between styles of equal weight, the rule placed last in the stylesheet will "win" and be applied to the page.
*   **Specificity:** Specificity overrides the top-down cascade. A class selector will overrule an element selector even if the element selector comes later in the code. A helpful way to think about specificity scores is: Element = 1, Class = 10, ID = 100.
*   **Debugging with Dev Tools:** When a style isn't applying as expected, right-click the page and choose "Inspect" to open Chrome Dev Tools. In the Styles tab, you can see exactly which CSS rules are active and which are crossed out because they were overruled by higher specificity.

## Inheritance
*   **How it Works:** Child elements automatically inherit certain property settings from their parent elements (such as the `body` or `html` element). 
*   **What is Inherited:** Generally, typography and font-related properties (like font-size, color, line-height, and alignment) are inherited. 
*   **What is NOT Inherited:** Properties not related to text (like `border`) are not inherited. Additionally, HTML form elements (like buttons and inputs) do not inherit font settings by default. You can force them to inherit these settings by using the `inherit` keyword (e.g., `font: inherit;`).
*   **DRY Code:** Utilizing inheritance correctly keeps your code "DRY" (Don't Repeat Yourself), making you a more efficient developer.

## The `!important` Flag
*   Adding `!important` to the end of a CSS declaration acts as the "nuclear option," overriding all other cascade and specificity rules. 
*   **Warning:** It is highly discouraged to use this flag. It usually indicates poorly organized or sloppy code. Beginners should avoid using it entirely and instead learn to write properly structured CSS to manage specificity.