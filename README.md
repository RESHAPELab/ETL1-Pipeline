# ETL1-Pipeline

The ETL1 pipeline reads the commit data and process it to populate the database with information about the source code updated by PRs

The first inout is the commit file created by the extractor. Below is an example of the format required. Not all columns are needed. However, to future expansions (like the predictions of the Author skills) new column data should be included into the processing pipeline.

The merged-commit-commits (3).csv (58MB) file can be downloaded at:

https://drive.google.com/file/d/133Va716hRhQtLHlS_BojcnzDAG-UAGBa/view?usp=sharing

The file to be read whould be updated in the second cell as the example below:
inputToRead = "/home/j/git/ETL1-Pipeline/data/inputs/new/rxjava_full/rxjava_full_commit_output.csv"

Research2.ipynb is on charge of splitting the file names commited by PRs into their own columns for further processing and populate the PR table.

The notebook writes three outputs:
fileNameOutput = "/home/j/git/ETL1-Pipeline/data/outputs/new/rxjava/dataframe_file_names.csv"

filesPR3_TXT_Output = r"/home/j/git/ETL1-Pipeline/data/outputs/new/rxjava/filesPR3BodyTitle2.txt"

filesPR3_CSV_Output = "/home/j/git/ETL1-Pipeline/data/outputs/new/rxjava/filesPR3BodyTitle2.csv"

The filesPR3_TXT_Output is used in the next step.

The figure file OSL_pipeline-inputs.png shows the entire pipeline (ETL1 and ETL2). Observe the input for the Research2.ipynb in the figure is another file produced by the Classifier.R. This step is not necessary anymore. Next version of the picture will remove it.

![OSL_pipeline-inputs](https://user-images.githubusercontent.com/34105280/212744629-529b7dc9-6a4e-4869-a7e5-2c2b51affdc8.png)
