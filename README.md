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


**Page Speed Optimizations :**
* **Removed Render Blocking CSS** : 
    - Used `grunt-critical` to find the minimum set of blocking CSS, or the critical CSS and inline it inside `index.html`.
    - Added `media="print"` attribute to the `css/print.css` 
* Put the `<script></script>` at the bottom of `body` element.
* Optimized Google fonts by adding the WebFont Config Script.
* Added `async` attribute to two `.js` files to load asynchronously.
* Used **Grunt** to :
    - minify `.css`
    - uglify `.js`
    - compress images

After optimization reached Desktop Score: 93/100 and mobile 91/100
**Achieving 60 fps in the pizza.html page** 

* Change CSS** for `.mover` : Add `transform: translateZ(0)`, `will-change: transform`, `transform translate3d(0,0,0)` and   `backface-visibility: hidden`.
* Deleted the determineDx function 
* Removed the `sizeSwitcher()` function and add the sizing `switch` case inside the `changePizzaSizes()` function which sets the percentage width required 
  according to changes in sliding bar.
* Declared the variables outside the loop to reduce loop complexity.
* Declared the variables querying the DOM everytime outside the loop. 
* Use *getElementByID* and *getElementsByClassName* instead of *querySelector* and *querySelectorALL* to increase scroll and page rendering..
* Made phase for sin wave an array `phase_array`to do 5 calculations once and then use it in for loop.
* Precalculate the variable `scr` to reduce activity in the loop
* Used `TranslateX` instead of `basicLeft` to repositioned pizzas.
* Have made some changes according to the discussions in the forum.
* Used `ticking` to make sure the updatePositions function isn't firing unnecessarily.
* Reduced pizzas from 200 to a dynamically calculated value using viewport height.
* Move `items` at the bottom of the page to stop updatePositions from re-defining items on every scroll event

### Getting started

#### Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

#### Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>
