sjPlot - Data Visualization for Statistics in Social Science
------------------------------------------------------------------------------
Collection of plotting and table output functions for data visualization. Results of various statistical analyses (that are commonly used in social sciences) can be visualized using this package, including simple and cross tabulated frequencies, histograms, box plots, (generalized) linear models, mixed effects models, PCA and correlation matrices, cluster analyses, scatter plots, Likert scales, interpretation of interaction terms in regression models, constructing index or score variables and much more.


### Installation

#### Latest development build

To install the latest development snapshot (see latest changes below), type following commands into the R console:

```r
library(devtools)
devtools::install_github("sjPlot/devel")
```

#### Officiale, stable release
To install the latest stable release from CRAN, type following command into the R console:

```r
install.packages("sjPlot")
```

### References, documentation and examples

- [Documentation and examples](http://www.strengejacke.de/sjPlot/)
- [Weblog](http://strengejacke.wordpress.com/sjplot-r-package/)


### Citation

In case you want / have to cite my package, please use `citation('sjPlot')` for citation information. Since this package makes heavy use of the [ggplot-package](http://cran.r-project.org/web/packages/ggplot2/index.html), consider citing this package as well.

### Changelog of current development build 1.7-10

#### General
* _Utility, recode and statistical test functions have been moved to another package called [sjmisc](https://github.com/sjPlot/sjmisc)!_
* R-Version dependency changed to R >= 3.1, due to import of `tidyr` and `dplyr` packages.

#### New functions
* `sjt.mwu` to print Mann-Whitney-tests as HTML-table.

#### Changes to functions
* `sjp.lmer` now calculates approximate p-values based on Wald chi-squared tests.
* `sjp.glm` now supports plotting `logistf` objects [(#issue 11)](https://github.com/sjPlot/devel/issues/11).
* `sjp.glmm` and `sjp.lmm` now also accept a list of fitted models (see examples in `?sjp.glmm` and `?sjp.lmm`).
* `sjp.emm.int` now also accepts `lmerMod`-objects from `lme4`-package.
* `sjp.int` now supports `plm` objects (from plm-package).
* Added parameter `legendTitle` to `sjp.int`.
* Added parameter `int.plot.index` to `sjp.int`, so only selected interaction terms may be plotted.
* Added parameter `showCI` to `sjp.emm.int` to add confidence intervals to estimated marginal means.
* Added parameter `axisLabels.x` to `sjp.emm.int` to manually add value labels for the x-axis.
* Parameter `legendLabels` of `sjp.int` now accepts a list of character vectors, with one vector of legend labels for each interaction plot plotted.
* Parameter `title` of `sjp.int` now accepts a character vector of same length as interaction terms, with one title character string for each interaction plot plotted.
* Parameter `transformTicks` in `sjp.glm` and `sjp.glmm` now defaults to `TRUE`.
* Added further pre-set themes to `sjp.setTheme`.
* Minor improvements of `sjp.setTheme`.

#### Bug fixes
* `sjp.int` did not work for interaction terms of factors with more than two levels in mixed effects models (`merMod`-objects) - fixed.
* `sjp.glm` and `sjp.glmm` should catch axis limits, which are out of printable bounds, hence these function should no longer stop in such cases.
* `sjp.lmer` and `sjp.glmer` wrongly stated that paramter `ri.nr` was out of bound when `type` was `re`, `fe.ri` or `ri.pc` - fixed.
* Weights with decimals in `sjt.xtab` (e.g. `weightBy = abs(rnorm(100, 2, 1)`) caused an error - fixed.
