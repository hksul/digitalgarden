---
{"dg-publish":true,"permalink":"/pages/blood-test-etc-uric-acid/","dgHomeLink":true,"dgPassFrontmatter":false}
---


### UricAcid


```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.UricAcid).sort(b => b.Date);
 
//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"UricAcid", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.UricAcid.values},
];

var layout = {title:"UricAcid"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "UricAcid")

```

