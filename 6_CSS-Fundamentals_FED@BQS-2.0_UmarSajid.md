# **Foundational CSS**

### **Introduction**

Welcome\! If you're starting your journey with CSS, you've come to the right place. This guide consolidates the essential foundational lessons from The Odin Project into a single, easy-to-follow document designed to help you succeed.

CSS has a reputation for being a bit tricky, but the truth is that a solid grasp of a few core concepts is all you need to start building beautiful, well-structured websites. We'll walk through these concepts together, step-by-step. Our journey will take us from the absolute basics of CSS syntax and selectors, through the fundamental "box model" that governs every element on the page, and into the powerful world of modern layouts with Flexbox.

Let's get started and learn how to make your webpages look great\!

\--------------------------------------------------------------------------------

## **1.0 Getting Started: How to Talk to Your Webpage with CSS**

Before we can create beautiful designs, we must first learn the fundamental language of CSS and the different ways to connect it to an HTML document. Think of this as learning the basic grammar and vocabulary you need to give instructions to the browser. This is the essential first step in any web development project.

### **1.1 The Basic Language of CSS**

At its core, CSS is a set of rules. Each rule consists of a **selector** that targets an HTML element, followed by a **declaration block** inside curly braces {}. Inside this block are one or more **declarations**, which are property-value pairs separated by semicolons.

/\* A CSS Rule \*/

div { /\* 'div' is the selector \*/  
  color: white;         /\* 'color: white;' is a declaration \*/  
  background-color: black; /\* 'background-color' is the property, 'black' is the value \*/  
}

### **1.2 Selecting What to Style**

Selectors are how you tell CSS which HTML elements you want to style. Here are the most common types you'll use every day.

