---
layout: post
title: Authoring  R in Jupyter Notebooks on Docker
published: false
category: 
  - R
  - Jupyter
  - Python
---



Although you can install Jupyter + R + kernels on a PC (at least on OSX) I will focus on using  Docker. This provides the same environment regardless of OS. See [my previous post](http://cfljam.github.io/R-in-Jupyter/) on creating a [Docker definition](https://github.com/cfljam/pyRat) for a local Jupyter server. 

## Using R in  Jupyter Notebooks

The  major choice you face is whether to :
1. Use a Python kernel with option for R cell magics using  [rpy2](http://rpy.sourceforge.net/rpy2.html)
2. Use the newer [R kernel](https://github.com/IRkernel/IRkernel)

The principal advantage of using a Python kernel is having the ability to mix R with Python and shell commands. For writing pure R documents, the R kernel provides a cleaner "R only" look and better inline command completion and help. 

Example Notebooks are provided in the [**Notebooks** directory](https://github.com/cfljam/pyRat/Notebooks). Github [enabled in-place rendering of these recently](https://github.com/blog/1995-github-jupyter-notebooks-3) so you can see the notebook JSON rendered as HTML. There are still some teething problems [with graphics payload in these notebooks](https://github.com/IRkernel/IRkernel/issues/145) but the IRKernel team are onto it! 

### Git-Oriented Workflow

My workflow for using  a Dockerised notebook server to author R notebooks  is:

1. Create a new running container with port forwarding of the notebook server port 8888 and the location of my working directory on host mounted at e.g. **/Documents**

```
docker run -it -v /Users/johnmccallum/Documents:/Documents \
 -p 8888:8888 cfljam/pyRat
```
2. Navigate using the Notebook browser interface to host location where I have a git repository.
3. Create notebooks using R or python kernels.
4. Commit notebooks to repo, [where they are now rendered as HTML](https://github.com/blog/1995-github-jupyter-notebooks-3)
5. Optionally store notebooks as GitHub secret Gists for sharing rendered links via [Nbviewer](http://nbviewer.ipython.org/), and tag these using [GistBox](http://www.gistboxapp.com/).
6. Share and discuss output with collaborators via pull requests and/or Gist links

### Using R in a Python kernel with RPy2

1.  if you don't have **rpy2** installed, open up a terminal and eter: 

```
pip install rpy2
```

2. In a Python 2 Notebook and type in a cell
```
%load_ext rpy2.ipython
%pylab inline
```
.. this will load in R interface and also toggle inline graphs

3. Read http://rpy.sourceforge.net/rpy2/doc-2.4/html/interactive.html#module-rpy2.ipython.rmagic 
4. Run R with single line magics (%R) or cell magics (%%R)


### Using Rkernel  Notebooks

Just write R!

----------------
Many thanks to the Rocker and Jupyter teams who are doing an amazing job bringing us these expressive tools for data science. 

Links
======

- [Running Jupyter / IPython Notebooks on Docker for Mac/Windows](http://odewahn.github.io/docker-jumpstart/ipython-notebook.html)
- [Rpy2](http://rpy.sourceforge.net/)
