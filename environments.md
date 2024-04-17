# Conda Envs
Your question can probably be answered [here](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#managing-environments).

## Sharing an Env

1. activate the env
1. run `conda env export --from-history > environment.yml`
1. share the .yml file

To make an env from such a file, just run `conda env create -f environment.yml`

## Removing and Env

`conda remove --name myenv --all`

## Adding an Env to Jupyter notebook

Make sure you deactivate your conda env before doing this.
1. install ipykernel `conda install -c anaconda ipykernel`
1. run this `python -m ipykernel install --user --name=ENVNAME`