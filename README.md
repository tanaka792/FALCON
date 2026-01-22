This repository is based on the FALCON example
(https://mooseframework.inl.gov/falcon/examples/example01.html).

Initially, an error occurred in the fluid properties setup
(temperature 722.722 is outside the range of tabulated temperature),
so the fluid properties were modified to use water97.

To avoid warnings, some Transfer settings were partially modified:

MultiAppInterpolationTransfer → MultiAppGeometricInterpolationTransfer
MultiAppNearestNodeTransfer → MultiAppGeneralFieldNearestNodeTransfer
Exodus output was also added.

The mesh files are not included in this repository and should be obtained from the official FALCON example.

With these modifications, the simulation was confirmed to work correctly with MPI = 1.
However, when running with MPI ≥ 2, the Matrix_T results in mrect1 do not change at all.
