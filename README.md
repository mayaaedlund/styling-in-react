# A Comparison of Common Styling Methods in React

Styling in React applications is a critical aspect of developers that impacts maintainbility, scalability, and collaboration. This study examines four popular styling methods - Normal CSS, CSS Modules, CSS-in-JS and Tailwind CSS. The aim is to compare them and discuss their advantages and disadvantages to provide recommendations for different types of projects.



# Normal CSS: A Simple Approach to Styling React Applications

Normal CSS involves separation style in a `.css` file and linking them to React components using `className`.

**Pros**
- Clear Separation: Maintains a distinct separation between JavaScript and styling, simplifying collaboration between coders and designers.
- Offers full range of CSS features, including media queries and animation.
- Simplicity: Ideal for small projects

**Cons**
- Global Scope Issues: Styles applied in one part of the application may affect others.
- Performance Overhead: Large CSS files can increase initial page load times. 


**Example:**
![NormalCSS](normalcss1.png)
![NormalCSS](normalcss2.png)


# CSS Modules: Scoped and Maintainable Styles
CSS Modules is almost like normal CSS, except the styles are only accessible in the module if its explicity imported, ensuring their is no global scope issues. 

**Pros**
- Scoped Styles: Avoids class name collisions.
- Organized Codbase: Better suited for large project because you can organazie your code more efficiency. 

**Cons**
- Not as lightweight as traditional CSS due to added modularity features. 

**Example:**
![CSSmodules](cssmodules1.png)
![CSSmodules](cssmodules2.png)

# Tailwind CSS: Utility-First Styling for Rapid Development
An utility first CSS-framework which allows you to put designs directly on to HTML-element. Instead of writing your CSS in separate files, you can use classes that representares rules. The rules are already made and you don't need to write your own CSS styles. 

**Pros**
- Rapid Development, eliminates the need to write your own CSS-styles.
- Consistency, enforces a consistens design system

**Cons**
- Readability, can be hard to read and understand, code can be longer and more complex
- Complex customization: can be challenging to customize Tailwind CSS to meet unique design requirements. To adjust the default settings might require deep changes in the configuration file.

**Example**
![tailwind](tailwind.png)



# CSS-in-JS: Dynamic and Component-Specific Styles
Styled components allows you to define component-specific styles directly within JavaScript files using templates. 

**Pros**
- Scoped Styles: Elimination conflicts though styles are scoped to the component.
- Clean Codebase: Reducing the need for external files.

**Cons**
- Requires time to learn.
- Inline styles can result in larger bundle sizes.


# How Do Styling Method Affect Page Loading Time?

How we structure our styling impacts the React bundle size. The larger the `main.css`, the longer it will take to load and parse.

**Normal CSS** 
Normal CSS is performant because it doesn’t involve additional JavaScript or modules. Styles are loaded directly from CSS files, which makes it fast for smaller projects. However, as the project grows and the CSS files become larger, the loading time can increase.

**CSS Modules** 
CSS Modules help reduce the risk of unnecessary styles being loaded onto a page, as only the styles that are imported are used. This leads to performance optimization, especially in larger applications. However, even though styles are scoped to specific modules, there can still be a slight performance overhead compared to normal CSS.

**Tailwind CSS** 
Tailwind CSS is optimized to reduce unused styles through its "purging" method, meaning that only the classes actually used in the project are included in the final CSS file. This can decrease both file size and loading time. However, if purging is not correctly configured, it may result in larger CSS files.

**CSS-in-JS** 
CSS-in-JS libraries like Styled Components generate dynamic, component-specific styles that are only loaded when the component itself is rendered, which can reduce loading times. On the other side, CSS-in-JS can negatively impact performance because all styles are generated within JavaScript, rather than being in separate CSS files.


# Recommendations

| **Method**       | **Pros**                         | **Cons**                            | **Best for**                         |
|-------------------|----------------------------------|-------------------------------------|---------------------------------------|
| Normal CSS        | Simple, full CSS features       | Global scope issues, performance    | Small projects                       |
| CSS Modules       | Scoped styles, organized code   | Setup complexity                    | Medium to large projects             |
| Tailwind CSS      | Rapid development, consistency  | Readability, customization          | Consistent design, rapid prototyping |
| CSS-in-JS         | Dynamic styling, scoped styles  | Learning curve, larger bundle size  | Dynamic components, experienced team |


Based on the information, different styling methods are more suitable for various types of projects. For instance, Normal CSS works well for smaller projects due to its simplicity and the ease of making quick styling changes. However, it is less ideal for larger projects because of its global scope, which can lead to conflicts and difficulties in managing styles across the project.

For medium to large projects, CSS Modules is a better option, as it avoids the global scope issues by allowing scoped, modular styles. Additionally, it promotes better organization and maintainability of the codebase.

Tailwind CSS is particularly well-suited for e-commerce platforms or projects requiring rapid prototyping and a consistent design system. Its utility-first approach makes it easy to build designs quickly while maintaining consistency across the application.

Lastly, CSS-in-JS is a great choice for projects that require dynamic styling and reusable components. It’s especially effective in teams that have prior experience with this methodology, as it integrates styling directly within the JavaScript code, providing flexibility and powerful features like conditional styling.


# References:

## Normal CSS
- [MDN: What is CSS?](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/What_is_CSS)
- [BBC Bitesize: Introduction to CSS](https://www.bbc.co.uk/bitesize/guides/zggs2nb/revision/3)

## CSS Modules
- [Create React App Docs: Adding a CSS Modules Stylesheet](https://create-react-app.dev/docs/adding-a-css-modules-stylesheet/)
- [GitHub: CSS Modules](https://github.com/css-modules/css-modules)

## Tailwind CSS
- [Tailwind CSS Official Site](https://tailwindcss.com/)
- [CSS Tricks: An Introduction to Tailwind CSS](https://www.builder.io/blog/tailwind-css-tips-and-tricks)

## CSS-in-JS
- [Styled Components](https://styled-components.com/)
- [Better Programming: All You Need to Know About CSS-in-JS](https://betterprogramming.pub/all-you-need-to-know-about-css-in-js-984a72d48ebc)

## Other
- [Dev.to: Tailwind vs CSS-in-JS vs CSS Modules](https://medium.com/@ignatovich.dm/css-modules-vs-css-in-js-vs-tailwind-css-a-comprehensive-comparison-24e7cb6f48e9)

- [Page Loading Time](https://blog.theashishmaurya.me/how-to-minimize-react-bundle-size-for-faster-loading-times)



  
