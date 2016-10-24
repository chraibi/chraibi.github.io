---
layout: post
title:  "Getting started with JuPedSim"
image: '/assets/img/totoro.png'
date:   2016-10-25 10:00:00
tags:
- JuPedSim, Pedestrian Dynamics
description: 'JuPedSim: Get started'
categories:
- JuPedSim
serie: learn
---


In this tutorial we will see how to use [JuPedSim](www.jupedsim.org). 
I will focus only on jpscore (simulation module).

![simulation](../assets/img/simu.png)

Besides, I will take the example of CLion.
(but you can still use your preferred IDE..)

You can *see* this tutorial on [YouTube](https://www.youtube.com/watch?v=Achsd2EpJbI).

**Download the code of `jpscore`** 

- From [repository](https://cst.version.fz-juelich.de/jupedsim/jpscore)
- Once the download is finished, change to the directory of the code. 
- The git branch will be by default `develop`. This is the main branch of the code.

**Create a project**

- Open `CLion`.
- Open a project. The "project file" in our case is the file `CMakelists.txt`. 
  `CLion` will read it, and then index the whole project. This may take some time.
  (this initialization process takes place only for the first setup of the project.)
- When `CLion` is done with the indexing, start building the project. 
  --> click on `Build`. 
- `jpscore` has quit a lot of source files. Therefore, the compilation of the whole project takes some time ...
- In the directory inputfiles as well as in demos you can find some `inifiles` to start with. 
- After running a simulation let's have a look at the result.
  You can edit the inifile to have more control over the simulation. The result of the simulation is in the file trajectories.xml. 

**Visualization of the results** 

- Open `jpsvis`[^1] and visualize the trajectory-file.
- Next time I will show how to work with jpsvis. 

**Questions** 

- If you have any questions or problems please open an issue. Use the [Gitlab issue tracker](https://cst.version.fz-juelich.de/jupedsim/jpscore/issues). 




[^1]: `jpsvis` comes with an executable for Windows and a `dmg-file` for Mac OS X.