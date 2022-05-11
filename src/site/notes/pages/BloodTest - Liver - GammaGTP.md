---
{"dg-publish":true,"permalink":"/pages/blood-test-liver-gamma-gtp/","dgHomeLink":true,"dgPassFrontmatter":false}
---


## GammaGTP


```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.GammaGTP).sort(b => b.Date);
 
//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Phenotypic", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.GammaGTP.values},
];

var layout = {title:"GammaGTP"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "GammaGTP")

```
