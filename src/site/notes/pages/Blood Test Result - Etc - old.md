---
{"dg-publish":true,"permalink":"/pages/blood-test-result-etc-old/","dgHomeLink":true,"dgPassFrontmatter":false}
---




## Blood Sugar, HbA1c, Uric Acid, Ferritin & Testosterone

### BloodSugar


```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.BloodSugar).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data = pages.map(b=>b["BloodSugar"]);

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'BloodSugar (mg/dL) [70-100]',
            data: data.values,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        }]
    }
}
window.renderChart(chartData, this.container);
```



<div style="page-break-after: always;"></div>

### HbA1c
 
```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.HbA1c).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data = pages.map(b=>b["HbA1c"]);

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'HbA1c (%) [<=5.6]',
            data: data.values,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        }]
    }
}
window.renderChart(chartData, this.container);
```


<div style="page-break-after: always;"></div>

### UricAcid
 
```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.UricAcid).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data = pages.map(b=>b["UricAcid"]);

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'UricAcid (mg/dL) [3.4-7.0]',
            data: data.values,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        }]
    }
}
window.renderChart(chartData, this.container);
```


<div style="page-break-after: always;"></div>

### Ferritin
 
```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.Ferritin).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data = pages.map(b=>b["Ferritin"]);

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'Ferritin (ng/mL) [30-400]',
            data: data.values,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        }]
    }
}
window.renderChart(chartData, this.container);
```


<div style="page-break-after: always;"></div>

### Testoterone
 
```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.TestosteroneTotal).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data = pages.map(b=>b["TestosteroneTotal"]);

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'TestosteroneTotal ',
            data: data.values,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        }]
    }
}
window.renderChart(chartData, this.container);
```
