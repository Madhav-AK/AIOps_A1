AI OPs Assignment 1 Submission
- By Madhav AK
- DA24B012

This README file goes through all major submission points.

### Main 1 Pg Report and Video Link:

- Video Recording Link: https://drive.google.com/file/d/1SD-btzyUdqQ9IJSAcP4-Leu92eLS-pLY/view?usp=sharing
- One page pdf summary of my overall process can be found in the main directory of this repo titled AIOps_A1_1pg_report.pdf

### Question 1:

- The theoretical answers to question 1 can be found in the pdf in the q1/ folder of this repo.

### Question 2:

- The answers to question 2 can be found in the pdf in the q2/ folder of this repo.
- The notebook used to generate the results can also be found in the q2/ folder of this repo.

Instructions to Run the Notebook:
- First run the command: mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./mlruns --host 0.0.0.0 --port 5000 --allowed-hosts "*" --cors-allowed-origins "http://localhost:5000, http://127.0.0.1:5000"
- The above launches the mlflow server
- You can now open q2/q2.ipynb and run the cells of the notebook.

### Question 3:

- The Screenshots at the necessary intervals showing the original, modified, and rolled back states can be found in the q3/ folder of this repo.
- The corresponding .dvc files and .dvcignore etc that were created during the process can also be found in the root directory of this repo.
- This is the same repo where the video demonstration is showing, and you may verify the history of this repo.
- The video recording shows me scrolling through the entire terminal history while explaining what I had done.

### Question 4:

- Question 4 needed to be done with a partner.
- Since we cannot share our main repo with our partners, we created a separate repo for this question.
- The separate repo can be found at this link: https://github.com/Madhav-AK/AIOps_A1_Q4
- The video recording shows me scrolling through the entire terminal history while explaining what I had done.

### Some AI Use Declarations:

In order to get the validation loss curves with epochs,
I realized the sklearn MLPClassifier didnt expose an easy function call to just get those data points.

I used an AI to figure out what's the best awy to get that:
And it suggested using model.partial_fit(X_train, y_train, classes=classes)
that allowed me to get epoch wise data and log it accordingly

I also got a bug, which I used an AI to debug:
I needed to add skops_trusted_types=["sklearn.neural_network._stochastic_optimizers.AdamOptimizer"] to mlflow.sklearn.log_model

I also used the AI to assist me in debugging this command:
{ echo "filename"; find data -type f -printf "%f\n" | LC_ALL=C sort; } > q3/data.csv
which is used to get the filenames into data.csv

We could have done the above using an external python script, but i thought it would be easier and more convenient this way.