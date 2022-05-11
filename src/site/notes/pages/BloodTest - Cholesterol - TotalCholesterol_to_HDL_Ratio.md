---
{"dg-publish":true,"permalink":"/pages/blood-test-cholesterol-total-cholesterol-to-hdl-ratio/","dgHomeLink":true,"dgPassFrontmatter":false}
---

## TotalCholesterol-to-HDL Ratio




```dataviewjs

let pg1 = dv.pages("#BloodTest").where(b=>b.TotalCholesterol & b.HDL ).sort(b => b.Date);
const data2 = pg1.map(b=>b["TotalCholesterol"]/b["HDL"]);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"TotalCholesterol to HDL Ratio", x:  pg1.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values}
];

var layout = {title:"TotalCholesterol to HDL Ratio"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "TotalCholesterol_to_HDL_Ratio")

```


