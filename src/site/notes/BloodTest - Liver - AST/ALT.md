---
{"dg-publish":true,"permalink":"/blood-test-liver-ast/alt/","dgHomeLink":true,"dgPassFrontmatter":false}
---


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

window.renderPlotlyImage(this.container, data, layout, config, "ASTALT")