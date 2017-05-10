Changes to the Mobile website
==
1. Moved Google Analytics script into the end of `<body>` element and made the scipt `async`. My score increased by 5 points. Google Analytics is not a necessary script to render, therefore it should be loaded asynchronously from the content. Otherwise, it becomes render-blocking.
 - Desktop: 91
 - Mobile: 78
2. Removed Google Fonts. Visually, I saw little difference between Open Sans and Arial. However, the score increased by whooping 10 points for mobile! If I was very keen on getting a specific font because it provided a visual or branding aesthetic, I would use this tutorial [here]("https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/webfont-optimization").
 - Desktop: 91
 - Mobile: 88-90
3. Added a media query for css links in html (media = "print"). It did not impact phones significantly and helped raise the desktop score by a few point.
 - Desktop: 94
 - Mobile: 87
4. Added a media query for phones. As expected that did not change mobile score. However, desktop score increased by a few points.
 - Desktop: 96
 - Mobile: 87
