# Trimmed Mean Go Package

## Overview

This repository contains a Go package that provides a function to calculate the trimmed mean of a dataset. The trimmed mean is a measure of central tendency, calculated by removing a specified proportion of the smallest and largest values from the dataset before computing the mean of the remaining values. This can be particularly useful for mitigating the impact of outliers.

## Features

- Computes the trimmed mean for a slice of `float64` values.
- Supports both symmetric and asymmetric trimming, where you can specify different trimming proportions for the lower and upper ends of the dataset.

## Installation

To use this package, clone the repository and import it into your Go project.

```sh
git get github.com/yuchenbi87/trimmedmean
```

In your Go code, import the package as follows:

```go
import "github.com/yuchenbi87/trimmedmean"
```

### Parameters

- `data []float64`: A slice of float64 values representing the dataset.
- `trim ...float64`: A variadic parameter representing the proportion of values to be trimmed from each end of the sorted dataset. If only one value is provided, trimming is assumed to be symmetric.

## Comparison with R

To verify the correctness of the Go implementation, the trimmed mean was also calculated using R's `mean(x, trim = 0.05)` function. The results were as follows:

- **For integer data**: The Go trimmed mean result was `50.5`, and the R result was also `50.5`.
- **For float data**: The Go trimmed mean result was `50.55`, while the R result was `50.55`.

## Running Tests

Unit tests are provided to validate the functionality of the `TrimmedMean` function. You can run the tests using the following command:

```sh
go test ./...
```

The tests are located in the `trimmedmean_test.go` file and cover different scenarios, including symmetric and asymmetric trimming.
