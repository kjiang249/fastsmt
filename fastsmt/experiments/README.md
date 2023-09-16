# Intro

Here we describe how to reproduce results reported in [Z3alpha](https://github.com/JohnLu1990/z3alpha) submission to AAAI24 Student Program. Note that you need to use Z3 version `12.2.2` to get the same results. Please consult setup instructions on this.

# Downloading benchmarks

We provide scripts to download the benchmarks used in our experiments from this repository.
After the download relevant datasets can be found in corresponding folders - e.g. `experiments/data/sage2/train/` will contain training set to be used for synthesis on *Sage2* benchmark. 

#### SRI repository

```bash
$ ./download_data.sh
```

# Learning and synthesis

You can find strategies resulting from our experiments in `final_strategies` subdirectory. Concretely, in `all` subdirectory you can find all learned strategies and in `smt2` subdirectory you can find final synthesized strategies in SMT2 format. Next, we describe how to re-run these experiments.

## Learning 

In order to reproduce our experiment on Sage2 benchmark use the following command:

```bash
(venv) $ ./experiments/runners/run_sage2.sh
```

This will sequentially run all models (neural network, bilinear, evolutionary, random and bfs model) used in our experiments. For other benchmarks use appropriate scripts (e.g. ```./experiments/runners/run_leipzig.sh ```). 

## Synthesis

In order to synthesize single master strategy out of all created strategies run (e.g. for Sage2):

```bash
(venv) $ ./experiments/synthesis/tree_sage2.sh
```
