# Handwritten Digit Classifier

This project explores handwritten digit classification with the MNIST dataset and PyTorch. The notebook includes data exploration, fully connected neural network experiments, a convolutional neural network, and model evaluation plots.

## Project files

- `developing-handwritten-digit-classifer.ipynb` — the main notebook.
- `requirements.txt` — Python dependencies, including the CUDA 12.6 PyTorch wheels.
- `best_model.pth`, `saved_model.pth` — saved model state dictionaries.
- `data/` — local MNIST dataset files (ignored by Git).
- `venv/` — local Python virtual environment (ignored by Git).

## Requirements

- Python 3.10 or newer
- NVIDIA GPU and compatible CUDA driver for GPU acceleration; a CPU can be used instead

## Setup

From the project directory, create and activate a virtual environment in PowerShell:

```powershell
py -m venv venv
.\venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

The requirements file installs PyTorch wheels for CUDA 12.6. If you do not need GPU support or those wheels do not match your setup, install the PyTorch and torchvision builds recommended for your system from the [official PyTorch installation guide](https://pytorch.org/get-started/locally/), then install the remaining packages listed in `requirements.txt`.

## Dataset

The notebook loads MNIST with `download=False`, so the dataset must already be present under `data/` in the layout expected by `torchvision.datasets.MNIST`. To let torchvision download it automatically, change `download=False` to `download=True` in the dataset-loading cell and run that cell.

## Run the notebook

```powershell
jupyter lab
```

Open `developing-handwritten-digit-classifer.ipynb` and run the cells from top to bottom. Training can take several minutes depending on your hardware. The notebook checks for CUDA and uses it when available.

## Outputs

The notebook trains and evaluates dense and convolutional networks, plots loss and accuracy, displays sample predictions, and builds a confusion matrix. Training cells save model parameters to `.pth` files in the project directory.

## Git notes

The `.gitignore` file excludes `venv/` and `data/`, keeping the local environment and dataset out of future commits. Model checkpoints are currently present in the repository; add `*.pth` to `.gitignore` if you also want to keep checkpoints out of future commits.
