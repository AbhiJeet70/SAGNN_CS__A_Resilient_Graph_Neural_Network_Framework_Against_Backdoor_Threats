# SAGNN_CS__A_Resilient_Graph_Neural_Network_Framework_Against_Backdoor_Threats

This repository contains the implementation and analysis of Backdoor attacks on Graph Neural Networks both Traditional (GCN, GraphSage and GAT) and Higher Order Graph Neural Network (ESAN, SUN and SAGNN) and a new model SAGNN+CS. 

<p align="center">
  <img src="images/abhi_system.png" width="500">
</p>

**Results on Cora dataset.** Each cell shows ASR/Accuracy. In the Baseline column the highest value is bolded; in each attack column, the lowest ASR is bolded and the highest clean accuracy is bolded.

| Model               | GNN Type    | Baseline    | SBA-Samp       | SBA-Gen        | GTA            | UGBA           | DPGBA          |
|---------------------|-------------|-------------|----------------|----------------|----------------|----------------|----------------|
| GCN                 | Traditional | 88.54       | 90/88.54       | 100/87.43      | 90/87.43       | 100/87.80      | 100/87.62      |
| GraphSage           | Traditional | **89.28**   | 100/**89.28**  | 100/**88.91**  | 100/**88.72**  | 100/88.17      | 100/88.17      |
| GAT                 | Traditional | 88.54       | 90/88.54       | 100/87.99      | 100/87.43      | 100/**88.72**  | 100/88.54      |
| SUN                 | Higher-Order| 87.62       | **0.0**/87.62  | **0.0**/87.43  | 20.0/86.88     | 20.0/87.25     | **0.0**/87.25  |
| ESAN-ego            | Higher-Order| 48.61       | **0.0**/48.61  | **0.0**/48.61  | 10.0/48.61     | 20.0/48.24     | **0.0**/48.98  |
| ESAN-edge_deleted   | Higher-Order| 86.69       | 63.33/87.12    | 63.33/87.83    | **0.0**/87.24  | 10.0/85.32     | 0.0/87.75      |
| ESAN-node_deleted   | Higher-Order| 86.69       | 63.33/87.83    | 63.33/87.27    | 10.0/87.99     | 10.0/82.26     | 0.0/87.06      |
| SAGN                | Higher-Order| 86.88       | **0.0**/87.70  | **0.0**/87.88  | 20.0/86.69     | 20.0/86.14     | **0.0**/86.32  |
| SAGNN+CS (Ours)     | Higher-Order| 87.06       | **0.0**/87.99  | **0.0**/87.80  | 10.0/86.88     | **10.0**/86.69 | **0.0**/87.62  |

**Results on CiteSeer dataset.** Each cell shows ASR/Accuracy. In the Baseline column the highest value is bolded; in each attack column, the lowest ASR is bolded and the highest clean accuracy is bolded.

| Model               | GNN Type    | Baseline   | SBA-Samp         | SBA-Gen          | GTA            | UGBA           | DPGBA          |
|---------------------|-------------|------------|------------------|------------------|----------------|----------------|----------------|
| GCN                 | Traditional | 75.19      | 90/75.19         | 90/73.38         | 90/73.38       | 90/73.53       | 90/72.78       |
| GraphSage           | Traditional | 75.34      | 100/75.34        | 100/75.79        | 90/76.09       | 100/76.09      | 100/75.64      |
| GAT                 | Traditional | 73.68      | 100/73.68        | 90/73.68         | 100/74.14      | 100/74.14      | 100/74.14      |
| SUN                 | Higher-Order| 75.04      | **0.0**/74.59    | **0.0**/73.98    | 3.33/72.63     | **0.0**/75.19  | **0.0**/74.44  |
| ESAN-ego            | Higher-Order| 24.96      | 45.0/25.26       | 45.0/25.26       | **0.0**/25.26  | **0.0**/25.11  | **0.0**/25.26  |
| ESAN-edge_deleted   | Higher-Order| 72.93      | 45.0/71.73       | 45.0/72.48       | **0.0**/72.48  | **0.0**/71.73  | **0.0**/73.08  |
| ESAN-node_deleted   | Higher-Order| 72.18      | 45.0/72.18       | 45.0/72.93       | **0.0**/73.23  | **0.0**/72.63  | **0.0**/72.33  |
| SAGN                | Higher-Order| **75.79**  | **0.0**/**76.84**| **0.0**/**76.09**| **0.0**/**76.84**| **0.0**/**76.54**| **0.0**/**76.39**|
| SAGNN+CS (Ours)     | Higher-Order| 71.88      | **0.0**/72.18    | 3.33/71.58       | 3.33/72.18     | 3.33/72.33     | 3.33/71.58     |

**Results on PubMed dataset.** Each cell shows ASR/Accuracy. In the Baseline column the highest value is bolded; in each attack column, the lowest ASR is bolded and the highest clean accuracy is bolded.

