# Quantum Lab

## Overview

Quantum Lab is a public template for quantum computing with MIT's [TorchQuantum](https://github.com/mit-han-lab/torchquantum) and Lightning AI's [PyTorch Lightning](https://lightning.ai/docs/pytorch/latest/).

The recommended way for Quantum Lab users to create new repos is with the [use this template](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) button.

## Source Module

`quantumlab.core` should contain code for the Lightning Module and Trainer.

`quantumlab.components` should contain experiment utilities grouped by purpose for cohesion.

`quantumlab.pipeline` should contain code for data acquistion and preprocessing, and building a TorchDataset and LightningDataModule.

`quantumlab.serve` should contain code for model serving APIs built with [FastAPI](https://fastapi.tiangolo.com/project-generation/#machine-learning-models-with-spacy-and-fastapi).

`quantumlab.lab` should contain code for the command line interface built with [Typer](https://typer.tiangolo.com/) and [Rich](https://rich.readthedocs.io/en/stable/).

`quantumlab.pages` should contain code for data apps built with streamlit.

`quantumlab.config` can assist with project, trainer, and sweep configurations.

## Base Requirements and Extras

Quantum Lab installs minimal requirements out of the box, and provides extras to make creating robust virtual environments easier. To view the requirements, in [setup.cfg](setup.cfg), see `install_requires` for the base requirements and `options.extras_require` for the available extras.

The recommended install is as follows:

```sh
python3 -m venv .venv
source .venv/bin/activate
pip install -e ".[all]"
```

## M Series Macs

There is an issue with the build wheels of one qiskit's dependencies, `tweedledum`. We can install torchquantum without dependencies using the follow; however, this also means we will need to install dependencies as we begin to work through examples. As such, it is recommended to use this Quantum Lab in a Linux environment.

```sh
source .venv/bin/activate
pip install -r requirements.txt
pip install --no-deps git+https://github.com/mit-han-lab/torchquantum.git
```
