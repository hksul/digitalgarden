```dataviewjs

let pg = dv.pages("#InBody").where(b=>b.BasalMetabolicRate).sort(b => b.Date);

let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
var d3 = require(path+"/assets/d3.v7.min.js");


var data = [
 {x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: pg.BasalMetabolicRate.values}
];
var layout = {title:"BasalMetabolicRate "};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "BasalMetabolicRate")
```