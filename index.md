# DIVAS: Data Integration via Analysis of Subspaces

![DIVAS Logo](reference/figures/DIVAS_logo.png)

## Introduction

We provide an R implementation of DIVAS (Prothero et al., 2024), a
statistical method for multi-modal data integration. Via statistical
analysis of subspaces, DIVAS identifies joint, partially shared, and
individual variation across multiple data blocks in a completely
data-driven way. In addition to translating the original MATLAB
implementation into an accessible R package, we also provide
visualization tools and worked examples for exploring DIVAS results in
practice.

**Documentation website**: <https://byronsyun.github.io/DIVAS/>

## Installation

### Dependencies

The DIVAS package requires the current 1.x line of the `CVXR` package
for compatibility with the SCS solver interface. The package has been
tested with `CVXR` 1.0-15. In `DESCRIPTION`, DIVAS also declares
`CVXR (>= 1.0-15)` as a package dependency.

``` r

# Install devtools (if not already installed)
install.packages("devtools")

# Install CVXR 1.x. DIVAS has been tested with CVXR 1.0-15.
install.packages("remotes")
remotes::install_version("CVXR", version = "1.0-15", repos = "https://cloud.r-project.org")

# Alternatively, install the latest CRAN release if it is compatible with your R version.
# install.packages("CVXR")
```

### Installing the DIVAS package

You can install the development version of DIVAS from GitHub using
`devtools`:

``` r

# Install DIVAS package from the main branch on GitHub
devtools::install_github("ByronSyun/DIVAS/pkg", ref = "main")

# Or install from a local folder if you have cloned the repository
# devtools::install("path/to/DIVAS-main/pkg")
```

## Usage Examples

The DIVAS package supports analysis of various data formats. Here is a
simple example using the built-in toy MATLAB dataset:

``` r

library(R.matlab)
library(DIVAS)

data_path <- system.file("extdata", "toyDataThreeWay.mat", package = "DIVAS")
data <- readMat(data_path)

datablock <- list(
  X1 = data$datablock[1,1][[1]][[1]],
  X2 = data$datablock[1,2][[1]][[1]],
  X3 = data$datablock[1,3][[1]][[1]]
)

result <- DIVASmain(datablock)
dataname <- paste0("DataBlock_", 1:length(datablock))
plots <- DJIVEAngleDiagnosticJP(datablock, dataname, result, 566, "Demo")
print(plots)
```

For more detailed tutorials, see the documentation website and linked
case studies below.

## Available Datasets

We provide the following examples to illustrate the use of DIVAS in
different scenarios.

| Dataset | Brief Description | Vignette Link | Format | Primary Reference |
|----|----|----|----|----|
| toyDataThreeWay.mat | Synthetic 3-block data with known joint structures | [Toy Dataset Example](https://byronsyun.github.io/DIVAS/articles/DIVAS_Toy_Dataset_Example.html) | .mat | Prothero et al. (2024) |
| gnp_imputed.qs | GNP economic time series data | [GNP Dataset Example](https://byronsyun.github.io/DIVAS/articles/DIVAS_GNP_Dataset_Example.html) | .qs | Stock & Watson (2016) |
| COVID-19 Multi-Omics | 6-block integration: scRNA-seq (4 cell types), proteomics, metabolomics from 114 COVID-19 patient samples | [COVID Case Study](https://byronsyun.github.io/DIVAS_COVID19_CaseStudy/) | .rds | Su et al. (2020) |

## Case Study: COVID-19 Multi-Omics Analysis

This project serves as a comprehensive, real-world application of the
DIVAS package on a complex multi-omics dataset from a COVID-19 patient
cohort. It demonstrates the full data processing and analysis workflow,
from raw data cleaning to final DIVAS results, showcasing the practical
utility of the package.

**➡️ [View the full analysis on
GitHub](https://github.com/ByronSyun/DIVAS_COVID19_CaseStudy)**

## Citation

If you use DIVAS, please cite the manuscript:

Sun, Y., Marron, J. S., Lê Cao, K.-A., & Mao, J. (2026). DIVAS: an R
package for identifying shared and individual variations of multiomics
data. bioRxiv, 2026.01.12.698985.
<https://doi.org/10.64898/2026.01.12.698985>

The package citation is also available in R with `citation("DIVAS")` and
on the [Authors and
Citation](https://byronsyun.github.io/DIVAS/authors.html#citation) page.

## Developers

- **[Jiadong Mao](https://github.com/jiadongm)** - *Lead Developer,
  Maintainer*
- **[Yinuo Sun](https://github.com/ByronSyun)** - *Package Developer,
  Maintainer*

## References

Prothero, J., et al. (2024). Data integration via analysis of subspaces
(DIVAS).

Su, Y., Chen, D., Yuan, D., et al. (2020). Multi-Omics Resolves a Sharp
Disease-State Shift between Mild and Moderate COVID-19. Cell, 183(6),
1479-1495. <https://doi.org/10.1016/j.cell.2020.10.037>

## License

This project is licensed under the GNU Affero General Public License
v3.0 (AGPL-3) - see the LICENSE file for details.
