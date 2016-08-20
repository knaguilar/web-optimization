# Website Performance Optimization portfolio project

## Getting started
1) Download all the files into your local computer and open index.html in a browser.

or

2) Go to https://knaguilar.github.io/web-optimization/ to view it online.

## Optimizations made:

### index.html
In order to make it get a score higher than 90 on PageSpeed I did the following optimizations:
- inlined css
- async google analytics
- added media="print" to print.css
- moved javascript to the bottom of body
- resized pizzeria.jpg
- removed google fonts

### views/js/main.js
Two main changes had to happen here: pizza slider had to resize in less than 5ms & scrolling had to run at 60 fms.

Pizza Slider Optimizations:
Inside changePizzaSizes, I optimized the for loop by removing unnecessary work such as determineDx and newwdith. The newwidth that would be used can from moving sizeSwitcher's switch options into changePizzaSizes and changing the sizes into percentages rather than px. Also, I saved document.querySelectorAll(".randomPizzaContainer") in a variable since it was being used often.

As for scrolling, inside updatePosition I changed querySelectorAll to getElementsByClassName as well as inside changePizzaSizes. I also noticed a few variables that kept being repeated inside the for loop and I calculated and stored them outside such as scrollNum = document.body.scrollTop / 1250, phase, elem and pizzasDiv; I saved phase inside an array that would be used to do some calculations inside the for loop. Lastly, I decreased the number of items to 20 rather than items.length = 200 and calculated the number of pizzas that were needed to fill the screen, based on the browser resolution.