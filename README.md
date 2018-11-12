# ExpressionEngine® User Guide

The public user guide repository for the [ExpressionEngine](https://expressionengine.com) project. The online version of the user guide is hosted at [docs.expressionengine.com](https://docs.expressionengine.com).

## Setup Instructions

The ExpressionEngine user guide uses Sphinx to manage the documentation and output it to various formats. Pages are written in human-readable ReStructured Text format.

## Prerequisites

To build the user guide, you must have Docker installed. If you need to install it, the easiest way is with [Docker Desktop](https://www.docker.com/products/docker-desktop).

## Editing and Creating Documentation

All of the source files exist under `source/` and is where you will add new documentation or modify existing documentation. We recommend working from feature branches and making pull requests to the `stability` branch of this repo.

## So where's the HTML?

The HTML documentation is what we care most about, as it is the primary documentation that users will encounter. Since revisions to the built files are not of value, they are not under source control. This also allows you to regenerate as necessary if you want to "preview" your work. Generating the HTML is very simple. From the root directory of your fork, issue this command:

```
eetools make
```

If you want to rebuild all files from scratch instead of just the changed ones, use:

```
eetools make -c
```

Note, on MAMP you may get a `eetools: command not found`, as your shell maybe isn’t looking in the current working directory. Just use `./eetools` instead.

You will see it do a whiz-bang compilation, at which point the fully rendered user guide and images will be in `build/html/`. After the HTML has been built, each successive build will only rebuild files that have changed, saving considerable time. If for any reason you want to "reset" your build files, use the `-c` flag for a "clean" build.

## Style Guideline

Please refer to [style_guide.rst](style_guide.rst) for samples and ReST convention standards used in the ExpressionEngine user guide. Please note that standard ReST renders will not be able to parse all of the directives, as many are specific to Sphinx.
