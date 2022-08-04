```dataviewjs
 


let pg = dv.pages("#InBody").where(b=>b.Weight).sort(b => b.Date);
let pg2 = dv.pages("#InBody").where(b=> b.FitnessScore).sort(b => b.Date);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Weight", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.Weight.values},
 {name:"FitnessScore", x:  pg2.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg2.FitnessScore.values}
];

var layout = {title:"Weight & FitnessScore  "};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "WeightFitnessScore")
```