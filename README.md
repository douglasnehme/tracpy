# TracPy

Fortran core of TRACMASS + Python wrapping around the outside.

## Chages Info

Forked from [TracPy v1.0](https://github.com/kthyng/tracpy/releases/tag/v1.0) with minor changes in:
1. [tools.py](https://github.com/douglasnehme/tracpy/blob/master/tracpy/tools.py#L482)
1. [tracpy_class.py](https://github.com/douglasnehme/tracpy/blob/master/tracpy/tracpy_class.py#L10)

## Set up for TracPy

I recommend setting up a good python environment for this work, as follows:

1. If you do not have anaconda or miniconda install miniconda:
    * download file from Continuum
    * `bash [download file]`

1. Set `conda-forge` to be highest-priority channel (this helps the geography libraries like cartopy that connect to the geos library be all consistent)
    * `conda config --add channels conda-forge --force`

1. Create environment called "tracpy", reinforce conda-forge usage and I need to install pyproj (some of the listed packages are required and some are just suggested because they are useful)
    * `conda create --name tracpy --channel conda-forge python=3.6 cartopy matplotlib ipython netCDF4 fiona shapely pandas xarray cmocean jupyter scipy numpy seaborn pyproj --yes`

1. To use environment:
    * `conda activate tracpy`

1. Need to also have `octant`:
    * `cd ~`
    * `git clone https://github.com/hetland/octant.git`
    * `cd octant`
    * `pip install -e .`

1. Make sure you installed `octant`:
    * `conda list octant`

1. Get `tracpy` source code:
    * `cd ~`
    * `git clone https://github.com/douglasnehme/tracpy.git`
    * `cd tracpy`
    * `pip install -e .`
    * This makes the package an editable install so that it can be updated with future additions to TracPy. To instead install the package locally:
`pip install --user .` Note that a required package is [octant](https://github.com/hetland/octant).

1. Make sure you installed `tracpy`:
    * `conda list tracpy`

1. To stop using environment (in a given terminal window):
    * `conda deactivate`

1. To install more packages later:
    * `conda install --channel conda-forge [package name]`

1. [not tested from here] Run the manual in `/docs` with `jupyter notebook`


If you want to install locally, you can generally use the `--user` flag (e.g. `pip install --user .`).


## To update the code later

1. Move into your TracPy directory.
1. Update your GitHub repository.
`git pull`
1. Edit your install of TracPy.
`pip install -e .`
or
`pip install --force-reinstall -e .`
or, for local installation:
`pip install --ignore-installed --user .`


## To test the code

1. After making changes to the code, you can do some basic functionality testing with `py.test` or `nosetests` in the `tests` subdirectory.


## To learn more about the module TracPy

Learn more by running a small test case. Internet required.

1. Open an iPython notebook server in the TracPy `docs` directory.
`ipython notebook`
1. A webpage will open in your browser showing the available notebooks in the current directory. Open the notebook called manual.
1. The cells of the notebook can be run in order by pushing "shift" and "enter" together or the whole notebook can be run by selecting Cell > Run all. The notebook demonstrates how to initialize and run a numerical drifter experiment using TracPy.
1. Alternatively, a static PDF version of the manual can be viewed at `http://nbviewer.ipython.org/urls/raw.github.com/kthyng/tracpy/master/docs/manual.ipynb`.


## To run your own projects

For projects, it is suggested to start a separate directory with its own initialization and run file for the simulation(s). Then TracPy can be imported as a module and the run script can be run from the project. An example set of projects can be found at `https://github.com/kthyng/gisr.git`.


## To learn more about TRACMASS

* Döös, K., Kjellsson, J., & Jönsson, B. (2013). TRACMASS—A Lagrangian Trajectory Model. In Preventive Methods for Coastal Protection (pp. 225-249). Springer International Publishing.
* Döös, K., Rupolo, V., & Brodeau, L. (2011). Dispersion of surface drifters and model-simulated trajectories. Ocean Modelling, 39(3), 301-310.
* Döös, K., & Engqvist, A. (2007). Assessment of water exchange between a discharge region and the open sea–A comparison of different methodological concepts. Estuarine, Coastal and Shelf Science, 74(4), 709-721.
* TRACMASS on GitHub: https://github.com/TRACMASS
