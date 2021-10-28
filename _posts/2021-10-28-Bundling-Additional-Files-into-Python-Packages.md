---
title: "Bundling Additional Files into Python Packages"
date: 2021-10-28
permalink: /blog/2021/10/bundling-files/
layout: single
author_profile: true
tags:
  - python
  - software
---

What
======
This note is about packaging Python modules so that the users can install the source files and also additional files that are used by the source files. 


Why
======
Suppose a Python package loads a pre-trained classifer saved in a .sav file and uses it for a classification task. Therefore, our local installation of this package should be able to access the .sav file, which would be missing in our local machine unless it's bundled into the package distribution. 

How
======
There are different ways of doing this. One solution is to store the files in the package folder and point them in a Manifest file. See the [<span style="color:#337ab7">`Manifest`</span>](https://github.com/alan-turing-institute/ptype/blob/develop/Manifest.in) and [<span style="color:#337ab7">`sav`</span>](https://github.com/alan-turing-institute/ptype/blob/develop/ptype/LR.sav) file for an example.

Note that you also need to set <span style="color:#337ab7">`include_package_data`</span> to <span style="color:#337ab7">`True`</span> in the setup file as in the [<span style="color:#337ab7">`setup`</span>](https://github.com/alan-turing-institute/ptype/blob/develop/setup.py) file.

References:  
===========
<https://github.com/pypa/sampleproject/issues/30#issuecomment-426993883>  
<https://packaging.python.org/guides/using-manifest-in/#using-manifest-in>
