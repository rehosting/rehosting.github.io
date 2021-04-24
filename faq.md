---
layout: page
title: F.A.Q.
permalink: /faq/
---

# Q: What does the "target type" column mean?

The types are adopted from the paper "[What You Corrupt Is Not What You Crash: Challenges in Fuzzing Embedded Devices"](http://s3.eurecom.fr/docs/ndss18_muench.pdf), which categorizes embedded devices and firmware based on the deployed operating system.

In short, the different system types are:
* **Type 0**: Not an embedded system
* **Type 1**: System based on a general purpose OS retrofitted for embedded application
* **Type 2**: System with operating system specifically created for embedded targets
* **Type 3**: System with no operating system abstraction at all, running "bare-metal" firmware

# Q: I found a mistake, what should I do?

Great! Mistakes can happen and we are happy to fix them.
Feel free to open a issue on our [github repository](https://github.com/rehosting/rehosting.github.io/issues) to kick off discussion with us!

# Q: How do I add a new rehosting system?

First, fork and clone our repository:
```shell
$ git clone git@github.com:[your_github_user_name]/rehosting.github.io.git
$ cd rehosting.github.io.git
```

Afterwards, copy the [`template.yml`](https://github.com/rehosting/rehosting.github.io/blob/main/assets/template.yml) file into the the `_data` directory, using the system name as destination name:
```shell
$ cp assets/template.yml _data/awesome_new_system.yml
```

Now edit the new `.yml` file to your liking; `|` denotes options from which you will have to choose. Once done, you can test if everything renders correctly locally (requires a local installation of ruby and Bundler):
```shell
$ bundle install
$ bundle exec jekyll serve
```

Now, if everything succeeded, you should be able to see your local copy of this website at `http://127.0.0.1:4000/`. If everything is to your liking, push your updates and send us your pull request!



# Q: CVE number? Logo? Am I affected?

The work on this webpage is purely educational and summarizes the state of the art. No attacks have been carried out within this work, so these questions do not apply here.

# Q: Who is behind this?

The [paper]({{ site.baseurl }}{% link assets/paper.pdf %}) on which the presented classification is based on was written by:
Andrew Fasano, Tiemoko Ballo, Marius Muench, Alexander Bulekov, Brendan Dolan-Gavitt, Manuel Egele, Aurélien Francillon, Long Lu, Nick Gregory, Davide Balzarotti, and William Robertson.

