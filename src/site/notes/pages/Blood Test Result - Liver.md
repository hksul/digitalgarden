---
{"dg-publish":true,"permalink":"/pages/blood-test-result-liver/","dgHomeLink":true,"dgPassFrontmatter":false}
---


[BioHacking MOC](BioHacking%20MOC.md)
[Blood test MOC](../pages/Blood%20test%20MOC.md)


---

 

# Liver Panel
 
## AST/ALT


```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.AST).sort(b => b.Date);
let pg2 = dv.pages("#BloodTest").where(b=> b.ALT).sort(b => b.Date);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"AST", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.AST.values},
 {name:"ALT", x:  pg2.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg2.ALT.values}
];

var layout = {title:"AST & ALT  "};
var config = {displaylogo:false};

window.renderPlotly(this.container, data, layout, config)

```


<div style="page-break-after: always;"></div>


## ALP



```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.ALP).sort(b => b.Date);
 
//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Phenotypic", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.ALP.values},
];

var layout = {title:"ALP"};
var config = {displaylogo:false};

window.renderPlotly(this.container, data, layout, config)

```


<div style="page-break-after: always;"></div>


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

window.renderPlotly(this.container, data, layout, config)

```

---
