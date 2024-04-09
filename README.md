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

Open a terminal in the project directory and run:

 ```bash
jupyter notebook
 ```
This will open Jupyter in your web browser.

Open the Notebook:

In the Jupyter interface, navigate to WebScraping_Project.ipynb and click to open it.

Execute the Notebook:

Run each cell in the notebook by clicking on it and pressing Shift + Enter, or by using the "Run" button in the toolbar. Ensure you execute the cells in the order they appear.

Save the Results:

Once you reach the end of the notebook, and have the df_answers DataFrame ready, save it to a CSV file by adding and running a new cell with the following code:

 ```python
df_answers.to_csv('df_answers.csv', index=False)
 ```
This command saves the DataFrame to a file named df_answers.csv in the project directory.

