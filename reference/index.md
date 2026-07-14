# Package index

## Package Overview

- [`DIVAS`](https://byronsyun.github.io/DIVAS/reference/DIVAS-package.md)
  [`DIVAS-package`](https://byronsyun.github.io/DIVAS/reference/DIVAS-package.md)
  : DIVAS: Data Integration via Analysis of Subspaces

## Core Workflow Function

The main function to run the DIVAS analysis pipeline.

- [`DIVASmain()`](https://byronsyun.github.io/DIVAS/reference/DIVASmain.md)
  : Data integration via analysis of subspaces

## Signal Extraction Functions

Functions for extracting signals from data matrices.

- [`DJIVESignalExtractJP()`](https://byronsyun.github.io/DIVAS/reference/DJIVESignalExtractJP.md)
  : Signal Matrix Extraction for DIVAS
- [`MatSignalExtractJP()`](https://byronsyun.github.io/DIVAS/reference/MatSignalExtractJP.md)
  : Matrix Signal Extraction
- [`MedianMarcenkoPastur()`](https://byronsyun.github.io/DIVAS/reference/MedianMarcenkoPastur.md)
  : Calculate the Median of the Marčenko-Pastur Distribution
- [`PercentileMarcenkoPastur()`](https://byronsyun.github.io/DIVAS/reference/PercentileMarcenkoPastur.md)
  : Percentile of the Marcenko-Pastur Distribution
- [`incMarPas()`](https://byronsyun.github.io/DIVAS/reference/incMarPas.md)
  : Incomplete Marčenko-Pastur Distribution Function
- [`ksOpt()`](https://byronsyun.github.io/DIVAS/reference/ksOpt.md) :
  Optimal Shrinkage Estimation using Kolmogorov-Smirnov Criterion
- [`optimal_shrinkage()`](https://byronsyun.github.io/DIVAS/reference/optimal_shrinkage.md)
  : Optimal Shrinkage of Singular Values
- [`optshrink_impl()`](https://byronsyun.github.io/DIVAS/reference/optshrink_impl.md)
  : Optimal Shrinkage of Singular Values

## Joint Structure Estimation Functions

Functions for estimating joint and individual structures.

- [`DJIVEJointStrucEstimateJP()`](https://byronsyun.github.io/DIVAS/reference/DJIVEJointStrucEstimateJP.md)
  : Estimate full and partially shared joint structures Establish a DC
  programming problem to estimate each partially joint structure using
  Penalty CCP algorithm.

## Reconstruction Functions

Functions for reconstructing data based on identified structures.

- [`DJIVEReconstructMJ()`](https://byronsyun.github.io/DIVAS/reference/DJIVEReconstructMJ.md)
  : DJIVEReconstructMJ - Reconstruct joint blocks from data blocks
- [`MatReconstructMJ()`](https://byronsyun.github.io/DIVAS/reference/MatReconstructMJ.md)
  : MatReconstructMJ - Reconstruct joint block matrices and their
  loadings from data

## Diagnostic Functions

Functions for diagnosing and evaluating the DIVAS results.

- [`DJIVEAngleDiagnosticJP()`](https://byronsyun.github.io/DIVAS/reference/DJIVEAngleDiagnosticJP.md)
  : Create Diagnostic Plots for DJIVE Analysis
- [`randDirAngleMJ()`](https://byronsyun.github.io/DIVAS/reference/randDirAngleMJ.md)
  : Calculate Random Direction Angles

## Utility Functions

Helper functions for DIVAS workflow and result interpretation.

- [`MatCenterJP()`](https://byronsyun.github.io/DIVAS/reference/MatCenterJP.md)
  : Center a Matrix by Rows, Columns, or Both
- [`acosd()`](https://byronsyun.github.io/DIVAS/reference/acosd.md) :
  Arccosine in Degrees
- [`getTopFeatures()`](https://byronsyun.github.io/DIVAS/reference/getTopFeatures.md)
  : Extract Top Contributing Features for a DIVAS Component
