[![DOI](https://joss.theoj.org/papers/10.21105/joss.05729/status.svg)](https://doi.org/10.21105/joss.05729)

# Paraqus

## Introduction

Paraqus is a Python package to convert simulation results, for example from finite element or CFD simulations, to the widely used and open *Visualization Toolkit* (VTK) file format. It was initially designed for the export of FE results from the commercial FE software [Abaqus](https://www.3ds.com/products/simulia/abaqus), but its modular structure allows it to be extended to other software. VTK files can be visualized for example by the free and open source software [ParaView](https://www.paraview.org). Paraqus is intended for anyone who wants to convert simulation results, especially from Abaqus, to a non-proprietary format, either to use tools such as ParaView for their own visualizations, or to exchange data in an open format.


## Documentation

The documentation for Paraqus can be found [here](https://paraqus.readthedocs.io/). We refer the reader to the documentation for information on dependencies, installation, and usage of the package.


## Contacts

For any problems related to Paraqus, please open an issue in our [github repository](https://github.com/InstituteOfMechanics/Paraqus).


## License

Paraqus is released under the [GNU GPLv3](https://choosealicense.com/licenses/gpl-3.0/) license.

## Citation
If you used Paraqus for your project, please cite the following [publication](https://joss.theoj.org/papers/10.21105/joss.05729):

    @article{paraqus, 
             doi = {10.21105/joss.05729}, 
             year = {2025}, 
             volume = {10}, 
             number = {106}, 
             pages = {5729}, 
             author = {Tim Furlan and Jonathan Stollberg and Andreas Menzel}, 
             title = {Paraqus: Exporting Finite Element Simulation Results from Abaqus to VTK}, 
             journal = {Journal of Open Source Software}}


