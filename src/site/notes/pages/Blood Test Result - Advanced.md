---
{"dg-publish":true,"permalink":"/pages/blood-test-result-advanced/","dgHomeLink":true,"dgPassFrontmatter":false}
---


## Phenotypic Age Panel  - *Aging*

### Phenotypic Age


```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.Lymphocyte && b.ALP  && b.Albumin).sort(b => b.Date);

const data2 = pg.map( b=>141.5+Math.log(-0.00553*Math.log(1-(1-Math.exp(-Math.exp((-19.907-0.0336*b["Albumin"]*10+0.0095*b["Creatinine"]*88.4+0.1953*b["BloodSugar"]/18 -0.0120*b["Lymphocyte"]+0.0268*b["MCV"]+0.0019*b["ALP"]+0.0554*b["WBC"]+0.0804*b["Age"]+0.3306*b["RDWFake"]+0.0954*b["lnCRPFake"]*0.1))*(Math.exp(0.0076927*120)-1)/0.0076927))))/0.09165);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Phenotypic", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values},
];

var layout = {title:"Phenotypic Age "};
var config = {displaylogo:false};

window.renderPlotly(this.container, data, layout, config)

```


 



### Mortality Rate


```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.Lymphocyte && b.ALP  && b.Albumin).sort(b => b.Date);

const data2 = pg.map( b=>1-Math.exp(-Math.exp((-19.907-0.0336*b["Albumin"]*10+0.0095*b["Creatinine"]*88.4+0.1953*b["BloodSugar"]/18 -0.0120*b["Lymphocyte"]+0.0268*b["MCV"]+0.0019*b["ALP"]+0.0554*b["WBC"]+0.0804*b["Age"]+0.3306*b["RDWFake"]+0.0954*b["lnCRPFake"]*0.1))*(Math.exp(0.0076927*120)-1)/0.0076927));

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Mortality Rate", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values},
];

var layout = {title:"Mortality Rate"};
var config = {displaylogo:false};

window.renderPlotly(this.container, data, layout, config)

```



---
## Phenotypic Model
- Model

$$
\begin{equation}
-0.0336*10*Albumin+0.0095*88.4*Creatinine+0.1953/18*Glucose -0.0120*Lymphocyte+0.0268*MCV
\end{equation}
$$
$$
\begin{equation}
+0.0019*ALP+0.0554*WBC+0.0804*Age+0.3306*RDWFake+0.0954*0.1*lnCRPFake
\end{equation}
   
$$

	 
- Variables used in the Model
	- Albumin: dissolved proteins in the plasma, including hormones and other signal molecules.

	- Creatinine: this is a waste product cleared by the kidneys, thus a high value suggests kidney malfunction; but it can be confounded by exercise, which raises creatinine.

	- Glucose: blood sugar rises with Type 2 diabetes and loss of insulin sensitivity.

	- C-reactive protein: this is a measure of systemic inflammation.

	- Lymphocyte %: the most common types of white blood cells.

	- Mean red cell volume (MCV): the average size of red blood cells

	- Red cell distribution width (RDW): standard deviation of the above

	- Alkaline phosphatase (ALP): this is elevated in liver disease, including cancers and hepatitis.

	- White blood cell count: total white blood cells of all types


---

 
- From
	- [Refs: "An epigenetic biomarker of aging for lifespan and healthspan", Aging (Albany NY) 10(4) 573-591 (2018 Apr 18).](https://www.ncbi.nlm.nih.gov/pubmed/29676998)
	- [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5940111/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5940111/)
	- https://www.aginginterventionfoundation.org/DNAmPhenoAge_gen_Enhanced.xlsx
	 - ![](../assets/DNAmPhenoAge_gen_Enhanced.xlsx)
 
---
- Other References

	- https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002718#pmed.1002718.ref021
	- https://blog.naver.com/PostView.naver?blogId=lheebok&logNo=222306541409
 - Covid19 and Aging
	 - https://www.nature.com/articles/s41467-022-29801-8
	 - https://www.clien.net/service/board/lecture/17219327?type=recommend

---


## Liver Models
- https://www.kasl.org/bbs/index.html?code=guide&category=&gubun=&idx=&page=1&number=3826&mode=view&order=&sort=&keyfield=&key=
- 지방증 평가
	- Fatty liver index (FLI)


### NAFLD liver fat score (NLFS)

```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.AST && b.ALT).sort(b => b.Date);

const data2 = pg.map( b=>-2.89 + 0.04*b["AST"]+ 0.94*b["AST"]/b["ALT"]);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Mortality Rate", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values},
];

var layout = {title:"NAFLD liver fat score (NLFS) [>-0.64] - Must include 0.15*Fasting Insulin"};
var config = {displaylogo:false};

window.renderPlotly(this.container, data, layout, config)

```



### Hepatic steatosis index (HSI) 


```dataviewjs

let pg = dv.pages("#BloodTest").where(b=>b.AST && b.ALT).sort(b => b.Date);

const data2 = pg.map(b=>8*b["ALT"]/b["AST"]+24);

//let path = "/Users/hongkeesul/Dropbox/Research_obsidian/Research";//absolute path to your vault
//var d3 = require(path+"/assets/d3.v7.min.js");

var data = [
 {name:"Mortality Rate", x:  pg.Date.values.map(x => moment(x.toString()).format("YYYY-MM-DD")),y: data2.values},
];

var layout = {title:"Hepatic steatosis index (HSI) [>=36, <30] - Assuming Flat BMI of 24"};
var config = {displaylogo:false};

window.renderPlotly(this.container, data, layout, config)

```



- 간 섬유화 평가
	- NAFLD fibrosis score (NFS)
	- Fibrosis-4 (FIB-4) index