---
layout: default
title: Getting Started
permalink: getting_started/
---

# Getting Started

## How to compile
PDES-MAS is hosted on the Github repository. Use `Git` to clone it to your local repository:

```$shell
git clone https://github.com/PDES-MAS/PDES-MAS.git
cd ./PDES-MAS
```

PDES-MAS uses [CMake](https://cmake.org/) to manage its build process. Typically, you should use the `Release` target 
to achieve the best performance, and use `Debug` only when you're debugging it. To build PDES-MAS, first, ensure that 
you have `CMake` installed. You can either use a package manager of download it manually from `CMake` official site.

Then, use `CMake` to generate the `Makefile`, build it in the `./bin` directory:
```shell
mkdir bin
cd bin
cmake -DCMAKE_BUILD_TYPE=Release ..
```

After the `Makefile` has been generated, use `make` to build it:

```shell
make -j5
```

# Running Example Code

There are already some standard examples of multi-agent system model, [Tileworld](http://www.tworld-ai.com/resrc/introducing_the_tileworld.pdf) is one of them.  
And we've provided an example of this kind of agent. You can find it in your build directory after successfully built PDES-MAS. 
To run and test it, just use `mpirun`:
```shell
mpirun -np 15 tileworld
```

