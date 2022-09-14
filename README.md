# this is a sample project directory to guide my future research

_adapted from **Good research code** - Patrick Mineault_

## instructions summary

1. Pick a name and create a folder for the project
2. Initialize a git repository and sync to Github
3. Set up a virtual environment
4. Create a project skeleton
5. Install a project package

**_The end result will be a logically organized project skeleton that’s synced to version control._**

⚠️You can do many of these steps inside of an
IDE or file explorer - not just in the terminal.

## git and github

After picking a name and making a directory for your research project, initialize and sync your git repository to github.

1. create a **README.md** file in the directory.
2. run `git init`
3. `git add README.md`
4. `git commit -m "first commit"`
5. `git branch -M main`
6. `git remote add origin https://github.com/your-user-name/and-directory-name.git`
7. `git push -u origin main`

⚠️ Commit code from a few times a day to a few times per week. Don’t wait
until the project is almost finished before you start to commit. **A commit should represent a unit of related work.** For example, if you made changes in 3 files to add a new functionality, that should be one commit. **Make your git commit messages meaningful**, as it will help you keep track down bugs several months
down the line.

## virtual environments with _conda_

Virtual environments are used to manage dependencies. Each virtual environment specifies which versions of software and packages a project uses. The specs can be different for different projects, and each virtual environment can be easily swapped, created, duplicated or destroyed. Virtual ennviroments solve the problem of one big monolithic Python environment when every package is installed in that one
environment. Since this environment is not documented anywhere, if you need to move to another computer, or need to recreate the environment from scratch several months later, you would be in for several hours or days
of frustration.

⚠️ You can use software like conda, pipenv, poetry, venv,
virtualenv, asdf or docker to manage dependencies. Here we use the conda workflow, which is popular among
data scientists and researchers.

### terminal

**conda** is both a package manager
(something that installs package on your system) and a virtual environment manager (something that can swap out different
combinations of packages and binaries - virtual environments - easily).

1. `conda create --name codebook python=3.8`
2. `conda activate codebook`
3. `conda install pandas numpy scipy matplotlib seaborn`
4. `conda env export > environment.yml`
5. ``

## Folders

- data: Where you put raw data for your project. You usually won’t sync this to source control, unless you use very
  small, text-based datasets (< 10 MBs).
- docs: Where you put documentation, including Markdown and reStructuredText (reST). Calling it docs makes
  it easy to publish documentation online through Github pages.
- results: Where you put results, including checkpoints, hdf5 files, pickle files, as well as figures and tables. If
  these files are heavy, you won’t put these under source control.
- scripts: Where you put scripts - Python and bash alike - as well as .ipynb notebooks.
- src: Where you put reusable Python modules for your project. This is the kind of python code that you import.
- tests: Where you put tests for your code

You can create this project directory structure in the terminal with:

`mkdir {data,docs,results,scripts,src,tests}`
