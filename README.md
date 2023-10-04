# 2D Turbulence Model
A model to generate low-frequency wind fluctuations i.e. 2D turbulence. 

## Introduction
This model is based on the 2D spectral tensor presented in [Syed and Mann (2023)](https://doi.org/10.21203/rs.3.rs-3194206/v1 "Syed and Mann (2023)").  The low-frequency turbulence model has four input parameters:

1. $\sigma^2_{2D}$ the variance exhibited by low-frequency fluctuations ,
2. $L_{2D}$ the length scale corresponding to the peak of mesoscale turbulence,
3. $z_i$ the attenuation length, which is assumed to be the boundary layer height, and
4. $\psi$ the anisotropy parameter.

The model generates 2D wind fields for the longitudinal ($u$) and lateral ($v$) wind components. 

## Contents
This repository has following files:
1. An executable file compiled in a win64 operating system for windows: windsimu_win64.exe
2. A sample input file foe generating wind fields: test2d.inp

The input file has the following format:
Input  | Comment
------------- | -------------
2  | Simulate the field with two spatial dimensions
2 | Simulate two components
1 | namely the $u$-component and
2 | the $v$-component
3 | The vertical spatial dimension is not simulated
$N_1$ | the number of points in the $x$-direction (Must be equal to $2^n$ where $n$ is a positive integer)
$N_2$ | the number of points in the $y$-direction (Must be equal to $2^n$ where $n$ is a positive integer)
$L_1$ | length of box in meters
$L_2$ | width of box in meters
2D | The simulation is two-dimensional, large-scale, anisotropic
$\sigma^2_{2D}$ | the variance exhibited by low-frequency fluctuations
$L_{2D}$ | the length scale corresponding to the peak of mesoscale turbulence in meters
$z_i$ | the attenuation length, which is assumed to be the boundary layer height, in meters
$\psi$ | the anisotropy parameter in degrees ($45^\circ$ is isotropic)
seed | random, and must be a negative integer
output.u | Output file name for the $u$ component
output.v | Output file name for the $v$ component

## Running the executable
In order to generate wind fields simply runt the executable with desired parameters in the input file:

`.\windsimu_win64.exe test2d.inp`

The output will be generated in binary format. 

## Reference
1. Abdul Haseeb Syed, Jakob Mann. A model for low-frequency, anisotropic wind fluctuations and coherences in the marine atmosphere, 27 July 2023, PREPRINT (Version 1) available at Research Square [https://doi.org/10.21203/rs.3.rs-3194206/v1]
