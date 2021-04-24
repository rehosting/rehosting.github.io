---
layout: home
title: Home
---

Welcome! This webpage serves as information point for people interested in rehosting.
In particular, we provide an overview and categorization of existing work on rehosting, together with links to the corresponding papers, source code releases, and data sets.

## Rehosting?

Rehosting describes the process of building an execution environment for specific firmware images.

In comparison to emulation, which aims to create virtual platforms for specific instances of hardware, rehosting is *firmware-centric* and has security testing as main objective.

## Take me to the data!

We classify rehosting systems in four different categories:
* [Pure Emulation]({{ site.baseurl }}{% link tables/pure_emulation.md %})
* [Hardware-in-the-loop]({{ site.baseurl }}{% link tables/partial_emulation.md %})
* [Symbolic Abstractions]({{ site.baseurl }}{% link tables/symbolic_abstractions.md %})
* [Hybrid Approaches]({{ site.baseurl }}{% link tables/hybrid_approaches.md %})

Click on any of these links, or directly the ones in the footer, to get to the corresponding overview!

## Anything else I should know?

Yes! This webpage is based on our work ["SoK: Enabling Security Analyses of Embedded Systems via Rehosting."]({{ site.baseurl }}{% link assets/paper.pdf %} ), which will appear at AsiaCCS'21. The paper contains more information about the classification and rehosting in general.

However, the state of the art presented in the paper is just a snapshot at the time of writing. As it constantly evolves, we want to reflect updates on this webpage, maintained by the community!

If you want to add a rehosting system or update information about an existing one, please check our [faq]({{ site.baseurl }}{% link faq.md %}).

