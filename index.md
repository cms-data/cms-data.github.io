---
layout: default
---

## What's cms-data?

[The cms-data github organization](http://github.com/cms-data) is meant to kept large
file (e.g. weights) which are requested by a given package in CMSSW but which
are deemed to be too large to stay in the cms-sw/cmssw repository.

This is of course not meant to contain actual CMS datafiles.

## Repository structure:

Packages should be called according to their CMSSW counterparts, just with a
dash (`-`) in place of a slash (`/`). E.g.:

    <subsystem>/<package>

datafiles should be kept in a flat structure inside the repository.
  
## Packaging datafiles into an RPM

In order to be picked up by CMSSW the datafiles need to be packaged in a RPM.
This is done automatically once a spec file is provided in
[CMSDIST](http://github.com/cms-sw/cmsdist). By convention, the spec file needs
to be called:

```
data-<subsy<package>.spec
```

and have the following structure:

    ### RPM cms data-<subsystem>-<package> <tag>

    %prep

    ## IMPORT data-build-github

where `<tag>` is some tag or hash given to the repository found in this
organization.
