```dataviewjs
 


let pg = dv.pages("#FitnessTest").where(b=>b.Power).sort(b => b.Date);
let pg2 = dv.pages("#FitnessTest").where(b=> b.Strength).sort(b => b.Date);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Power", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.Power.values},
 {name:"Strength", x:  pg2.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg2.Strength.values}
];

var layout = {title:"Power & Strength  "};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "PowerStrength")
```