<!--
Copyright (c) 2023 Ernst Strüngmann Institute (ESI) for Neuroscience
in Cooperation with Max Planck Society
SPDX-License-Identifier: CC-BY-NC-SA-1.0
-->

# acme-demo
Demo and Examples showing how to use ACME.

## Setup

### Slidedeck

The slides were built with [Quarto](https://quarto.org/) version 1.2.313.
To make the Quarto VS Code extension (and Quarto's web server) pick up
the HTML build, first render the project

```shell
quarto render
```

Then generate a generic `index.html` by creating a symlink to the produced
`acme-demo.html`:

```shell
ln -s acme-demo.html index.html
```

### Demo Code

The Jupyter notebook `connectome-demo.ipynb` is intended as "supplementary
material" for the slidedeck: it illustrates how to concurrently compute
functional connectomes across a subject cohort.

The second thematic area covered by the included demo codes are
[Newton Fractals](https://en.wikipedia.org/wiki/Newton_fractal). The
notebook `fractal-intro.ipynb` provides a short introduction to this topic
(not focused on parallelization), the `fractal-demo.ipynb` notebook illustrates
how to compute Newton fractals in parallel.

## Usage

### Publish Slidedeck

First, set `embed-resources: false` (many hosters find ~100MB html files
suspicious...), then

```shell
quarto render acme-demo.qmd --output-dir demo23
```

Then copy the entire contents of `demo23` to the desired webspace and
check the result in a browser.

### Run Demos

Due to its memory requirements, the `connectome-demo.ipynb` notebook is best
run on a multi-node computing cluster. Conversely, `fractal-demo.ipynb` is
mainly CPU-intensive and can therefore be run on a (capable) multi-core
machine as well.

Both topics are stand-alone demos and can be analyzed independently. The
Jupyter notebooks are intended as exemplary illustrations, while the Python
modules provide the computational backbone for the notebooks.

