# Usage Guide for the SOAR Implementation

This guide provides step-by-step instructions to set up your environment, clone the repository, and run the provided Jupyter Notebook to reproduce the experimental results for the SOAR project.


---

## 1. Clone the Repository

Open your terminal (or use a Git client) and clone the repository using the following command:

```
git clone https://anonymous.4open.science/r/ECE-570-Research-Paper-SOAR/
```

This will create a local copy of all the project files, including the Jupyter Notebook (`final_soar_implementation.ipynb`), data files, and any supporting modules.

---

## 2. Environment Setup

### Prerequisites

- **Python:** Version 3.7 or higher.
- **Jupyter Notebook or Google Colab:** The notebook works in either environment.
- **GPU (Optional):** A CUDA-enabled GPU is recommended for training and indexing to achieve faster performance (Google Colab is a good option if you do not have a local GPU).

### Installing Dependencies


Install the required packages using the included `requirements.txt` file:

```
pip install -r requirements.txt
```

*Note: If running in Google Colab, you can install dependencies by adding a cell with `!pip install -r requirements.txt`.*

---

## 3. Running the Notebook

The entire project is contained within the notebook `final_soar_implementation.ipynb`. This notebook includes data preprocessing, SOAR model training, FAISS index construction (both IVF-PQ and HNSW), and evaluation of experimental results.

### To Run Locally:

1. Open the notebook with Jupyter Notebook or JupyterLab:
   ```
   jupyter notebook final_soar_implementation.ipynb
   ```
2. Execute all cells sequentially (you can use the “Run All” command).

### To Run in Google Colab:

1. Upload the notebook to Google Colab via the “Open notebook” interface, or open the repository link in Colab if configured.
2. Run each cell in sequence. Make sure to select a GPU runtime via `Runtime > Change runtime type` and choose “GPU” for faster execution.

---

## 4. Expected Outputs

- **Data Preprocessing:**  
  The notebook will load the dataset (e.g., SIFT-128 or GloVe embeddings), normalize the data, apply PCA if needed, and run MiniBatchKMeans clustering.
  
- **Training:**  
  The SOAR model will be trained with orthogonality constraints. You’ll see training loss values and other diagnostic information as the epochs progress.

- **Index Building:**  
  The notebook constructs the FAISS index using both IVF-PQ and HNSW. Printouts or plots of retrieval metrics (e.g., Recall@10, query latency) will be generated.

- **Evaluation:**  
  At the end, the notebook will display the evaluation results that match those reported in the paper.

---

## 5. Troubleshooting

- **Dependencies:**  
  If you encounter issues, verify that the Python version and packages specified in `requirements.txt` are correctly installed. Use `pip list` to check for installed versions.

- **Data Paths:**  
  Ensure that any dataset files referenced in the notebook are in the appropriate directories. Adjust file paths in the notebook cells if necessary.

- **Runtime Environment:**  
  If running locally without a GPU, note that training and indexing may be slower. Switching to a GPU (e.g., via Google Colab) is recommended.

---

By following these steps, you should be able to reproduce all experiments and results as described in the term paper. If you have any issues, please consult the troubleshooting section or check the repository’s README for additional details.
