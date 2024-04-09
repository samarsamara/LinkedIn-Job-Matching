<h1 align="center">LinkedIn Job Matching</h1>
<p align="center">
  Samar Samara, Kinan ibraheem, Rawan Badarneh
  <p align="center">
    Technion
  </p>
</p>

## Overview
When people seeks a job they often search in the jobs in LinkedIn, but we noticed that   when a new position becomes available, employees are often tasked with finding potential candidates who meet the job requirements, So we decided to help people find the job and in the same time help employees to increase their chances of earning bonuses, If a candidate recommended by an employee is hired, the referring employee typically receives a bonus as recognition for their contribution, employees often share job postings on LinkedIn in search of suitable matches so we want to develop AI-driven solutions that analyze these posts to identify potential matches. By automating the matching process, we aim to facilitate smoother and more effective job discovery for both job seekers and matching candidates for jobs. Moreover, in our project one of the significant advantages of the matching process is that the person who finds the job post suitable for him can send his cv to the employee who shared the post who can apply him for the job and this increases his chances to be accepted for the job.

## Install 
Before running this project, you'll need to have Apache Spark installed. Depending on your operating system, the installation steps may vary. Visit the official Apache Spark website to download Spark and find detailed installation instructions for your specific platform.

## How to Run This Project
Welcome to our project! Follow these instructions carefully to get the project up and running on your system.

Prerequisites
Before you begin, ensure you have the following software installed on your computer:

- Python 3.x
- Jupyter Notebook
- pandas
- numpy
- matplotlib
- bs4
- openai
- google.generativeai
  
You can install Python libraries using pip. For example:

```bash
pip install jupyter pandas numpy matplotlib bs4 openai google.generativeai
 ```
Setup
Clone the project repository to your local machine:

 ```bash
git clone https://github.com/samarsamara/LinkedIn-Job-Matching.git
cd LinkedIn-Job-Matching
 ```
## Running the Web Scraping Notebook
Launch Jupyter Notebook:

- Open a terminal in the project directory and run:

 ```bash
jupyter notebook
 ```
This will open Jupyter in your web browser.

- Open the Notebook:

In the Jupyter interface, navigate to **WebScraping_Project.ipynb** and click to open it.

- Execute the Notebook:

Run each cell in the notebook by clicking on it and pressing **Shift + Enter**, or by using the "Run" button in the toolbar. Ensure you execute the cells in the order they appear.

- Save the Results:

Once you reach the end of the notebook, and have the df_answers DataFrame ready, save it to a CSV file by adding and running a new cell with the following code:

 ```python
df_answers.to_csv('df_answers.csv', index=False)
 ```
This command saves the DataFrame to a file named df_answers.csv in the project directory.

## Running the Preprocessing Notebook
- Open the Preprocessing Notebook:

In the Jupyter interface, navigate to **Preproccess_Position_Skills.ipynb** and click to open it.

- Execute the Notebook:

Similar to the previous notebook, run each cell in Preproccess_Position_Skills.ipynb by clicking on it and pressing **Shift + Enter**, or by using the "Run" button in the toolbar. It's important to execute the cells in sequence to ensure the logic flows correctly and dependencies are managed.

- Save the DataFrame to a CSV file: Use the pandas to_csv method to save the temp DataFrame to a CSV file. Add the following line of code at the end of your script or notebook cell:

 ```python
temp.to_csv('temp.csv', index=False)
 ```
This command saves the temp DataFrame to a file named temp.csv in your current working directory. 

### Running the preprocess_users_Skills Notebook

- Open the Notebook: Navigate to the **preprocess_users_Skills.ipynb** notebook in your Jupyter interface and open it.

- Execute the Notebook: Run each cell sequentially by pressing **Shift + Enter**. It's essential to execute the cells in order, as they likely depend on each other for inputs and data processing steps.

- Save the `temp1` DataFrame: At the end of the notebook, you'll generate a DataFrame named `temp1`. This DataFrame contains processed data that will be crucial for subsequent analysis or processing steps. To save `temp1`, add and run the following line of code in the last cell of the notebook:

   ```python
   temp1.to_csv('temp1.csv', index=False)
   ```
### Running the Tagging_positions Notebook

