---
name: Fivox
version: "0.6"
major: 0
minor: 6
description: ITK library to sample events into regular volumes
updated: 11/03/17
homepage: https://github.com/BlueBrain/Fivox
repository: https://github.com/BlueBrain/Fivox.git
issuesurl: https://github.com/BlueBrain/Fivox/issues
packageurl: 
license: LGPL
maturity: EP
maintainers: Blue Brain Project (bbp-open-source@googlegroups.com)
contributors: hernando
readmetype: text/x-markdown
---
Fivox Documentation
===================

# Introduction

Fivox (Field Voxelization) is a library to generate volumetric images of
3d scalar fields (Local Field Potential, spike densities, voltage
sensitive dye), with loaders for the compartment, soma and spike reports
generated by the Neuron and NEST simulators used in the Blue Brain
Project. Fivox supports time animation. For more information see @ref
applications.

Fivox can be retrieved by cloning
the [source code](https://github.com/BlueBrain/Fivox).

The voxelize command line tool can be used to generate volumes for
ParaView or other volume rendering applications. When compiled with
Livre, launch Livre with one of the URIs used by the voxelize command line tool
as the volume parameter. The fivox data source will be loaded
automatically and selected through one of the volume URI schemes.

The sample-point command line tool can be used to extract the time series at a
specific 3D point. The output file can be then used as the input for the
plot2D.py python tool to generate a 2D graph showing the evolution of the data
over time.

To use the ImageSource programmatically, please refer to the @ref fivox
namespace documentation and voxelize command line tool.

![](doc/images/3m_spikes_scaled.jpg "Fivox spike densities rendered in Livre")
![](doc/images/paraview.jpg "Using a Fivox volume in ParaView")

## Features

Fivox provides the following major features:

* Converting compartment reports to volumetric LFP-like data
* Converting spike reports densities to volumetric data
* Converting compartment and surface area reports to volumetric data
* Time and animation support
* Extract the time series at a specific point

# Installation

Build Fivox from source:
~~~
git clone https://github.com/BlueBrain/Fivox
mkdir Fivox/build
cd Fivox/build
cmake ..
make
~~~

# Usage

All command line applications support the following parameters:

@snippet apps/commandLineApplication.h AppParameters
@snippet fivox/uriHandler.cpp VolumeParameters

The voxelize command line tool also supports:

@snippet apps/voxelize/voxelize.cpp VoxelizeParameters

The sample-point command line tool also supports:

@snippet apps/samplePoint/sample-point.cpp SamplePointParameters

# About

Fivox uses CMake to create a platform-specific build environment. The following
platforms and build environments are tested:

* Linux: Ubuntu 14.04, RHEL 6.6 (Makefile, x64)
* Mac OS X 10.9

The [API documentation](https://bluebrain.github.io/Fivox-0.6/index.html)
can be found on [bluebrain.github.io](https://bluebrain.github.io).

