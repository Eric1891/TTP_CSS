<img src="https://i.imgur.com/Bzkqs5I.png" alt="drawing" width="100"/>

# CSS (Cascading Style Sheets)

## Meeting Process
- Pre-requisites
    1) Install Visual Studio Code
    2) Install the `Live Server` VSCode Extension
- Topics we'll be going over
    - > Note: Create index.html file
    - **Internal CSS Styling**:
        - `<style>` element: It contains CSS, which is applied to the contents of the document
            - index.html 
            ```
            <!-- Inside of the Head element -->
            <style>
                p {
                    color: red;
                }
            </style>
            <!--  -->
            
            <!-- Inside of body element -->
            <p>Hello TTP!</p>
            <!--  -->
            ```
    -  **Local CSS Styling**:
        -  Description: adding CSS to `style=""` attribute of an HTML element
            -  index.html
            ```
            <!-- Inside of body element -->
            <p style="color: red">Hello TTP!</p>
            <!--  -->
            ```
    - **External CSS Styling (most recommended)**:
        - Description: creating a CSS file (to input all CSS styling for your HTML elements) and connecting the two files together.
            - > Note: create a folder named `style` and inside of this folder, create a file named `style.css`
            - index.html
            ```
            <!-- inside of head element - connect this html file to our style.css file in our style folder -->
            <link rel="stylesheet" href="style/style.css">
            <!--  -->
            
            <!-- Inside of body element -->
            <p>Hello TTP!</p>
            <!--  -->
            ```
            - style.css
            ```
            
            /* p - selector */
            /* color: - CSS property */
            /* red; - CSS property value */
            p {
                color: red;
            }
            ```
    > Note: from now on, we're going to be using our `style.css` file for styling our `index.html` file
    - **Selectors: Element**:
        - Description: selects all elements with the specified element name (and gives them the specified spelling)
            - index.html
            ```
            <h1>CSS Selectors</h1>

            <h3>Article 1</h3>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi doloribus nostrum eos est enim voluptatem repellat, provident quasi consequatur asperiores libero nam repudiandae iste voluptatibus ab ipsa. Quam, accusamus temporibus!</p>

            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi doloribus nostrum eos est enim voluptatem repellat, provident quasi consequatur asperiores libero nam repudiandae iste voluptatibus ab ipsa. Quam, accusamus temporibus!</p>
            ```
            - style.css
            ```
            body {
                font-size: 34px;
            }

            p {
                color: blue
            }
            ```
        - More practice
            - index.html
            ```
            <h1>CSS Selectors</h1>

            <h3>Article 1</h3>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi doloribus nostrum eos est enim voluptatem repellat, provident quasi consequatur asperiores libero nam repudiandae iste voluptatibus ab ipsa. Quam, accusamus temporibus!</p>

            <h2>Article 2</h2>

            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi doloribus nostrum eos est enim voluptatem repellat, provident quasi consequatur asperiores libero nam repudiandae iste voluptatibus ab ipsa. Quam, accusamus temporibus!</p>
            ```
            - style.css
            ```
            body {
                font-size: 34px;
            }

            p {
                color: blue
            }

            h1, h2, h3 {
                color: green;
            }
            ```
    - Selectors: Classes
        - Description: selects elements with a specific class attribute (can be used in multiple elements)
            - index.html
            ```
            <h1>Movies</h1>

            <p class="movies">My Favorite movies are Spider Man, Batman, Hulk ...</p>

            <h2 class="shows-title">Shows</h2>

            <p>My Favorite shows are Grey's Anatomy, Flash, ...</p>
            ```
            - style.css
            ```
            h1 {
                font-style: italic;
                font-size: 40px;
            }

            .movies {
                color: aqua;
            }

            .shows-title {
                color: pink;
            }
            ```
    - Selectors: ID
        - Description: uses the id attribute of an HTML element to select a specific element (are unique to one specific element)
            - index.html
            ```
            <h1 id="recipe-title">Recipes</h1>

            <h2 id="desserts">Favorite Desserts</h2>
            <p>Chocolate Ice cream</p>
            <p>Vanilla Ice Cream</p>
            ```
            - style.css
            ```
            #recipe-title {
                text-transform: uppercase;
            }

            #desserts {
                text-align: center;
            }
            ```
    - Selectors: Universal
        - Description: selects elements of any type
            - index.html
            ```
            <main>
                <h2 class="languages">Programming Languages</h2>

                <ol>
                    <li>Python</li>
                    <li>Javascript</li>
                    <li>HTML</li>
                </ol>
            </main>
            ```
            - style.css
            ```
            * {
                text-align: center;
                font-family: monospace;
            }

            li {
                color:bisque;
            }

            .languages {
                text-transform: uppercase;
            }
            ```
    - Colors
        - Description: Discuss various colors properties in CSS
            - index.html
            ```
            <main>
                <h2 >Article 1</h2>

                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Distinctio nemo debitis minus? Consectetur hic, nesciunt atque inventore nobis rem amet eos possimus?</p>
            </main>

            <main>
                <h2 >Article 2</h2>

                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Distinctio nemo debitis minus? Consectetur hic, nesciunt atque inventore nobis rem amet eos possimus?</p>
            </main>
            ```
            - style.css
            ```
            body {
                font-size: 24px;
                font-family: monospace;
                line-height: 1.5;
                background-color: papayawhip;
                /* rgb - red green blue */
                color: rgb(0,0,0);
            }

            p {
                /* rgba - red green blue alpha --> alpha = transperancy (1 highest, 0 lowest)*/
                color: rgba(0,0,0,.5);
                text-align: center;
            }

            h2 {
                /* Hex values are actually just a different way to represent RGB values. Instead of using three numbers between 0 and 255, you use six hexadecimal numbers. Hex numbers can be 0-9 and A-F. */
                color: #35358c;
            }
            ```
    - Units & Sizes:
        - Description: `px = pixels` ---> are an absolute unit, so when you set the font size to 24 pixels, it's going to be 24 pixels (won't change if a user changes the font size in their browser). `rem` ---> are relative units that are based on the document's font-size. Most browsers default font size is 16px. Thus, if the default size is 16px, then 1rem = 16px (2rem = 32px). This means, that depending on whether a user changes the default font size of their browser, `rem` will adopt to those changes, but `pixels` will not. Thus, when dealing with font-sizes, `rem` is the recommended way of unit sizes.
            - index.html
            ```
            <h1>Pixels Font size</h1>
            <h1>REM Font size</h1>
            ```
            - style.css
            ```
            /* Go to (on Chrome browser) --- Settings --> Appearance --> Font Size */
            h1 {
                font-size: 32px;
            }

            /* h1 {
                font-size: 2rem;
            } */
            ```
    - Box Model:
        - Description: a box that wraps around every HTML element. It consists of: margins, borders, padding, and the actual content
                - **Content**: It is the actual content of an element, such as text, images, or other HTML elements.
                - **Padding**: It is the space between the content and the element's border.
                - **Border**: It is a line that surrounds the padding and content of an element. The border can be customized using properties like border-width, border-color, and border-style.
                - **Margin**: It is the space between the element's border and other elements on the page. 
            - index.html
            ```
            <header class="container">Box Model</header>

            <main class="container">Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde culpa hic mollitia suscipit natus molestiae beatae, cum inventore sequi. Excepturi eligendi, numquam quod recusandae at fugit maiores nulla voluptate veritatis?</main>
            ```
            - style.css
            ```
            /* Universal selector that selects all elements on the page*/
            * {
                /* These properties below make you start with a clean slate and have more control over the styles applied to your elements.  */

                /* sets the margin of all elements to 0, removing any default margin applied by the browser. */
                margin: 0;

                /* It sets the padding of all elements to 0, removing any default padding applied by the browser. */
                padding: 0;

                /* This property changes the box model behavior to border-box, which means that the width and height of an element include the content, padding, and border, but exclude the margin. This ensures consistent sizing and spacing of elements across different browsers. */
                box-sizing: border-box;
            }
            /*  */

            .container {
                border: 2px dotted red;
                border-right: 2px dotted blue;
                border-bottom: 2px dotted green;

                /* default browser font size = 16px ---> 1.5rem = 24px (1.5 * 16)*/
                font-size: 1.5rem;

                /* em - unit measurement ---> will scale proportionally based on the font size of the .container element itself, allowing for a responsive and adaptable layout. */

                /* we know font-size = 1.5rem (24px) */
                /* 1.5em = 36px ----> 1.5 * 24px (font-size - 1.5rem) */
                /* Thus, em will scale based on the font-size we have declared in the class "container" here */
                margin: 1.5em;

                /* You can also use margin to specify the margin of all four sides */
                /* margin: 1.5em 1em 1.5em 1em;  */
                /* top: 1.5em, right: 1em, bottom: 1.5em, left: 1em */

                /* or, you can specify the margin sides individually */
                /* margin-top: 1.5em;
                margin-bottom: 1.5em;
                margin-left: 1em;
                margin-right: 1em; */

                padding: 1.5em;
                /* You can do this with padding as well to specify all 4 sides */
                /* You can also separate all sides separately like with margin */

                /* Outline: used to create a visible outline around an element, typically used to highlight or focus on an element. It does not take up any space in the box model. If you go to the box model, you don't see it.*/
                outline: 5px solid purple;

                outline-offset: 5px; /* Used to offset outwards or use -5px to offset inwards the border */
            }
            ```
    - Typography:
        - Description: Review some common text properties.
                - Review more `font-family` [fonts here](https://fonts.google.com/)
            - index.html
            ```
            header >CSS Typography</header>

            <main >Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde culpa hic mollitia suscipit natus molestiae beatae, cum inventore sequi. Excepturi eligendi, numquam quod recusandae at fugit maiores nulla voluptate veritatis?</main>
            ```
            - style.css
            ```
            body {
                font-size: 2rem;
                font-family: monospace;
            }

            main {
                text-decoration: underline;
                text-transform: uppercase;
                text-align: left;
                text-indent: 2em;
                line-height: 1.5;
                letter-spacing: .1em;
                word-spacing: .5em;
                font-weight: 600;
                font-style: italic;
            }
            ```