* **Universal Selector:** The universal selector (\*) selects every single element on the page. It's often used to apply a baseline style to an entire document.  
* **Type Selectors:** These select all elements of a given type. For example, div selects all \<div\> elements on the page.  
* **Class Selectors:** A class selector finds all elements with a specific class attribute. You denote a class in CSS with a period (.) followed by the class name. Classes are reusable and can be applied to many elements. Class names cannot begin with a number and should use hyphens for multiple words (e.g., .alert-text).  
* **ID Selectors:** An ID selector targets the one element with a specific ID attribute. You denote an ID in CSS with a hash symbol (\#). The most critical rule for IDs is that **an ID must be unique on a page**—you can only use it once. For this reason, IDs should be used sparingly.  
* **Grouping Selectors:** To reduce repetition, you can apply the same styles to multiple selectors by separating them with a comma (,).  
* **Chaining Selectors:** You can chain selectors together *without a space* to target elements that have *all* of the specified attributes. For example, .subsection.header will only select elements that have *both* the subsection class and the header class.  
* **Descendant Combinator:** A space between selectors acts as a descendant combinator. It selects an element only if it is a descendant (a child, grandchild, etc.) of another element. For example, .ancestor .contents will select any element with the class contents that is nested somewhere inside an element with the class ancestor.

### **1.3 Three Ways to Add CSS to HTML**

There are three methods for applying your CSS rules to an HTML document.

1. **External CSS:** This involves creating a separate .css file for your styles and linking it within the \<head\> tags of your HTML file using a \<link\> element.  
   * **Pros:** This is the cleanest and most organized method. It keeps your content (HTML) and presentation (CSS) separate and allows you to reuse the same stylesheet across multiple pages.  
   * **Cons:** It requires an extra file to be loaded by the browser.  
   * **Best Use Case:** This is the standard best practice for virtually all web projects.  
2. **Internal CSS:** This method involves placing your CSS rules inside \<style\> tags, which are then placed directly inside the \<head\> of your HTML document.  
   * **Pros:** Useful for applying unique styles to a single page without creating a separate file.  
   * **Cons:** It can make your HTML file large and messy if you have a lot of styles. You can't reuse the styles on other pages.  
   * **Best Use Case:** Quick tests or applying styles that are truly unique to a single page of a larger site.  
3. **Inline CSS:** Styles are applied directly to an HTML element using the style attribute.  
   * **Pros:** Can be useful for a highly specific style on a single element.  
   * **Cons:** It's messy, makes HTML files bloated, and is difficult to maintain. Inline styles also have high specificity, which can override other styles in unexpected ways.  
   * **Best Use Case:** Generally not recommended, but can be used for very specific, one-off style adjustments.

For consistency, organization, and maintainability, **External CSS is the recommended method** for all your projects.

### **1.4 A Few Key Properties to Start With**

Here are some of the most common CSS properties you'll use to get started.

* **color and background-color** These properties do exactly what they sound like: color sets the text color of an element, while background-color sets its background color. Values can be keywords (like red), HEX codes (\#ff0000), or RGB values (rgb(255, 0, 0\)).  
* **Typography (font-family, font-size, font-weight)**  
  * font-family sets the font for the text. It's best practice to provide a list of fonts, ending with a generic family like serif as a fallback.  
  * font-size controls the size of the text (e.g., font-size: 22px).  
  * font-weight affects the boldness of the text, using keywords like bold or numeric values like 700.  
* **text-align** This property aligns text horizontally within an element, using values like left, right, or center.  
* **Image Sizing (height and width)** You can set the height and width of an image. To maintain the image's original proportions, it's best to set one dimension (e.g., width: 500px) and set the other to auto (e.g., height: auto).

Now that you know how to write CSS and apply it, let's explore how browsers decide which styles to use when rules conflict.

\--------------------------------------------------------------------------------

## **2.0 The Rules of Engagement: Understanding the Cascade**

Have you ever written a CSS rule that didn't work and wondered why? The answer almost always lies in the "Cascade." This is the set of rules browsers use to resolve conflicting style declarations for the same element. Understanding this critical "tie-breaker" system is the key to avoiding frustration and predicting exactly how your styles will be rendered on the page.

### **2.1 Specificity: The Weight of a Selector**

Specificity is the primary way the cascade resolves conflicts. A CSS rule with a more specific selector will always take precedence over a less specific one. The hierarchy of selector specificity is as follows:

1. **ID selectors:** The most specific selector. A rule targeting an ID (e.g., \#subsection) will override rules using classes or element types.  
2. **Class selectors:** More specific than type selectors. A rule targeting a class (e.g., .list) will beat a rule targeting just the element type.  
3. **Type selectors:** The least specific selector. A rule targeting an element type (e.g., div) is easily overridden.

For example, consider an element that is targeted by two conflicting rules:

\<div class="main"\>  
  \<p class="list" id="subsection"\>This text will be blue.\</p\>  
\</div\>

/\* Rule 1: More specific (ID) \*/  
\#subsection {  
  color: blue;  
}

/\* Rule 2: Less specific (two classes) \*/  
.main .list {  
  color: red;  
}

Rule 1 wins because an ID selector is inherently more specific than any number of class selectors. The text will be blue.

Specificity is also additive. A selector's total "weight" is calculated by how many of each selector type it includes. Consider this more complex example:

\<div class="main"\>  
  \<div class="list" id="subsection"\>This text will be red.\</div\>  
\</div\>

/\* Rule 1: One ID \*/  
\#subsection {  
  color: blue;  
}

/\* Rule 2: One ID and one class \*/  
.main \#subsection {  
  color: red;  
}

Here, both rules target the same element, and both contain an ID. However, Rule 2 is more specific because it has the same number of IDs (one) plus an *additional* class selector (.main). This gives it a higher combined weight, so the text will be red.

### **2.2 Inheritance: Passing Styles Down**

Certain CSS properties, like color and font-family, are naturally "inherited." This means that if you apply them to a parent element, they will be passed down to its child elements.

However, a rule that **directly targets an element will always beat an inherited style**, regardless of the parent's specificity.

\<\!-- index.html \--\>  
\<div id="parent"\>  
  \<div class="child"\>\</div\>  
\</div\>

/\* styles.css \*/  
\#parent {  
  color: red; /\* High specificity using an ID \*/  
}  
.child {  
  color: blue; /\* Lower specificity using a class \*/  
}

