```dataviewjs

let pg1 = dv.pages("#BloodTest").where(b=>b.Triglyceride ).sort(b => b.Date);
let pg2 = dv.pages("#BloodTest").where(b=>b.HDL ).sort(b => b.Date);
let pg3 = dv.pages("#BloodTest").where(b=>b.LDL).sort(b => b.Date);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Triglyceride", x:  pg1.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg1.Triglyceride.values},
 {name:"HDL", x:  pg2.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg2.HDL.values},
 {name:"LDL", x:  pg3.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg3.LDL.values},
];

var layout = {title:"Triglyceride / HDL / LDL"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "Triglyceride/HDL/LDL")
```