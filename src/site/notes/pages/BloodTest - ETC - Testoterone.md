---
{"dg-publish":true,"permalink":"/pages/blood-test-etc-testoterone/","dgHomeLink":true,"dgPassFrontmatter":false}
---


### Testoterone


```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.TestosteroneTotal).sort(b => b.Date);
 
//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Testoterone", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.TestosteroneTotal.values},
];

var layout = {title:"Testoterone"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "Testoterone")

```

