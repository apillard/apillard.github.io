# [apillard.github.io](https://apillard.github.io)

Currently this site is serving as a demo for my Multiple Property Live Scatter Chart.

The features of this chart were inspired by [productchart.com](http://www.productchart.com/smartphones/). I've been shopping for cars halfway seriously, but I don't have a good idea of specifically what I want. There are many comparison tools for cars out there [like this one](http://www.edmunds.com/car-comparisons/). But they all expect you to select only a handful of specific models to compare in a table output. Having used ProductChart previously, I felt like it would be a good fit for vehicle data. Having a large chart with many models populated could help narrow down the field. Once you have a small set to work with, you could move from the chart filtering to the existing style of comparison tool.

As is, the current scatter chart has nothing to do with vehicles, but it could be extracted to a generic component and then fed with vehicle data. All data points are generated with 4 numerical properties, A, B, C and D. And you can change the scatter plot axes to use any of these properties as well as filter the data set on any of the 4.

As far as technology selection goes, JS was very appealing to me as a first GitHub project. The barrier to entry is super low. You pretty much only need a browser and a text editor to get started. I didn't have to worry about installing a compiler, or setting up a local server or anything. Testing worked great just using a file:// URI in Chrome to point to my local copy.

##Development Process
After I had formed my idea for a "ProductChart for vehicles" and identified Chart.js as a good technology fit, the Chart.js sample code really got me started on programming. Their [docs site](http://www.chartjs.org/docs/) leaves you wanting, with no documentation at all for a scatter chart. Fortunately there was [a nice example](https://github.com/chartjs/Chart.js/blob/master/samples/scatter-multi-axis.html) that I used as base to get me started with a basic scatter chart. From there I modified the code to support the multiple properties and live data updates. The css and html portions are fairly simple. And while working on it, I never felt like things got to a scale where I had trouble keeping track of where things are, so I just left everything in a single html file. If this project expands splitting files into html, css and js would probably be wise.

##Technologies Used
* [Github](https://www.github.com) - This was my first ever GitHub project, and my first use of Git on a personal project. The GitHub for Windows client abstracted away a lot of the Git operations though. I would like to move to a Git command line client to learn more about Git.
* [Chart.js](http://www.chartjs.org/) - This library has some very nice APIs for live data updates and custom tooltips. It is also the standard charting library in use at UP where I work, and I hadn't had a chance to use it yet.
* [JQuery](https://jquery.com/) - For a simple project I'd thought I'd forgo the Angular that's used at UP and go for something simpler. The direct DOM manipulation was a nice change of pace. Previous to this project I had only dabbled with JQuery.
* [JQuery UI](https://jqueryui.com/) - I needed some slider controls, and JQuery UI provided. Seemed like the obvious choice when I was using JQuery already. Especially when I'm not being too picky about the visuals.
* [Visual Studo Code](https://code.visualstudio.com/) - While I'm trying out new things, may as well try a new text editor too.

##Future Enhancements
* Replace random data with actual car data from a vehicle API like [this one](http://developer.edmunds.com/api-documentation/vehicle/)
* Add non-numeric properties that can be filtered via radio or checkbox controls
* Integrate axis property selectors into axis labels
* Update chart immediately on control change and remove "Update Chart" button
* Extract chart to a component instead of being coded directly on the web page
* Improve tooltips to include links, pictures, other non-text data (May require forking chart.js)
* Localize library references instead of only relying on the CDN
* Use thumbnails instead of just colored dots for data points (Not sure how useful this would be given the small size of thumbnails on ProductChart but, it's worth experimenting with) (May require forking chart.js)
* Improve animations when data is removed or added to the chart. When data moves around it's got a nice default, but when added or removed it's very abrupt. A fade-in/fade-out effect might be nice.
* See how much of the JQuery DOM manipulation I can remove. I imagine most of it could be replaced with native JS features.
* Come up with a better name. "Multiple Property Live Scatter Chart" is quite the mouthful
