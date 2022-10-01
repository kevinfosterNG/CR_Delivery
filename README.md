# CR Delivery

## Summary
This application allows delivery of Crystal Reports by either Email or File export either directly, or scheduled through NextGen's Background Business Processor.  
Refer to the [User Guide](https://github.com/kevinfosterNG/CR_Delivery/blob/master/Crystal%20Report%20Delivery%20-%20User%20Guide.pdf) for installation and configuration. 

Here is a simple flow chart:

```mermaid
flowchart LR;
    subgraph nge [NextGen]
        direction TB
        ng[(NGProd)]-->bbp;
        bbp[[BBP Job]];
    end
    bbp-->cd;
    cd-->pdf[[fa:fa-file-alt Report Delivered!]];
    subgraph cd [Crystal Delivery]
        direction TB
        crxml([fa:fa-file-code *.crxml]) --> crd;
        crd(CR_Delivery.exe) --> crxml;
        crxml --> rpt(*.rpt) --> crxml;
    end
```

### CR Delivery (v1.0.13)
<p align="center">
  <img src="https://github.com/kevinfosterNG/CR_Delivery/blob/master/app.png" />
  <h5 align="center">CR Delivery About
<p align="center">
  
![asdf](https://fostes.org/img/CRDelivery-TestExport.gif)
  
### NextGen BBP Integration
  <p align="center">
  <img src="https://github.com/kevinfosterNG/CR_Delivery/blob/master/bbp_job.png" />
  <h5 align="center">NextGen BBP Integration
<p align="center">

## Installer Download
[v1.1.3](Setup-1.1.3.msi)

## Supported NextGen versions
_Though most versions are suspected to work as is, these are the specific versions tested against._

| NG Version | Status | CR Delivery Version | CR Runtime |
|:-------:|:------|:------|:------|
| 5.8.3 | ![Passing](https://raw.githubusercontent.com/travis-ci/travis-api/master/public/images/result/passing.png) | v1.0.10 (and earlier) | 13.0.14 |
| 5.9.1 | ![Passing](https://raw.githubusercontent.com/travis-ci/travis-api/master/public/images/result/passing.png) | v1.0.10 (and earlier) | 13.0.14 |
| 5.9.2 | ![Passing](https://raw.githubusercontent.com/travis-ci/travis-api/master/public/images/result/passing.png) | v1.1.2 (and later) | 13.0.24 |
| 5.9.3 | ![Unknown](https://raw.githubusercontent.com/travis-ci/travis-api/master/public/images/result/unknown.png) | v1.1.2 (and later) | 13.0.24 |
| 5.9.2020.1 | ![Unknown](https://raw.githubusercontent.com/travis-ci/travis-api/master/public/images/result/unknown.png) | v1.1.2 (and later) | 13.0.24 |
| 6.2021.1 | ![Passing](https://raw.githubusercontent.com/travis-ci/travis-api/master/public/images/result/passing.png) | v1.1.2 (and later) | 13.0.24 |
