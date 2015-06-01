---
published: false
---

## Using R in Jupyter Notebooks on Docker

When Github [enabled rendering of Jupyter Notebooks](https://github.com/blog/1995-github-jupyter-notebooks-3) recently they provided a compelling reason for R users try out the data document authoring power that is [Jupyter Notebooks](https://jupyter.org/). One trouble with Jupyter is that, compared to R environments like the  awesome [Rstudio](http://www.rstudio.com/), installation and configuration of Jupyter plus the  [R2py cell magics](http://rpy.sourceforge.net/rpy2.html) or [R kernels]() required to run R is quite a lot greater. [This nice blog post](http://www.michaelpacer.com/maths/r-kernel-for-ipython-notebook) describes the non-trivial install for the Jutyper R kernel on OsX.

### Docker to the Rescue

[Docker](http://docker.com) allows automation of the setup and exchange of complex computing environments like this. Although there are some great Docker images available  for [Jupyter Notebooks](https://registry.hub.docker.com/repos/ipython/) and for R through the [Rocker project]( https://github.com/rocker-org/rocker), there don't seem to be any that combine R installation with Jupyter.

I created a simple Dockerfile 




Links
======
- [Introducing Rocker](http://dirk.eddelbuettel.com/blog/2014/10/23/)
- [Running Jupyter / IPython Notebooks on Docker for Mac/Windows](http://odewahn.github.io/docker-jumpstart/ipython-notebook.html)

