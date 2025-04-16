# SAGNN_CS__A_Resilient_Graph_Neural_Network_Framework_Against_Backdoor_Threats

This repository contains the implementation and analysis of Backdoor attacks on Graph Neural Networks both Traditional (GCN, GraphSage and GAT) and Higher Order Graph Neural Network (ESAN, SUN and SAGNN) and a new model SAGNN+CS. 


# Project Setup and Installation

This project uses a `requirements.txt` file to list all the Python packages (and their specific versions) that the project depends on. Follow the steps below to set up your environment and install the required dependencies.

## Step 1: Open a Terminal or Command Prompt

Navigate to your project directory containing the `requirements.txt` file.

## Step 2: Create and Activate a Virtual Environment

It is a good practice to create a virtual environment so that the packages you install do not interfere with system-wide packages.

### Creating a Virtual Environment

Run the following command to create a virtual environment (using `venv`):

```bash
python -m venv venv
```

### Activating the Virtual Environment

- **On Windows:**

  ```bash
  venv\Scripts\activate
  ```

- **On macOS/Linux:**

  ```bash
  source venv/bin/activate
  ```

## Step 3: Install Dependencies Using pip

With your virtual environment activated (or in your global environment), run the following command:

```bash
pip install -r requirements.txt
```

This command tells pip to read the `requirements.txt` file and install all the listed packages.

## Step 4: Verify Installation

To verify that a package is installed correctly, you can run:

```bash
python -c "import torch; print(torch.__version__)"
```

This should print the installed version of PyTorch.

## Using an IDE

If you're using an IDE such as VS Code, you can use its integrated terminal to run these commands.

```
use python main.py to run all the models.
You can also specify the model which you want the results for by writing python main.py model_type (example: sagnn+cs or sagn or sun or esan or gnn).
