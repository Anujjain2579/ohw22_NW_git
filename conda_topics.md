# Conda

Great resource: Software Carpentry -- https://carpentries-incubator.github.io/introduction-to-conda-for-data-scientists

## Make sure you have conda
- `conda --version`
- we recommend **miniconda**

## Why?
- sanity: separate environments with different packages or even python versions for different projects
- reproducibility (matlab versions as a reproducibility example)
- portability (for collaborators or your future self, or you work on many machines...)
- automatically resolve dependency issues for you, for example when you install new packages
- Conda
  - Conda is an open source package and environment management system
  - Conda vs Miniconda vs Anaconda
    <img src="https://carpentries-incubator.github.io/introduction-to-conda-for-data-scientists/fig/miniconda_vs_anaconda.png" style="width:600px">
  - pre-built packages, cross platform, can use other package management tools such as pip

## Commands
- Create a conda environment in command line
  ```shell
  $ conda create --name basic-scipy-env ipython=7.13 matplotlib=3.1 numpy=1.18 scipy=1.4
  ```
  - When conda installs a package into an environment it also installs any required dependencies. 
- Check what versions are available
  ```shell
  $ conda search scikit-learn
  ```
- Activate an environment
  ```shell
  # Enter the following
  $ conda activate basic-scipy-env
  
  # Your shell prompt will look like
  (basic-scipy-env) $
  
  # You can come out from this environment by doing
  (basic-scipy-env) $ conda deactivate
  
  # Your shell prompt will look like
  $
  ```
- Install just 1 package
  ```
  $ conda install pandas
  ```
- List existing environments
  ```
  $ conda env list 
  ```
- List content of an environment
  ```
  # Current environment
  $ conda activate basic-scipy-env
  (basic-scipy-env) $ conda list
  
  # A particular env
  $ conda list --name basic-scipy-env
  ```
- Delete an environment
  ```
  $ conda remove --name basic-scipy-env --all
  ```


## Others
- To use an environment easily for notebooks, include a Jupyter kernel (`ipykernel` for Python or `irkernel` for R) in the environment
  - What is a Jupyter kerner? it is a programming language-specific process that executes the code contained in a Jupyter notebook
- We recommend the `conda-forge` channel for installing packages
  - `conda-forge` channel is "a community led collection of recipes, build infrastructure and distributions for the conda package manager"
  ```
  $ conda install --channel conda-forge scipy=1.6
  ```
  - What are conda channels? URLs to directories containing conda packages
  - the Anaconda managed channels are referred to as the `defaults` channel, it is where the packages are searched if you don't specify the channel
  - We like `conda-forge` because:
    - packages may be more up-to-date
    - it includes additional packages not available in `defaults`


## Sharing environments
- Creating an environment using an `environment.yml` file
  ```
  $ conda create --name ohw22 --file environment.yml
  ```
- What's in an environment file?
  ```
  name: my-test-env
  
  channels:
    - conda-forge
    - defaults

  dependencies:
    - ipython
    - matplotlib
    - pandas
    - pip
    - python=3.9
    - scikit-learn
  ```
- Note: pytorch has its own channel for `pytorch` and `torchvision`
