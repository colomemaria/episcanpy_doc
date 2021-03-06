# How to build the website for the EpiScanpy document

To view the website of EpiScanpy document, visit https://colomemaria.github.io/episcanpy_doc/

Here is how to build the website from the beginning. Please skip the step that you have previously done, for example, create a new conda environment.

## Create a conda environment for compilation

```
conda create -n compile_doc python=3.7
conda activate compile_doc
```

## Install the needed libraries and software
```
pip install episcanpy
conda install sphinx
pip install sphinx-autodoc-typehints sphinx_rtd_theme
pip install scanpydoc
```

## Get the codes of EpiScanpy from Github
```
mkdir episcanpy_document
cd episcanpy_document
git clone https://github.com/colomemaria/epiScanpy.git
```

## Compile the document to html
```
sphinx-build -b html epiScanpy/docs build_doc
```

## Update the compiled html files to Github
```
mkdir episcanpy_html
cd episcanpy_html
git clone https://github.com/colomemaria/episcanpy_doc.git
cp -Rf ../build_doc/* episcanpy_doc/docs/.
cd episcanpy_doc
git add --all
git commit -m "update website"
git push origin HEAD:refs/heads/master
```
