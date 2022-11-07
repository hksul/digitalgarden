```dataviewjs

let pg1 = dv.pages("#BloodTest").where(b=>b.Triglyceride && b.HDL ).sort(b => b.Date);
const data2 = pg1.map(b=>b["Triglyceride"]/b["HDL"]);



//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Triglyceride to HDL Ratio", x:  pg1.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values}
];

var layout = {title:"Triglyceride to HDL Ratio"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "Triglyceride_to_HDL_Ratio")

```