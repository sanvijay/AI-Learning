# Install conda to manage
Conda is an open-source, cross-platform, language-agnostic package manager and environment management system.

 - [brew install anaconda](https://formulae.brew.sh/cask/anaconda)
 - or [brew install miniconda](https://formulae.brew.sh/cask/miniconda)

```
brew install --cask anaconda
echo "export PATH="/opt/homebrew/anaconda3/bin:\$PATH"\n" >>! ~/.bash_profile
```

### Conda cheatsheet

 - [Cheatsheet](https://docs.conda.io/projects/conda/en/stable/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf)

```
# Some useful conda commands
conda init zsh # One time command
conda create -n myenv python=3.9
conda activate myenv
conda deactivate

conda env list

# Sharing conda environment
conda env export > myenv.yml
conda env create -f myenv.yml
```
