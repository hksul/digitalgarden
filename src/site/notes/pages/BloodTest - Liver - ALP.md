```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.ALP).sort(b => b.Date);
 
//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Phenotypic", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.ALP.values},
];

var layout = {title:"ALP"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "ALP")

```