---
{"dg-publish":true,"permalink":"/pages/blood-test-result-cholesterol-old/","tags":"gardenEntry","dgHomeLink":true,"dgPassFrontmatter":false}
---


[BioHacking MOC](BioHacking%20MOC.md)
[Blood test MOC](../pages/Blood%20test%20MOC.md)


---


# Cholesterol Panel


## TotalCholesterol




```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.TotalCholesterol).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data = pages.map(b=>b["TotalCholesterol"]);

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'TotalCholesterol (mg/dL) [<200]',
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

## Triglyceride / HDL / LDL
 
```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.Triglyceride || b.HDL || b.LDL).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data1 = pages.map(b=>b["Triglyceride"]);
const data2 = pages.map(b=>b["HDL"]);
const data3 = pages.map(b=>b["LDL"]);

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'Triglyceride (mg/dL) [<150]',
            data: data1.values,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        },
		{
            label: 'HDL (mg/dL) [40-60]',
            data: data2.values,
            backgroundColor: [
                'rgba(155, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(155, 99, 132, 1)'
            ],
            borderWidth: 1
        },
		{
            label: 'LDL (mg/dL) [<130;<100 Optimal]',
            data: data3.values,
            backgroundColor: [
                'rgba(55, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(55, 99, 132, 1)'
            ],
            borderWidth: 1
        }]
    }
}
window.renderChart(chartData, this.container);
```



<div style="page-break-after: always;"></div>

## Triglycerides-to-HDL Ratio

```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.Triglyceride && b.HDL).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data = pages.map(b=>b["Triglyceride"]/b["HDL"]);
 

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'Triglycerides-to-HDL Ratio',
            data: data.values,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        },
		]
    }
}
window.renderChart(chartData, this.container);
```



<div style="page-break-after: always;"></div>

## TotalCholesterol-to-HDL Ratio

```dataviewjs
const pages = dv.pages("#BloodTest").where(b=>b.TotalCholesterol && b.HDL).sort(b => b.Date);
const labels = pages.map(b=>b["Date"]);
const data = pages.map(b=>b["TotalCholesterol"]/b["HDL"]);
 

const chartData = {
    type: 'line',
    data: {        
		labels: labels.values,
        datasets: [{
            label: 'TotalCholesterol-to-HDL Ratio',
            data: data.values,
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)'
            ],
            borderWidth: 1
        },
		]
    }
}
window.renderChart(chartData, this.container);
```

