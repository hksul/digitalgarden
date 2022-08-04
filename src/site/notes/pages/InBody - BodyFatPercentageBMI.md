```dataviewjs
 


let pg = dv.pages("#InBody").where(b=>b.BMI).sort(b => b.Date);
let pg2 = dv.pages("#InBody").where(b=> b.PercentBodyFat).sort(b => b.Date);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"BMI", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.BMI.values},
 {name:"PercentBodyFat", x:  pg2.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg2.PercentBodyFat.values}
];

var layout = {title:"BMI & PercentBodyFat  "};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "BodyFatPercentageBMI")
```