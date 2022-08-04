```dataviewjs

const pages = await dv.io.csv("/pages/weight_20220605.csv");


var labels1 = [];
var data1 = [];

for (var i= 0; i < pages.length;i++) {
if (pages[i]["Weight"] !=0 && pages[i]["Date"].substring(0,4)>"2020"){
    labels1.push(pages[i]["Date"].substring(0,10))
    data1.push(pages[i]["Weight (kg)"])
  }
}
labels1.reverse();
data1.reverse();


let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
var d3 = require(path+"/assets/d3.v7.min.js");


var data = [
 {x:  labels1.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data1,mode: 'markers'}
];
var layout = {title:"2021-2022 Weight History"};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "2021_2022_WeightHistory")
```