---
{"dg-publish":true,"permalink":"/pages/blood-test-etc-ferritin/","dgHomeLink":true,"dgPassFrontmatter":false}
---


### Ferritin


```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.Ferritin).sort(b => b.Date);
 
//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Ferritin", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.Ferritin.values},
];

var layout = {title:"Ferritin"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "Ferritin")

```

