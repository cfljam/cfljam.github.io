---
layout: post
title: MAPNET Workshop 2014
published: true
---

# Executable Explanations at MAPNET

![mapnetlogo](http://www.visg.co.nz/images/mapnet.jpg)

## MAPNET Selections Sweeps and iPython Workshop Wednesday 22 October 2014 

As part of the 2014 [MAPNET Workshop](http://www.agresearch.co.nz/news/events/Pages/MAPNET.aspx) I will present a  some examples of using iPython Notebooks to complement demonstrations of the [selection pipeline](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4144660/) developed by VISG colleagues.
The aim of the workshop will be to demonstrate the possibilities and power of *learning, developing and sharing*  analyses of genetics data in the [iPython Notebook](http://ipython.org/notebook.html) ecosystem. iPython Notebooks provide a scalable and portable way to organise use of the diverse programmes and code tools necessary to deal with large scale genetic and genomic data. 

## Topics to be demonstrated

- use of Unix Shell, Python and R cell magics 
- Manipulation of vcf ([Variant Call Format](http://en.wikipedia.org/wiki/Variant_Call_Format)) data using [vcftools](http://vcftools.sourceforge.net/) , [vcflib](https://github.com/ekg/vcflib) and [bcftools](http://samtools.github.io/bcftools)
- interval operations with [BedTools](http://bedtools.readthedocs.org/en/latest/)
- tabular data handling with [Pandas](http://pandas.pydata.org/pandas-docs/stable/index.html)
- plotting data with matplotib and ggplot2
- saving and sharing notebooks through [GitHub Gist](https://gist.github.com/) 

## Workshop Software and Pre-Requisites 

Participants may just choose to look and learn and ask questions, but can also pre-install software to allow them to run the examples during or after. The intention is to demonstrate what is possible and provide motivation for learning more about these technologies.  

### Other Options
If you just want to explore use of Scientific Python and iPython Notebooks for general data work I can recommend  installing [Anaconda Python](https://store.continuum.io/cshop/anaconda/) for Windows and Mac. If you want to try out a simpler but more robust Vagrant VM fro Data Science check out the [DataScienceToolBox] (http://datasciencetoolbox.org/).

### Our (Prototype) Virtual Machine for Statistical Genetics

The examples all run on an Ubuntu Linux Virtual machine in Oracle Virtualbox, so the minimal requirement is to install Oracle VirtualBox. We will provide a machine image at the workshop. 
If you have more time and experience, you can install from scratch using the wonders of [Vagrant](https://www.vagrantup.com/). Here's how:

- Set up a user account at https://github.com/
- install [Git](http://git-scm.com/)
- Install [Oracle VirtualBox](https://www.virtualbox.org/)
- Install [Vagrant](https://www.vagrantup.com/)
- [Read the Readme] (https://github.com/cfljam/statgen_py_vm/blob/master/README.md), especially if you are behind a firewall
- Open up a terminal (Git For Windows comes with **Git Bash** ) 
- Create the Virtual Machine by issuing the following commands:

    git clone --recursive  https://github.com/cfljam/statgen_py_vm.git

    cd statgen_py_vm
    
    vagrant up
    
**Note** you may need to re-run the provisioning step to complete the install if stuff times out, by typing:

	vagrant provision

The first time you run this, it will take  while to fetch the base box and install software. Once it all completes you have a fresh virtual machine providing an iPython server you can access from the host machine at http://localhost:8888/. You can also access this from the shell by typing

    vagrant ssh


and do what you like inside the VM as 

- User *vagrant* 
- password *vagrant*

Restart the VM from the host machine shell 

	vagrant reload

or stop by

	vagrant halt

My  intention is to keep updating this Vagrant definition, so in future you can just generate and updated install by repeating the above process, or just pulling updated from GitHub. ie. from the command line inside the repository type

	git pull 
    vagrant reload --provision
    
	