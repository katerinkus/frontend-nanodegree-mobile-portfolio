Part 1
==

File list
--
1. *readable-index.html* - the HTML file you can follow
2. *index.html* - minified html
3. *smartphones.css* - css file for portrait orientation
4. *print.css* - css file for print media
5. *perfmatters.js* - original js file
6. *perfmatters.min.js* - minified js file

Changes to the Mobile website
--
1. Moved Google Analytics script into the end of `<body>` element and made the scipt `async`. My score increased by 5 points. Google Analytics is not a necessary script to render, therefore it should be loaded asynchronously from the content. Otherwise, it becomes render-blocking.
 - Desktop: 91
 - Mobile: 78
2. Removed Google Fonts. Visually, I saw little difference between Open Sans and Arial. However, the score increased by whooping 10 points for mobile! If I was very keen on getting a specific font because it provided a visual or branding aesthetic, I would use this tutorial [here]("https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/webfont-optimization").
 - Desktop: 91
 - Mobile: 88-90
3. Added a media query for css links in html (media = "print"). It did not impact phones significantly and helped raise the desktop score by a few point.
 - Desktop: 94
 - Mobile: 87
4. Added a media query for phones in portrait. That did not change mobile score. However, desktop score increased by a few points. At this point mobile and desktop only have one render-blocking css file: `styles.css`.
 - Desktop: 96
 - Mobile: 87
5. Compressed profile image and pizzeria image.
 - Desktop: 95
 - Mobile: 89
6. Inlined CSS. Personally, I would never use this technique unless the project was literally one page (like in this project). Worked well here though by reducing the number of CRP resources and paths.
 - Desktop: 96
 - Mobile: 98
7. Minified HTML. 2kb reduction.

Notes
--
If I could control the server, I would set `Cache-Control` expiration dates and compression.
Decided against further image compression, the files are already tiny and look really bad when compressed any further.

Part 2
==

Changes
--
1. Layout thrashing issue. Changed the for loop in `updatePositions()` function. I took out `scrollTop` values out of the for loop into a variable. This way the function does not have to get the same value for each item.
2. Compositing and painting. I put floating pizzas on a separate layer to reduce painting. Now the only painted thing is the scrollbar. To do that I added two properties to the css file for the `mover` element:  `will-change` and `transform` (for unsupported browsers).
3. JavaScript & layout optimization. I changed the `changePizzaSizes(size)` function: Before the resize took 273ms, now it takes around 1ms. I took the for loop calculations for the new width out of the for loop function. Since all pizzas are the same size to begin with, I only need calculations for one pizza. I then apply that to the rest.
