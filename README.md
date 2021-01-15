# A Data Exploration of the Package Ecosystem NPM

The following project contains the essay and the analysis made of data related to NPM. 

It is made public for the sake of the reproducibility of the study that was based on the findings made here.

## Tools

- this jupyter notebook with the imports mentioned in the first code cell
- the Bash cli for cutting data
- data downloaded from https://libraries.io/data
- a Google Cloud Bucket
- a Google Cloud VM

## Instructions 

### 1. Download the data
The csv-formatted data comes from https://libraries.io/data, choose the file **libraries-1.6.0-2020-01-12.tar.gz**
Upon download of this 24GB file, decompress from googlezip and tar so that you have a filestructure containing 7 datasets. For this study, only **projects_with_repository_fields-1.6.0-2020-01-12.csv** is used.

### 2. Cut NPM data using Bash
Open bash, or zsh etc. 
cd to the containing folder and run the following scripts to obtain the NPM projects data.

<code>awk -F, '$2 ~ /NPM/' projects_with_repository_fields-1.6.0-2020-01-12.csv > ~/npm_projects.csv</code>

<code>head -n 1 projects_with_repository_fields-1.6.0-2020-01-12.csv > ~/head.csv</code>

<code>cat head.csv npm_projects.csv > only_npm_projects_w_header.csv</code>

### 3. Read the data
To read the data I uploaded it in a Google Cloud Bucket, this can be done via tutorials online, or if my bucket is still active, you can access it there. Alternatively, you can run this project locally on your computer either by taking a sample of the csv with bash or in full by running a few columns at a time if there is a lack of memory. To do this, simply  comment out the line: fs... and with fs... and remove indentations in the code cell following the imports.

### 4. Run the Notebook
Download the notebook from this project and install all dependencies, you should then be able to run the code cells below.