The next step in our project workflow involves tagging positions. This process is handled in the `Tagging_positions` notebook, which includes important steps for data processing and analysis.

- Open the Notebook: Within the Jupyter interface, locate and open the **Tagging_positions.ipynb** notebook. Ensure you've completed previous steps as this notebook may depend on earlier outputs.

- Execute the Notebook: Carefully run each cell in the notebook in the order they appear. You can execute a cell by clicking on it and pressing **Shift + Enter**, or by using the "Run" button in the toolbar.

### Saving DataFrames

Within this notebook, two key DataFrames need to be saved at different points:

- **DataFrame `x` in Cell 12:** After executing up to cell 12, you will have the DataFrame `x` ready. Save this DataFrame by adding and running the following line of code in the next cell:

   ```python
   x.to_csv('x.csv', index=False)
   ```
- **DataFrame `result` in Cell 26:** After executing up to cell 26, you will have the DataFrame `result` ready. Save this DataFrame by adding and running the following line of code in the next cell:
     ```python
   result.to_csv('result.csv', index=False)
     ```

### Running the knn_users_skills Notebook

After tagging positions and preprocessing user skills, the next critical step involves utilizing the K Nearest Neighbors (KNN) algorithm to match user skills with potential job positions. This is accomplished in the `knn_users_skills` notebook.

- Open the Notebook: Locate and open the **knn_users_skills.ipynb** notebook in Jupyter. As with previous notebooks, ensure all previous steps have been completed, as this notebook may rely on their outputs.

- Execute the Notebook: Proceed to run each cell sequentially, ensuring that you execute them in the order they appear by pressing **Shift + Enter** or using the "Run" button in the toolbar.

### Saving the DataSets and Model

In this notebook, you will generate a training dataset, a validation dataset, and a trained KNN model. Here’s how to save them:

- **Save the Training Dataset (`knn_results`) in Cell 18:**
  
  After executing cell 18, save the training dataset `knn_results` with the following code in the next cell:

   ```python
   knn_results.to_csv('knn_results.csv', index=False)

This saves the dataset to knn_results.csv in the current directory, without the row indices.

- **Save the Validation Dataset (val_df) in Cell 19:**

Following the completion of cell 19, save the validation dataset val_df using:

```python
val_df.to_csv('val_df.csv', index=False)
```
This command will save the validation dataset to val_df.csv, also without the row indices.

- **Save the Trained KNN Model:**

To save the trained KNN model for later use, you can use the joblib library. If you haven’t already installed joblib, you can do so using pip:

```bash
pip install joblib
```
Then, add and execute the following line of code after the model training cell:

```python
import joblib
joblib.dump(knn_model, 'knn_model.joblib')
```
Replace knn_model with the actual variable name of your trained model. This will save your model to a file named knn_model.joblib.

### Running the analyzing_posts Notebook
The `analyzing_posts` notebook focuses on applying KMeans clustering to analyze job posts. This step is crucial for understanding the distribution of job types and the categorization of posts based on the defined features.

- Open the Notebook: Find and open the **analyzing_posts.ipynb** notebook within your Jupyter environment. This part of the project builds upon previous steps, so make sure all preceding notebooks have been completed accordingly.

- Execute the Notebook:  Work your way through the notebook, running each cell in sequence up to cell 16. You can run a cell by selecting it and pressing **Shift + Enter**, or by clicking the "Run" button.

### Saving Outputs

This notebook produces a DataFrame and a KMeans model that you need to save:

- **Save the DataFrame (`v`) in Cell 15:**
  
  Once you reach cell 15 and execute it, save the resulting DataFrame `v` by adding the following line in the next cell:

   ```python
   v.to_csv('v.csv', index=False)
   ```
This command saves the DataFrame to a file named v.csv in the current directory, excluding the row indices.

- **Save the KMeans Model in Cell 16:**

After completing cell 16, you will have trained your KMeans model. To save this model for future use, particularly the cluster centers, use the following code:

```python
import joblib
joblib.dump(kmeans, 'kmeans.joblib')
```
Ensure you have joblib installed (pip install joblib), and replace kmeans with the actual variable name of your KMeans model. This saves the model to kmeans.joblib.
