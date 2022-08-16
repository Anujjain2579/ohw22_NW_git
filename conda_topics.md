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
    ![conda_img](https://carpentries-incubator.github.io/introduction-to-conda-for-data-scientists/fig/miniconda_vs_anaconda.png)
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
