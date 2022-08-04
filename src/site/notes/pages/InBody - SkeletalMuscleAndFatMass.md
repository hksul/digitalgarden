```dataviewjs
 


let pg = dv.pages("#InBody").where(b=>b.BodyFatMass).sort(b => b.Date);
let pg2 = dv.pages("#InBody").where(b=> b.SkeletalMuscleMass).sort(b => b.Date);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"BodyFatMass", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.BodyFatMass.values},
 {name:"SkeletalMuscleMass", x:  pg2.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg2.SkeletalMuscleMass.values}
];

var layout = {title:"BodyFatMass & SkeletalMuscleMass  "};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "BodyFatMassSkeletalMuscleMass")
```