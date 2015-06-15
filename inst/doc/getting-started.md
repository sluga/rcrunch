<!--
%\VignetteEngine{knitr::knitr}
%\VignetteIndexEntry{Getting started with crunch}
-->

# Getting started with `crunch`

[Crunch.io](http://crunch.io/) provides a cloud-based data store and analytic engine. It has a [web client](https://beta.crunch.io/) for interactive data exploration and visualization. The *crunch* package for R allows analysts to interact with and manipulate Crunch datasets from within R. Importantly, this allows technical researchers to collaborate naturally with team members, managers, and clients who prefer a point-and-click interface: because all connect to the same dataset in the cloud, there is no need to email files back and forth continually to share results. 


```r
library(crunch)
```

Both *crunch* and the Crunch web application communicate with the same application programming interface (API), served over secure HTTP. Within an R script or interactive session, the *crunch* package allows you to interact with your data in Crunch with expressive, idiomatic R. Functions in crunch handle the translation between R objects and API requests and responses, so you can typically interact with your datasets as if they were local `data.frames` (with some additional metadata), not data on a remote server.

## Authentication

All work with data in Crunch requires users to be authenticated. Thus, the first step after loading *crunch* is to log in:

```r
login(email="xkcd@crunch.io")
```
```
Crunch.io password for xkcd@crunch.io: *enter your password here*
## Logged into crunch.io as xkcd@crunch.io
```

This will log you in to the Crunch API. All of these parameters can be also be set as R `options` in your .Rprofile so that you can simply `login()`. See `?login` for details.

## Table of contents

The Crunch data store is built around datasets, which contain variables. Unlike R `data.frames` and atomic vectors, Crunch datasets and variables contain additional metadata. The following vignettes illustrate how you can create and work with datasets using *crunch*.

* [Datasets](datasets.md): creating, loading, and manipulating datasets in Crunch
* [Variables](variables.md): cleaning and defining variable metadata
* [Array variables](array-variables.md): how to create and manipulate categorical-array and multiple-response variables
* [Variable organization](variable-order.md): defining a hierarchy and arranging variables within it
* [Transformations and derivations](derive.md): alter values within a dataset and create new variables as a function of others
* [Computing on Crunch data](analyze.md): crosstabulation and more 