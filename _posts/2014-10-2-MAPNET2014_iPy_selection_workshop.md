---
layout: post
title: MAPNET Workshop 2014
published: true
---

## Executable Explanations at MAPNET

![mapnetlogo](http://www.visg.co.nz/images/mapnet.jpg)

### MAPNET Selections Sweeps and iPython Workshop Wednesday 22 October 2014 

As part of the 2014 [MAPNET Workshop](http://www.agresearch.co.nz/news/events/Pages/MAPNET.aspx) I will present a  some examples of using iPython Notebooks to complement demonstrations of the [selection pipeline](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4144660/) developed by VISG colleagues.
The aim of the workshop will be to demonstrate the possibilities and power of *learning, developing and sharing*  analyses of genetics data in the [iPython Notebook](http://ipython.org/notebook.html) ecosystem. 

### Topics to be demonstrated

- use of Unix Shell, Python and R cell magics 
- Manipulation of vcf ([Variant Call Format](http://en.wikipedia.org/wiki/Variant_Call_Format)) data 
- interval operations with [BedTools](http://bedtools.readthedocs.org/en/latest/)
- tabular data handling with [Pandas](http://pandas.pydata.org/pandas-docs/stable/index.html)
- plotting with matplotib and ggplot2
- saving and sharing notebooks through [GitHub Gist](https://gist.github.com/) 

### Workshop Software and Pre-Requisites 

Participants may just choose to look and learn and ask questions, but can also pre-install software to allow them to run the examples during or after. 

The examples will all run on an Ubuntu Linux Virtual machine in Oracle Virtualbox. We will provide a machine image at the workshop **Or** you can install from scratch using the wonders of Vagrant. Here's how:

- Set up a user account at https://github.com/
- install [Git](http://git-scm.com/)
- Install [Oracle VirtualBox](https://www.virtualbox.org/)
- Install [Vagrant](http://git-scm.com/)
- Open up a terminal (Git For Windows comes with **Git Bash** ) 
- Create the Virtual Machine by issuing the following commands:

    git clone --recursive  https://github.com/cfljam/statgen_py_vm.git

    cd statgen_py_vm
    
    vagrant up
    
**Note** you may need to re-run the provisioning step to complete the install if stuff times out, by typing:

	vagrant provision

The first time you run this, it will take  while to fetch the base box and install software. Once it all completes you have a fresh virtual machine providing an iPython server you can access from the host machine at http://localhost:8888/. You can also access this from the shell by typing

    vagrant ssh


and do what you like as 

- User *vagrant* 
- password *vagrant*