In this case, the .child element will have blue text. Even though its parent has a more specific ID selector (\#parent), the rule for .child targets the element directly, so it wins over the inherited style.

### **2.3 Rule Order: The Final Tie-Breaker**

What happens if two conflicting rules have the exact same specificity? The cascade's final tie-breaker is rule order. The rule that is defined **last** in the stylesheet is the one that will be applied.

.alert { color: red; }  
.warning { color: yellow; }

If an element has both the alert and warning classes, its text will be yellow because the .warning rule comes last in the CSS file.

With the rules of the cascade understood, let's look at the essential tool for seeing these rules in action: the browser's inspector.

\--------------------------------------------------------------------------------

## **3.0 Your Secret Weapon: Inspecting HTML and CSS**

Every web developer's most critical asset is the browser's built-in developer tools. This "inspector" is essential for debugging your code, seeing how your HTML and CSS work together in real-time, and testing changes on the fly without having to constantly edit and save your files.

### **3.1 How to Open and Use the Inspector**

Opening the inspector is simple: either **right-click** on any part of a webpage and select **"Inspect,"** or press the **F12** key. This will open a panel with several tabs; for now, we'll focus on the 'Elements' and 'Styles' panels.

To inspect a specific element, you have two main options:

1. Click on the element directly in the HTML structure shown in the **'Elements' panel**.  
2. Click the **element select icon** (it looks like a square with a cursor arrow) in the top-left of the inspector, and then click on any element on the webpage itself.

### **3.2 Reading the 'Styles' Panel**

Once an element is selected, the **'Styles' panel** will show you all the CSS rules that are affecting it. This is where you can see the cascade in action.

Critically, if you see a CSS property with a **strikethrough**, it means that rule was successfully applied but has been overridden by another, more specific or later-defined rule. This is an invaluable clue for debugging why your styles aren't appearing as you expect.

### **3.3 Testing Styles Live in the Browser**

The 'Styles' panel is interactive. You can click on any property or value to change it, or click inside a selector's declaration block to add a new rule. The webpage will update in real-time with your changes. This is an extremely powerful feature for experimenting with different colors, sizes, and layouts quickly and efficiently.

**Note:** Changes made in the inspector are temporary and will be lost when you reload the page. They do not affect your source code files.

Now that you're armed with the inspector, it's time to dive into the most fundamental concept of CSS layout: the box model.

\--------------------------------------------------------------------------------

## **4.0 The Building Block of Every Page: The Box Model**

The single most important concept for understanding CSS layout is the **box model**. Every single element on a webpage—from text to images to entire sections—is treated as a rectangular box. Mastering the components of this box is the absolute key to sizing and positioning elements accurately.

### **4.1 The Four Layers of the Box**

Every box is composed of four layers, from the inside out. Understanding what each property controls is essential.

* **Content:** The innermost part, where your text, images, or other content appears. Its size can be controlled by width and height.  
* **padding:** The transparent space directly around the content. It increases the space between the content and the element's border.  
* **border:** The line that goes around the padding and content. It can have a size, style, and color.  
* **margin:** The transparent space on the very outside of the box. It creates space between this element and any adjacent elements.

### **4.2 A Better Way to Size Boxes: box-sizing**

By default, when you set an element's width and height, those dimensions apply *only* to the content area. The padding and border are then added *on top* of that size, which can make layout calculations difficult.

There is a much more intuitive way to handle this. By setting box-sizing: border-box;, you change the calculation. In this "alternative" box model, an element's specified width and height now include the padding and border. For example, if you set width: 200px; on an element with box-sizing: border-box;, the total width of the element from border-edge to border-edge will be exactly 200px, which is much easier to manage.

### **4.3 Important Margin Behaviors**

Margins have a couple of special behaviors you should know about:

* **Margin Collapsing:** When two block-level elements are stacked vertically, their adjacent vertical margins will "collapse." Instead of adding the two margins together, the browser will use only the larger of the two.  
* **Horizontal Centering:** You can easily center a block-level element horizontally inside its container by giving it a specific width and setting its left and right margins to auto. The shorthand for this is margin: auto;.

Since every element is a box, let's examine the two primary ways these boxes behave by default: as block or inline elements.

\--------------------------------------------------------------------------------

## **5.0 Box Behavior: Block vs. Inline**

Not all element "boxes" behave the same way in the normal flow of a document. HTML elements generally fall into one of two categories based on their default display property: block and inline. Understanding the fundamental difference between these two is crucial for arranging content on your page.

### **5.1 Block Elements**

Block-level elements are the major building blocks of your page layout. They have two key behaviors:

1. They always start on a **new line**.  
2. By default, they expand horizontally to fill the **full width** of their parent container.

Common block elements include \<div\>, \<p\>, and \<h1\> through \<h6\>.

### **5.2 Inline Elements**

Inline elements are designed to sit within the flow of text content. Their key behaviors are:

1. They do **not** start on a new line; they sit alongside other content.  
2. They only take up as much **width as their content requires**.

Padding and margin behave differently on inline elements and are generally not used to position them. Common inline elements include \<a\>, \<span\>, and \<strong\>.

### **5.3 The Hybrid: inline-block**

display: inline-block provides a useful middle ground between the two main types. An inline-block element will sit "in line" with other content like an inline element, but it will respect block-style properties like width, height, margin, and padding. This makes it a great tool for arranging a series of boxes side-by-side.

### **5.4 The Generic Containers: \<div\> and \<span\>**

Two of the most common HTML elements you'll use are \<div\> and \<span\>. These are **non-semantic containers**, meaning they have no meaning on their own. Their primary purpose is to act as "hooks" for your CSS selectors. By wrapping elements in a \<div\> or a \<span\>, you can give them a class or ID and then target them with styles, which is essential for grouping and positioning.

* **\<div\>**: A generic **block-level** container. It is the most common element used for grouping larger sections of a page to apply layouts to them.  
* **\<span\>**: A generic **inline-level** container. It is used to wrap small pieces of text or other inline content to apply specific styles without breaking the flow of the content.

Understanding the default block and inline behaviors is the foundation of layout. But to truly control the arrangement of these boxes side-by-side, we need a more powerful tool: Flexbox.

\--------------------------------------------------------------------------------

## **6.0 Modern Layouts with Flexbox**

Flexbox is an essential and powerful tool for modern CSS layouts. It provides an efficient and predictable way to arrange, align, and distribute space among items in a container, even when their size is unknown. As you start working with Flexbox, remember that the browser inspector is a crucial tool for visualizing how containers and items are behaving.

### **6.1 The Core Concept: Containers and Items**

A Flexbox layout is built on a simple parent-child relationship:

* **Flex Container:** This is any element that has the display: flex; property applied to it. This turns it into a flex-formatting context for its children.  
* **Flex Items:** These are the **direct children** of a flex container. Any element nested inside a flex container becomes a flex item.

### **6.2 Controlling Direction: The Two Axes**

The foundation of all flex alignment is the concept of two perpendicular axes: the **main axis** and the **cross axis**.

The flex-direction property defines the orientation of the main axis, which in turn determines how flex items are placed in the container.

* flex-direction: row; (the default): The **main axis** is horizontal (left-to-right), and the **cross axis** is vertical.  
* flex-direction: column;: The **main axis** becomes vertical (top-to-bottom), and the **cross axis** becomes horizontal.

This is a critical point: changing flex-direction also changes the behavior of other properties. For example, in a column container, flex-basis (a property related to sizing) refers to height instead of width.

### **6.3 Aligning Items Along the Axes**

Two primary properties control the alignment of flex items. Their behavior depends entirely on the flex-direction.

* **justify-content:** This property aligns items along the **main axis**. Common values include flex-start, center, flex-end, and space-between (which distributes items evenly with space between them).  
* **align-items:** This property aligns items along the **cross axis**. Common values include flex-start, center, and flex-end.

For a default flex-direction: row container, justify-content controls horizontal alignment, and align-items controls vertical alignment.

### **6.4 Controlling Space**

Here are two simple but powerful ways to manage how flex items grow and are spaced.

* **flex: 1**: This shorthand property, when applied to a flex item, tells it to grow and shrink as needed, distributing the container's free space among the items. If all items have flex: 1, they will share the space equally.  
* **gap**: This modern property is applied to the flex container and creates a consistent, specified space *between* flex items. For example, gap: 8px; will place 8 pixels of space between each item, simplifying spacing significantly.

These foundational concepts provide a powerful toolkit for building websites, and the best way to solidify them is through practice.

\--------------------------------------------------------------------------------

## **7.0 Check Your Understanding & Practice Exercises**

The best way to learn is by doing. This section gathers all the knowledge check questions and recommended hands-on exercises from the lessons into a single place. Use this to test your understanding and apply what you've just learned.

### **7.1 Knowledge Check Questions**

**Intro to CSS**

* What is the syntax for class and ID selectors?  
* How would you apply a single rule to two different selectors?  
* Given an element that has an id of title and a class of primary, how would you use both attributes for a single rule?  
* What does the descendant combinator do?  
* What are the names of the three ways to add CSS to HTML?  
* What are the main differences between the three ways of adding CSS to HTML?

**The Cascade**

* Between a rule that uses one class selector and a rule that uses three type selectors, which rule has the higher specificity?

**Inspecting HTML and CSS**

* How do you select a specific element on your page with your browser’s developer tools?  
* What does a strikethrough in a CSS declaration mean in your browser’s developer tools?  
* How do you change CSS in real time on specific elements of a web page with your browser’s developer tools?

**The Box Model**

* From inside to outside, what is the order of box-model properties?  
* What does the box-sizing CSS property do?  
* What is the difference between the standard and alternative box model?  
* Would you use margin or padding to create more space between 2 elements?  
* Would you use margin or padding to create more space between the contents of an element and its border?  
* Would you use margin or padding if you wanted two elements to overlap each other?  
* How do you set the alternative box model for all of your elements?  
* How do you center an element horizontally?

**Block and Inline**

* What is the difference between a block element and an inline element?  
* What is the difference between an inline element and an inline-block element?  
* Is an h1 block or inline?  
* Is button block or inline?  
* Is div block or inline?  
* Is span block or inline?

**Introduction to Flexbox**

* What’s the difference between a flex container and a flex item?  
* How do you create a flex item?

**Flexbox Axes**

* How do you make flex items arrange themselves vertically instead of horizontally?  
* In a column flex-container, what does flex-basis refer to?  
* In a row flex-container, what does flex-basis refer to?  
* Why do the previous two questions have different answers?

**Flexbox Alignment**

* What is the difference between justify-content and align-items?  
* How do you use flexbox to completely center a div inside a flex container?  
* What’s the difference between justify-content: space-between and justify-content: space-around?

### **7.2 Hands-On Practice**

Complete the following exercises from the CSS exercises repository.

* **From foundations/intro-to-css:**  
  * 01-css-methods  
  * 02-class-id-selectors  
  * 03-grouping-selectors  
  * 04-chaining-selectors  
  * 05-descendant-combinator  
* **From foundations/cascade:**  
  * 01-cascade-fix  
* **From foundations/block-and-inline:**  
  * 01-margin-and-padding-1  
  * 02-margin-and-padding-2  
* **Flexbox Practice:**  
  * Play **Flexbox Froggy**, a game to practice using Flexbox properties.  
* **From foundations/flex:**  
  * 01-flex-center  
  * 02-flex-header  
  * 03-flex-header-2  
  * 04-flex-information  
  * 05-flex-modal  
  * 06-flex-layout  
  * 07-flex-layout-2  
* **Project Application:**  
  * Apply CSS to the "Recipe page" you created during the HTML lessons. Use an external stylesheet and experiment with the properties you've learned.

To help you with your practice and future projects, here is a curated list of all the excellent resources mentioned in the lessons.

\--------------------------------------------------------------------------------

## **8.0 Your CSS Resource Toolkit**

This final section is a quick-reference list of all the external articles, guides, and interactive tools mentioned across the lessons. Bookmark this page—it's a valuable toolkit for your continued learning and a great place to look when you need a refresher.

### **8.1 Core Concepts & Guides**

* [The CSS Cascade (Interactive Read)](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)  
* [MDN: CSS values and units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Values_and_Units)  
* [Chrome DevTools Docs: Overview](https://developer.chrome.com/docs/devtools/overview/)  
* [Chrome DevTools Docs: Open DevTools](https://developer.chrome.com/docs/devtools/open/)  
* [Chrome DevTools Docs: View and Change the DOM](https://developer.chrome.com/docs/devtools/dom/)  
* [Chrome DevTools Docs: View and Change CSS](https://developer.chrome.com/docs/devtools/css/)  
* [MDN: CSS Box Model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)  
* [CSS Tricks: Margins](https://css-tricks.com/almanac/properties/m/margin/)  
* [MDN: Normal Flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout/In_Flow_and_Out_of_Flow)  
* [W3 schools: HTML Block and Inline Elements](https://www.w3schools.com/html/html_blocks.asp)  
* [Digital Ocean: Inline vs Inline-block Display in CSS](https://www.digitalocean.com/community/tutorials/css-display-inline-vs-inline-block)  
* [CSS Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)  
* [MDN:](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction)

### **8.2 Interactive Learning & Videos**

* [Interactive Scrim (CSS Intro)](https://scrimba.com/scrim/co92448a3b8398f244a187122)  
* [YouTube: Learn CSS Box Model In 8 Minutes](https://www.youtube.com/watch?v=rIO532_iZc4)  
* [YouTube: box-sizing: border-box (EASY\!)](https://www.youtube.com/watch?v=WlGQdgyrR_I)  
* [Interactive Guide to Flexbox](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/)  
* [Flexbox Froggy](https://flexboxfroggy.com/)

