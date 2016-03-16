#title:  Simple way to add zoom to d3.js chart
##date:  2016-03-16 11:02:36
##sub-folder:  d3js

From [Coderwall](https://coderwall.com/p/psogia/simplest-way-to-add-zoom-pan-on-d3-js)

I needed to add zoom/pan on d3.js visualisation. After a painful search on Google, I finally found a simple way to do it.

d3.js has everything to do it with only a few lines of code.

You just need to create a g element as first child of the SVG element and connect d3.behavior.zoom() behavior.


```
var svg = d3.select("body")
  .append("svg")
  .attr("width", "100%")
  .attr("height", "100%")
  .call(d3.behavior.zoom().on("zoom", function () {
    svg.attr("transform", "translate(" + d3.event.translate + ")" + " scale(" + d3.event.scale + ")")
  }))
  .append("g")
```
