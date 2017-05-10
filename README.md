Changes to the Mobile website
==
1. Moved Google Analytics script into the end of `<body>` element and made the scipt `async`. My score increased by 5 points. Google Analytics is not a necessary script to render, therefore it should be loaded asynchronously from the content. Otherwise, it becomes render-blocking.
 - Desktop: 91
 - Mobile: 78
2. Removed Google Fonts. Visually, I saw little difference between Open Sans and Arial. However, the score increased by whooping 10 points for mobile!
 - Desktop: 91
 - Mobile: 88-90
