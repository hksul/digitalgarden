```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.AST && b.ALT).sort(b => b.Date);

const data2 = pg.map(b=>8*b["ALT"]/b["AST"]+24);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Mortality Rate", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values},
];

var layout = {title:"Hepatic steatosis index (HSI) [>=36, <30] - Assuming Flat BMI of 24"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "HSI")

```