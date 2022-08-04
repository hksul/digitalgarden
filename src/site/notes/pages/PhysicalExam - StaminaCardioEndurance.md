```dataviewjs
 


let pg = dv.pages("#FitnessTest").where(b=>b.Stamina).sort(b => b.Date);
let pg2 = dv.pages("#FitnessTest").where(b=> b.CardioEndurance).sort(b => b.Date);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Stamina", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.Stamina.values},
 {name:"CardioEndurance", x:  pg2.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg2.CardioEndurance.values}
];

var layout = {title:"Stamina & CardioEndurance  "};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "StaminaCardioEndurance")
```