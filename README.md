# PSE Project - Fix explanation 
Correcting website orientation:
1. Located and commented-out the following lines of CSS from Footer.html template file (lines 92-102): 

`<!--<style>
        body {
           width: 100%;
           height: 100%;
           -moz-transform: rotate(180deg);
           -webkit-transform: rotate(180deg);
           -ms-transform: rotate(180deg);
           -o-transform: rotate(180deg);
           transform: rotate(180deg);
        }
      </style>-->`

Correcting stylesheet loading issues: 
1. Resolved `(500) Server Errors` with Stylesheet calls and the `Uncaught (in promise) Error: Syntax error, unrecognized expression: [data-"Times New Roman"-dropdown]` console errors by re-adding the missing `_header.scss_` template file in the `assets\scss\layouts\header` directory from a base version of Cornerstone 1.9.4. 

2. Bundled theme after these corrections were made to test out fixes on website. After the modified theme was applied to my sandbox store (dantemunoz.com), I noticed that the stylesheet was now loading; however, the carousel and product images were failing to load (spinning loading wheel). At this point, console was returning a 404 for theme-bundle.main.js

Correcting Product Grid and the Shop by Price/Faceted Search Panel:
1. Located the chunk of commented-out code in the `_body.scss` template file. Found in `\assets\scss\layouts\body\`

Correcting Carousel and Product Image loading issues:
1. Downloading clean version of Long John Silveys 1.9.4 theme 
2. Re-performing fixes mentioned above (website orientation & Stylesheet issues)
3. Theme bundle attempt
4. Receiving error when bundling

`events.js:141
throw er; // Unhandled 'error' event
^
Error: ENOENT: no such file or directory, open 'D:\xxxxx\xxxxx\stencil\assets\dist\theme-bundle.chunk.0.js'
at Error (native)`

5. Found post: https://github.com/bigcommerce/stencil-cli/issues/325 & STENCIL-3652
6. Ran Stencil Bundle 2-3 times until the bundle is complete 
7. Re-added the `\dist` folder into the resulting .zip file's `\assets` directory so that the missing dist folder is included.
8. Go to BigCommerce and upload theme. 
