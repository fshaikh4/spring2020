class notes: 02/05/2020

# important links
 - [BIOF 509 Gitter](https://gitter.im/biof509/community)
  - chatroom: for communication during the course
 - [BIOF 509 GitHub](https://github.com/biof509)
 - [BIOF 509 website](https://biof509.github.io)
 - [free DataCamp signup spreadsheet](https://docs.google.com/spreadsheets/d/1nNq2VXKP4hhQvEtGP7zxVC9QYUjfnCWNleZKN8EfBTE/edit?usp=sharing)
  - free access for "everyone you know"

# course overview
 - final project
 - presentation

---

# what is a shell?
 - program that runs on your computer and interprets commands, line-by-line (command-line)

# GitHub desktop
 - a way to interact w/ GitHub files if not using GitHub from terminal
 - want cloned repo paths to "mirror" URL
 
# git versioning
 - commits: store change information
 - pushed to "remote"
 - create a branch: will give you push access to your own branch, but harder for owner to manage several branches
  - will always be pushing to "master" (no need for branches)
  - but may want to use branching for collaborative projects
 - fork: "taking fork of original repository, and putting it onto your plate"
  - duplicates project on GitHub, under your org/username

---

# markdown
 - .md file extensions
  - e.g., README.md on GitHub
 - superset of HTML (contains many HTML functions)

# Colab & binder
 - Colab: integrated w/ Google Drive
 - binder is funded via grants (academically sponsored)
  - when close window, nothing saved (sort of like a sandbox)
  - user is 'jovyan' (inhabitant of planet Jupiter)
  - can use git on binder, to stage & commit changed files, one by one
  - ⌘+b or ctrl+b will allow collapse sidepane of binder window
  - binder can time-out (need to refresh; would lose previous changes)
 - how to work with Jupyter notebooks interactively without having it installed on a machine
  - all calculations are being run on a server (not using computational resources of the local machine)

# Jupyter Notebooks
 - run in web browser, with a frontend that renders markdown
 - can run code, and display results, all in one document
 - backends (also known as kernels) which execute code
  - kernels exist for many different languages
  - provides common user interface for many languages
 - want to practice concept of "literate programming"
  - text describing what you want to do
  - code
  - output of code (automatically generated by Jupyter Notebook)
  - text explaining results (is it what we expected? etc.)
 - extension: .ipynb (interactive python notebook)
  - built on ipython project (rebranded)
 - "jupyter": JUlia-PYThon-R

# docker
 - application that allows running/creation of docker image, which is a self-encapsulated virtual system (down to the OS)
 - binder is hosted on a docker image, specifically using ubuntu

---

# YAML
 - yet another markup language
 - YAML ain't a markup language
 - used to specify anaconda environments (specify packages and versions you want to use for a project)

# package managers
 - e.g., conda, apt, brew, pip
 - conda: can install non-python things (e.g., R)
 - pip: "pip installs python"

# anaconda distribution
 - distribution: describes a collection of software
  - e.g., linux distribution
 - spyder: popular python IDE
  - IDE: integrated development environment
 - miniconda: minimal installer of anaconda
  - relies on user to download necessary additional packages (no GUI)

# prepend to PATH
 - export PATH="path/to/something:$PATH"


# Jupyter Notebook keyboard shortcuts
 - m: convert cell to markdown
 - y: convert cell to code
 - b: code cell below
 - a: code cell above
 - enter: start editing cell
 - esc: stop editing cell
 - dd: delete cell
 - cv: copy-paste
 - xv: cut-paste

# Jupyter Lab
 - almost IDE (if not already)
 - binder opens up Jupyter Lab IDE in its windows
 - how do I know I'm on my computer (versus in binder or on a remote server)?
  - address of Jupyter Lab interface will say localhost:8888/

# python easter eggs
 - import this: Zen of Python (poem)
 - import antigravity: opens xkcd comic

# [DS101](https://github.com/marskar/ds101)
 - created slideshow from a Jupyter Notebook
