---
title: "CoxPH"
author: "Amy Watt"
date: "4/12/2019"
output: 
  html_document: 
    keep_md: true
---








```r
KM <- survfit(Surv(time, censor)~1, data=aids)
survminer::ggsurvplot(KM, conf.int=TRUE, censor=F) + ggtitle("Overall Survival Curve")
```

![](CoxPH_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

```r
KM <- survfit(Surv(time, censor)~karnof, type="kaplan-meier", conf.type="log", data=aids)
survminer::ggsurvplot(KM, conf.int=FALSE, censor=F) + ggtitle("Survival Curve by Karnofsky Scale")
```

![](CoxPH_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

