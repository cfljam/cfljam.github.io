---
layout: post
title: Authoring  R in Jupyter Notebooks on Docker
published: false
categories: [R, Docker, Jupyter,Python]
---



Although there are a number of choices I will focus on using  Docker. This provides a pretty similar environment regradless of OS. See [my previous post] on creating a [Docker definition](https://github.com/cfljam/pyRat)  for a local Jupyter server.

## Using R in  Jupyter Notebooks

The  major choice you face is whether to :
1. Use a Python kernel with option for R cell magics using  [R2py](http://rpy.sourceforge.net/rpy2.html)
2. Use the newer R kernel

The principal advantage of using a Python kernel is having the ability to mix R with Python and shell commands. For writing pure R documents, the R kernel provides a cleaner 'R only" look.

Example Notebooks are provided in the **Notebooks** directory [Githu repository](https://github.com/cfljam/pyRat/Notebooks). Github [enabled in-place rendering of these recently](https://github.com/blog/1995-github-jupyter-notebooks-3) so you can see the notebook JSON rendered as HTML.

### Git-Oriented Workflow

My workflow for using  a Dockerised notebook server to  author R notebooks  is:

1. Create a new running container with port forwarding of the notebook server port 8888 and the location of my working directory on host mounted at e.g. **/Documents**

```
docker run -it -v /Users/johnmccallum/Documents:/Documents \
 -p 8888:8888 cfljam/pyRat
```
2. Navigate using the Notebook browser interface to host location where I have a git repository.
3. Create notebooks using R or python kernels.
4. Commit notebooks to repo
5. Optionally store notebooks as GitHub secret Gists for sharing rendered links via [nbviewer], and tag these using GistBox.
6. Share and discuss output with collaborators via pull requests and/or Gist links

### Using R in a Python kernel with R2Py



### Using Rkernel  Notebooks





Many thanks to the Rocker and Jupyter teams who are doing an amazing job bringing us these expressive tools for data science!

Links
======

- [Running Jupyter / IPython Notebooks on Docker for Mac/Windows](http://odewahn.github.io/docker-jumpstart/ipython-notebook.html)
