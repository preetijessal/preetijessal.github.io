## Website Performance Optimization portfolio project

To inspect the site on your phone, you can run a local server for this do following steps:
Install python on your computer Visit link https://www.python.org/downloads/windows/

Go to command line prompt
c:\> cd copy the path of your project and just paste it after c:\> cd 
c:\Users\Lenovo\Desktop\udacity\project> python -m http.server (command for windows)
Then install ngrok on the top top-level of your project directory
Open command line window of ngrok and type following command
Type ngrok.exe http 8000
It will gives you a public URL then visit https://developers.google.com/speed/pagespeed/insights/ and paste that url address you will get your score and try running it through PageSpeed Insights or you can also visit the following link to Check optimization score on github https://preetijessal.github.io/

Folders Description:

src directory following files and folders:
`index.html`: unoptimized html file having low score
`css` and views/css folder: contains unminified css files
`js` folder contains the unuglified `.js` files.
`views/js/main.js` is an optimized js file. It is optimized to obtain the second goal- getting rid of **Jank**.

`dist` folder contains css, js and images folder
`css` folder contains all minimised css files 
`js` folder includes uglified js files which are main.min and perfmatters.min


**Grunt Files :** `Gruntfile.js` and `package.json`

**`index.html`** is an optimized html file which is also the entry point of the project. It is optimized to obtain the **PageSpeed** goal.


## Optimization Details :
Changes done in inde.html file are:
Added `media="print"` attribute to the `css/print.css` 
* Put the `<script></script>` at the bottom of `body` element.
* Optimized Google fonts by adding the WebFont Config Script.
* Added `async` attribute to two `.js` files to load asynchronously.
* Used **Grunt** to :
    - minify `.css`
    - uglify `.js`
    - compress images

After optimization reached Desktop Score: 93/100 and mobile 91/100
**Achieving 60 fps in the pizza.html page** 
* Changed document.queryselector to document.getElementById() to increase scroll and page rendering.
* Changed *queryselectorAll to *getElementsByClassName
* Change CSS** for `.mover` : Add `transform: translateZ(0)`, `will-change: transform`, `transform translate3d(0,0,0)` and   `backface-visibility: hidden`.
* Deleted the determineDx function 
* Removed the `sizeSwitcher()` function and add the sizing `switch` case inside the `changePizzaSizes()` function which sets the percentage width required 
  according to changes in sliding bar.
* Declared the variables outside the loop to reduce loop complexity.
* Declared the variables querying the DOM everytime outside the loop. 
* Made phase for sin wave an array `phase_array`to do 5 calculations once and then use it in for loop.
* Precalculate the variable `scr` to reduce activity in the loop
* Used `TranslateX` instead of `basicLeft` to repositioned pizzas.
* Have made some changes according to the discussions in the forum.
* Used `ticking` to make sure the updatePositions function isn't firing unnecessarily.
* Move `items` at the bottom of the page to stop updatePositions from re-defining items on every scroll event

