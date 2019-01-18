---
title: "Include R code in an Rmarkdown figure caption"
author: "YAP S S"
date: '2019-01-18'
slug: include-r-code-in-an-rmarkdown-figure-caption
tags: []
categories: []
---

Here how to include R code in an Rmarkdown with figure caption and then save to PDF file.

Use fig_caption: true in your YAML and opts_knit$set(eval.after = "fig.cap")

---
title: "Example"
output:
  pdf_document:
    fig_caption: true
---

```{r parameters}
library(knitr)
opts_knit$set(eval.after = "fig.cap")
insert_custom <- "world"
```

followed by

```{r hello-world, fig.cap = paste('Hello', insert_custom)}
plot(rnorm(10))
```
