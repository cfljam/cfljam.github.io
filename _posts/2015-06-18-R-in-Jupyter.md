---
layout: post
title: Running R in Jupyter Notebooks with  Docker
published: true
categories: [R, Docker, Jupyter, Python]
---
![Docker](https://secure.gravatar.com/avatar/26da7b36ff8bb5db4211400358dc7c4e.jpg?s=200&d=mm)
When Github recently [enabled rendering of Jupyter Notebooks](https://github.com/blog/1995-github-jupyter-notebooks-3)  they provided a compelling reason for R users try out the data document authoring power that [Jupyter Notebooks](https://jupyter.org/) provide.
![JupyR Screenshot](https://dl.dropboxusercontent.com/u/8064851/images/JuPyRScreen%20Shot.png)

One trouble with Jupyter is that, compared to R environments like the  awesome [Rstudio](http://www.rstudio.com/), installation and configuration of Jupyter plus the  [R2py cell magics](http://rpy.sourceforge.net/rpy2.html) or [R kernels]() required to run R is quite a lot greater. [This nice blog post](http://www.michaelpacer.com/maths/r-kernel-for-ipython-notebook) by MIke Pacer describes the non-trivial install for the Jutyper R kernel on OsX.

### Docker to the Rescue

[Docker](http://docker.com) allows reproducible, automated setup and exchange of complex computing environments like this. Although there are some great Docker images available  for [Jupyter Notebooks](https://registry.hub.docker.com/repos/ipython/) and for R through the [Rocker project]( https://github.com/rocker-org/rocker), there don't seem to be any that combine R installation with Jupyter.

I have created [a simple Dockerfile](https://github.com/cfljam/pyRat) that creates an image providing the Jupyter Scientific Python and tools to enable authoring notebooks with R content. The R kernel team helped out with [some nbconvert rendering and MIME content issues](https://github.com/IRkernel/IRkernel/issues/145).

In my next post I will describe some workflows for authoring and publishing Jupyter Notebooks with R content.

Many thanks to the Rocker and Jupyter teams who are doing an amazing job bringing us these expressive tools for data science!

Links
======
- [Introducing Rocker](http://dirk.eddelbuettel.com/blog/2014/10/23/)
- [Running Jupyter / IPython Notebooks on Docker for Mac/Windows](http://odewahn.github.io/docker-jumpstart/ipython-notebook.html)