| Model               | GNN Type    | Baseline   | SBA-Samp         | SBA-Gen          | GTA            | UGBA           | DPGBA          |
|---------------------|-------------|------------|------------------|------------------|----------------|----------------|----------------|
| GCN                 | Traditional | 83.39      | 90/83.39         | 92.5/85.39       | 92.5/86.03     | 95/86.46       | 95/86.63       |
| GraphSage           | Traditional | 84.28      | 92.5/84.28       | 95/86.61         | 95/87.22      | 95/87.65       | 90/87.90       |
| GAT                 | Traditional | 85.27      | 95/85.27         | 95/86.66         | 97.5/86.96    | 97.5/87.07     | 97.5/87.09     |
| SUN                 | Higher-Order| 88.18      | **0.0**/**88.36**| **0.0**/**88.18**| 5.0/**88.38** | **2.5**/**88.66**| **0.0**/**89.04**|
| ESAN-ego            | Higher-Order| 34.29      | 63.33/34.21      | 63.33/34.11      | 13.33/34.11   | 10.0/34.11     | 3.33/34.09     |
| ESAN-edge_deleted   | Higher-Order| 87.80      | 63.33/87.12      | 63.33/87.83      | **0.0**/87.24 | 10.0/85.32     | **0.0**/87.75  |
| ESAN-node_deleted   | Higher-Order| 87.37      | 63.33/87.83      | 63.33/87.27      | 6.67/87.47    | 6.67/84.99     | **0.0**/87.88  |
| SAGN                | Higher-Order| 87.45      | **0.0**/87.70    | **0.0**/87.88    | 2.5/87.34     | **2.5**/87.52  | **0.0**/87.85  |
| SAGNN+CS (Ours)     | Higher-Order| **88.21**  | **0.0**/88.23    | **0.0**/88.05    | 5.0/**88.38** | 5.0/87.95      | **0.0**/88.08  |


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

```
## ⭐ Give a Star!

If you found this project useful or interesting, please consider giving it a star on GitHub!

## Use this bibtex to cite

```bibtex    
@article{Dhali2025SAGNN,
	author = {Dhali, Abhijeet and Dividino, Renata},
	journal = {Proceedings of the Canadian Conference on Artificial Intelligence},
	year = {2025},
	month = {may 19},
	note = {https://caiac.pubpub.org/pub/s0xf3xtc},
	publisher = {Canadian Artificial Intelligence Association (CAIAC)},
	title = {SAGNN+{CS}: A {Resilient} {Graph} {Neural} {Network} {Framework} {Against} {Backdoor} {Threats}},
}
```

## References 

```bibtex
@inproceedings{dhali2024power,
  title={The Power of Many: Investigating Defense Mechanisms for Resilient Graph Neural Networks},
  author={Dhali, Abhijeet and Dividino, Renata},
  booktitle={2024 IEEE International Conference on Big Data (BigData)},
  pages={3572--3578},
  year={2024},
  organization={IEEE}
}

@inproceedings{bevilacqua2022equivariant,
  title={Equivariant Subgraph Aggregation Networks},
  author={Beatrice Bevilacqua and Fabrizio Frasca and Derek Lim and Balasubramaniam Srinivasan and Chen Cai and Gopinath Balamurugan and Michael M. Bronstein and Haggai Maron},
  booktitle={International Conference on Learning Representations},
  year={2022},
}

@article{frasca2022understanding,
  title={Understanding and extending subgraph gnns by rethinking their symmetries},
  author={Frasca, Fabrizio and Bevilacqua, Beatrice and Bronstein, Michael and Maron, Haggai},
  journal={Advances in Neural Information Processing Systems},
  volume={35},
  pages={31376--31390},
  year={2022}
}

@inproceedings{zeng2023substructure,
  title={Substructure aware graph neural networks},
  author={Zeng, Dingyi and Liu, Wanlong and Chen, Wenyu and Zhou, Li and Zhang, Malu and Qu, Hong},
  booktitle={Proceedings of the AAAI conference on artificial intelligence},
  volume={37},
  number={9},
  pages={11129--11137},
  year={2023}
}

@inproceedings{kipf2017semi,
  title={Semi-Supervised Classification with Graph Convolutional Networks},
  author={Kipf, Thomas N and Welling, Max},
  booktitle={International Conference on Learning Representations},
  year={2017}
}

@inproceedings{velivckovic2018graph,
  title={Graph Attention Networks},
  author={Veli{\v{c}}kovi{\'c}, Petar and Cucurull, Guillem and Casanova, Arantxa and Romero, Adriana and Li{\`o}, Pietro and Bengio, Yoshua},
  booktitle={International Conference on Learning Representations},
  year={2018}
}

@inproceedings{hamilton2017inductive,
  title={Inductive Representation Learning on Large Graphs},
  author={Hamilton, William L and Ying, Rex and Leskovec, Jure},
  booktitle={Advances in Neural Information Processing Systems},
  year={2017}
}


@inproceedings{zhang2021backdoor,
  title={Backdoor attacks to graph neural networks},
  author={Zhang, Zaixi and Jia, Jinyuan and Wang, Binghui and Gong, Neil Zhenqiang},
  booktitle={Proceedings of the 26th ACM Symposium on Access Control Models and Technologies},
  pages={15--26},
  year={2021}
}


@inproceedings{xi2021graph,
  title={Graph backdoor},
  author={Xi, Zhaohan and Pang, Ren and Ji, Shouling and Wang, Ting},
  booktitle={30th USENIX Security Symposium},
  pages={1523--1540},
  year={2021}
}

@inproceedings{dai2023unnoticeable,
  title={Unnoticeable backdoor attacks on graph neural networks},
  author={Dai, Enyan and Lin, Minhua and Zhang, Xiang and Wang, Suhang},
  booktitle={Proceedings of the ACM Web Conference 2023},
  pages={2263--2273},
  year={2023}
}


@inproceedings{zhang2024rethinking,
  title={Rethinking graph backdoor attacks: A distribution-preserving perspective},
  author={Zhang, Zhiwei and Lin, Minhua and Dai, Enyan and Wang, Suhang},
  booktitle={Proceedings of the 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining},
  pages={4386--4397},
  year={2024}
}
