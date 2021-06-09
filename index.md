---
layout: home
title: Home
---

Welcome! This webpage aims to provide an overview of the field of rehosting and a curated collection of relevant resources.
Informally, rehosting is the process of getting firmware from an embedded system to run in an environment where you can introspect on its behavior.
This is useful for a variety of tasks such as reverse engineering, user training, and conducting dynamic analyses of firmware.

In particular, we provide an overview and categorization of existing work on rehosting, together with links to the corresponding papers, source code releases, and data sets based off our paper [SoK: Enabling Security Analyses of Embedded Systems via Rehosting](https://dspace.mit.edu/handle/1721.1/130505).  However, the state of the art presented in the paper is just a snapshot at the time of writing. As it constantly evolves, we want to reflect updates on this webpage, [maintained by the community](https://github.com/rehosting/rehosting.github.io).

What's Rehosting?
---
In contrast to a hardware emulation system which comprehensively reproduces the features of specific hardware in a virtual environment, a rehosted embedded system is designed around a specific firmware image and must only reproduce the necessary hardware features that enable the firmware (or relevant components thereof) to run sufficiently in a virtual environment. We define these terms as follows:

**Virtual Environment (VE)**: A software environment in which code can be executed transparently.

**Hardware Emulation System (HES)**: A VE designed to accurately recreate the features of one or more selected pieces of hardware. Commonly called an emulator.

**Rehosted Embedded System (RES)**: A combination of a firmware image and VE designed to sufficiently recreate the firmware’s hardware dependencies such that analyses produce results representative of the firmware running on its original hardware.

**Rehosting**: The process of building an RES for a given embedded system to enable a specified analysis task. May include modifications to the firmware.

**Virtual Execution Engine (VXE)**: A mechanism for interpreting instructions for a given ISA in a VE.


What's the Rehosting Process?
---
We consider rehosting to fundamentally be an iterative process. You start with a firmware you wish to emulate and some knowledge of how the system should behave. You then run your firmware under emulation and observe its behavior. By observing the behavior of the system, you can decide if it is successfully rehosted. If it is not, you can study your observations to precisely identify where the system's behavior diverges from what you expect. You can then modify either your virtual execution environment or the firmware itself to rectify significant differences. You then can repeat this process until you believe the firmware is successfully rehosted.

![the rehosting process](/assets/images/process.png){: width="600" }


What are Open Problems in Rehosting?
---
We identify five key challenges that remain unsolved in the rehosting space:
* Building VXEs for new CPUs/ISAs
* Widespread adoption of modeling standards
* Handling peripheral behavior
* Quantifying fidelity of a rehosted system
* Facilitating rehosting for complex systems
We hope to see the research community continue working on these problems in the future.

Tell me more
---
Check out our paper [SoK: Enabling Security Analyses of Embedded Systems via Rehosting](https://dspace.mit.edu/handle/1721.1/130505) presented at AsiaCCS 2021 to learn more about rehosting.

