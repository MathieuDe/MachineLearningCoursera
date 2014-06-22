Using the caret package we are going to build a tree.

```r
library(rattle)
```

```
## Rattle : une interface graphique gratuite pour l'exploration de données avec R.
## Version 3.0.2 r169 Copyright (c) 2006-2013 Togaware Pty Ltd.
## Entrez 'rattle()' pour secouer, faire vibrer, et faire défiler vos données.
```

```r
library(rpart)
library(caret)
```

```
## Loading required package: lattice
## Loading required package: ggplot2
```

```r
setwd("E:/Coursera/Machine Learning/assignment")
dataml<-read.csv("pml-training.csv", header=TRUE)
dataml2<-dataml[,5:160]
intrain<-createDataPartition(y=dataml2$classe, p=0.05, list=FALSE)
training<-dataml2[intrain,]
testing<-dataml2[-intrain,]
```
I could not manage to run the train function in time

```r
modfit<-train(classe~.,method="rpart", data=training)
fancyRpartPlot(modfit$finalModel)
```
