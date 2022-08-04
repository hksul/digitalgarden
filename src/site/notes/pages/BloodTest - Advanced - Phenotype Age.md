```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.Lymphocyte && b.ALP  && b.Albumin).sort(b => b.Date);

const data2 = pg.map( b=>141.5+Math.log(-0.00553*Math.log(1-(1-Math.exp(-Math.exp((-19.907-0.0336*b["Albumin"]*10+0.0095*b["Creatinine"]*88.4+0.1953*b["BloodSugar"]/18 -0.0120*b["Lymphocyte"]+0.0268*b["MCV"]+0.0019*b["ALP"]+0.0554*b["WBC"]+0.0804*b["Age"]+0.3306*b["RDWFake"]+0.0954*b["lnCRPFake"]*0.1))*(Math.exp(0.0076927*120)-1)/0.0076927))))/0.09165);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"PhenotypeAge", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values},
];

var layout = {title:"Phenotype Age "};
var config = {displaylogo:false};

window.renderPlotlyImage(this.container, data, layout, config, "PhenotypeAge")

```