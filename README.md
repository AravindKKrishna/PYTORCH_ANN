# Iris Classification with PyTorch

A small neural-network project that classifies Iris flowers using their sepal and petal measurements. The model is trained and evaluated in the `iris.ipynb` Jupyter notebook.

## Features

- Loads the Iris dataset from `Iris.csv`
- Uses four measurements as model inputs:
  - Sepal length
  - Sepal width
  - Petal length
  - Petal width
- Trains a feed-forward PyTorch neural network
- Evaluates the model on a held-out test set
- Saves the trained weights to `iris_model.pt`

## Project Structure

| File | Description |
| --- | --- |
| `iris.ipynb` | Data preparation, model training, evaluation, prediction, and model saving |
| `Iris.csv` | Iris flower dataset |
| `iris_model.pt` | Saved PyTorch model weights |
| `requirements.txt` | Python dependencies |

## Setup

Create and activate a virtual environment, then install the dependencies:

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

The notebook also uses Jupyter, pandas, and matplotlib. Install them if they are not already available:

```bash
pip install jupyter pandas matplotlib
```

## Run the Notebook

Open `iris.ipynb` in VS Code or start Jupyter Notebook from the project directory:

```bash
jupyter notebook iris.ipynb
```

Run the cells from top to bottom. The notebook loads the CSV, converts the species labels to numeric classes, trains the model for 100 epochs, evaluates it, and saves the weights to `iris_model.pt`.

## Model

The network has the following structure:

```text
4 input features -> 8 neurons -> 9 neurons -> 3 output classes
```

The species labels are encoded as:

| Class | Species |
| --- | --- |
| `0` | Iris-setosa |
| `1` | Iris-versicolor |
| `2` | Iris-virginica |

The trained model uses `CrossEntropyLoss` and the Adam optimizer.

## Requirements

- Python 3.8+
- PyTorch
- torchvision
- torchaudio
- scikit-learn
- pandas
- matplotlib
- Jupyter Notebook or VS Code with the Jupyter extension

## Notes

The saved `iris_model.pt` file contains the model state dictionary. To load it, create the same `Model` architecture and call `load_state_dict` with the saved file.