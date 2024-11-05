


# Leveraging Excel for Data-Driven Insights: Sales Analysis


## Introduction

This repository contains a comprehensive analysis of sales data using Microsoft Excel. The analysis covers descriptive statistics, data visualization, and predictive modeling techniques. The goal is to extract valuable insights from the data to inform business decisions and improve sales performance.

In this project, we utilize MS Excel Tool to Analyse The Sample Superstore Sales released with Tableau v2022.1. create four predictive models aimed at answering the following questions:

### 1- Can we effectively forecast ED wait times in minutes to better manage patient flow and optimize resource allocation?

### 2- Can we predict whether the ED wait time will be within a normal range (<= 30 minutes) or high (> 30 minutes) based on a predefined threshold?

### 3- Can we estimate the duration of the ED visit in minutes using patient demographic information, clinical assessments, and initial operational metrics?

### 4- Can we predict if the LOV will fall within a normal range (<= 120 minutes) or will be high (> 120 minutes) using a specific threshold for classification?

By integrating both regression and classification methodologies, we aim to provide comprehensive insights and actionable recommendations for improving ED operations, ultimately contributing to a more efficient and patient-friendly healthcare system.
  
  
- # Steps to setup and run the Jupyter Notebooks
  
  ## Prerequisites
  
  - Ensure that Git is installed on your system.
  - Ensure that Python is installed on your system.
  - Ensure that you have access to the repository https://github.com/jeancheri/EDPredictiveEfficiency.git
  
  ## A) Initial Setup
  
  ### I - Clone the Repository:
  
  To clone the project repository, you'll need to identify the path where you want the project to reside on your local machine. Here's how to do it:
  
  1. Open your command prompt or terminal.
  
  2. Navigate to the directory where you want to clone the project using the `cd` command. For example:
     ```bash
     cd path/to/your/desired/directory
     ```
     
  3. Once you are in your chosen directory, run the git clone command with the project's repository URL.
  
  ```bash
  git clone https://github.com/jeancheri/EDPredictiveEfficiency.git
  cd EDPredictiveEfficiency
  ```
  
  Remember to take note of this path or bookmark it in your terminal for quick access, as you will likely return to this directory frequently during the course of your project.
  
  ### II - Creating Data Subdirectories
  
  In order to organize your project's data efficiently, open your command prompt or terminal and navigate to your `EDPredictiveEfficiency` project directory. Once there, run the following command to create the necessary subdirectories for data storage:
  
  ```bash
  mkdir -p data/{features,processed,raw,test,train,validation}
  ```
  
  This will create `features`, `processed`, `raw`, `test`, `train`, and `validation` folders inside a `data` directory.
  
  ### III - Downloading and Storing Raw Data
  Ensure that you are in the root of the `EDPredictiveEfficiency` directory and follow these steps to download the raw dataset:
  
  1. Click on the following link to download the `nhamcs14.sas7bdat` dataset file:
     [Download nhamcs14.sas7bdat](https://drive.google.com/file/d/1oKac8baXPlSrwSH9va_XiSJnswyRRkzg/view?usp=sharing)
  
  2. After the download is complete, move the downloaded file into the `data/raw` directory you created earlier.
  
  By following these steps, you'll have a well-structured data directory ready for use in your project.
  
  
  
  ### IV - Install Poetry (optional, if not already installed):
  
  - **Windows:**
  
    Open PowerShell as Administrator and run:
  
    ```powershell
    (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -
    ```
  
  - **Linux/MacOS:**
  
    Open a terminal and execute:
  
    ```bash
    curl -sSL https://install.python-poetry.org | python3 -
    ```
  
  ### V - Set up the Project with Poetry(optional, if not already done):
  
  1. Navigate to the cloned project directory (if you are not already there):
  
  ```bash
  cd /path_where_you_cloned_the_project/EDPredictiveEfficiency
  ```
  
  2. Install the project dependencies using Poetry:
  
  ```bash
  poetry install
  ```
  
  This will read the `pyproject.toml` file and install all necessary dependencies into a virtual environment specific for this project.
  
  3. Then, activate the poetry environment: 
  
  ```bash
  poetry shell
  ```
  
  This will spawn a new shell subprocess, which is configured to use the created virtual environment.
  
  ### VI - Run Notebook with the Pre-configured Kernel
  
  For executing code, we recommend using Jupyter Notebook, JupyterLab, or VSCode or any similar tools, as they offer comprehensive support for Jupyter notebooks.


#### Install and Configure ipykernel

Ensure that `ipykernel` is installed in your Poetry environment. This is required for using the environment as a Jupyter kernel, enabling support for Jupyter notebooks in tools such as Jupyter Notebook, JupyterLab, or VSCode.

**Add `ipykernel` via Poetry:**

```bash
poetry add ipykernel
```

**Register the Kernel:**

```bash
poetry run python -m ipykernel install --user --name=edpredictiveefficiency
```

This setup allows the Poetry-managed virtual environment to appear as a selectable kernel, ensuring that notebooks run with the dependencies specified in the project's `pyproject.toml`.  

  **for Jupyter Notebook:**

  ```bash
  poetry run jupyter notebook
  ```

  **Or for JupyterLab:**

  ```bash
  poetry run jupyter lab
  ```

  **Or for Vscode** 

  When working in a notebook within Visual Studio Code (VSCode), it's important to select the appropriate kernel for your project to ensure that your code runs correctly. Follow these steps to set the kernel to match your Poetry environment:

  1. Open your project notebook in VSCode.
  2. Look at the upper right corner of the notebook view to find the name of the current kernel. It might be set to a default kernel that VSCode has detected.
  3. Click on the current kernel name. A dropdown menu should appear with a list of available kernels.
  4. From the dropdown menu, select the kernel that corresponds to your Poetry environment. The kernel should have the same name as your project, such as "EDPredictiveEfficiency".

  By selecting the correct kernel, you ensure that the notebook is able to access all the dependencies and packages specific to your project's environment.

  

  ## Additional Libraries

  For additional libraries using Poetry and updated the `pyproject.toml` file, you should pull the latest changes from the repository and run `poetry install` again to ensure your environment is up to date:

  ```bash
  git pull
  poetry install
  ```

  By following these steps, you should be able to set up your local environment in a way that mirrors the established configuration , enabling you to run the notebooks as intended. 

  

  # B) Usage Instructions

  After setting up the project environment, you can utilize the provided Jupyter notebooks or Python scripts to run the predictive models.

  ## Running the Predictive Models

  To begin executing the models to predict wait times in the emergency department, follow the steps below:

  ### Accessing the Files

  Make sure you are in the root directory of the cloned project:

  ```bash
  cd /path_where_you_cloned_the_project/EDPredictiveEfficiency
  ```

  ## Option 1: Single notebook option to Run the Model

  For a simplified process, you can run the `waittime_regression_modeling.ipynb` notebook, which is the one-step option to execute the complete WAITTIME prediction model. This is an alternative to the below method multiple notebooks option to run the model.

  ### Steps to Run the Notebook

  1. Navigate to the notebook's directory:
     ```
     cd path_where_you_cloned_the_project/EDPredictiveEfficiency/notebooks/
     ```
  
  2. Open the `waittime_regression_modeling.ipynb` notebook using Jupyter Notebook or JupyterLab or Vscode:
     ```
     jupyter notebook waittime_regression_modeling.ipynb
     ```
     or
     ```
     jupyter lab waittime_regression_modeling.ipynb
     ```
  
  3. Run all cells in the notebook from the top to the bottom to execute the complete prediction workflow.

  Please note that this is the recommended approach if you prefer a one-step process over the multiple-step option.

  

  ## OPTION 2: Multiple notebooks and steps option to Run the Model

  If you prefer the 3 notebooks option, do:

  ### Step 1: Model Selection via Cross-Validation

  Navigate to the following notebook to begin model selection through cross-validation:

  ```plaintext
  /path_where_you_cloned_the_project/EDPredictiveEfficiency/scripts/models_training_and_selection/waittime_regression.ipynb
  ```

  Run all the cells in the notebook to perform the cross-validation process.

  ### Step 2: Model Training with Hyperparameter Tuning

  After selecting the best model, proceed with hyperparameter tuning using the following notebook:

  ```plaintext
  /path_where_you_cloned_the_project/EDPredictiveEfficiency/scripts/models_tuning_and_evaluation/waittime_regression_hyperparameter_tuning.ipynb
  ```

  Please make sure to execute the notebook cells to fine-tune and train the model.

  ### Step 3: Model Evaluation

  Evaluate the trained model's performance using the following evaluation notebook:

  ```plaintext
  /path_where_you_cloned_the_project/EDPredictiveEfficiency/scripts/models_testing/waittime_regression_final_evaluation.ipynb
  ```

  This notebook provides a detailed evaluation of a test dataset, offering insights into the model's accuracy and feature importance.

  

  ## Contributing
  ```plaintext
  Jean Applys Cherizol, Email: jeancherizol@gmail.com, Github: https://github.com/jeancheri
  Junior Zephir,        Email: zephirjunior@gmail.com, Github: https://github.com/junzephir
  ```
  We encourage contributions to the `EDPredictiveEfficiency` project. Your contributions can enhance various aspects of the project, such as predictive models, data preprocessing, and insights into emergency department operations.

  ## License

  This project is licensed under the MIT license. The LICENSE file provides more details on your rights and limitations under this license.
