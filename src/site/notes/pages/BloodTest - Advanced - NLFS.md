```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.AST && b.ALT).sort(b => b.Date);

const data2 = pg.map( b=>-2.89 + 0.04*b["AST"]+ 0.94*b["AST"]/b["ALT"]);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Mortality Rate", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values},
];

var layout = {title:"NAFLD liver fat score (NLFS) [>-0.64] - Must include 0.15*Fasting Insulin"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "NLFS")

```