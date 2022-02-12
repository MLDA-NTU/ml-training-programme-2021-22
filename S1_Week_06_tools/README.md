# Pratical Data Science

## Dev tools

- git: version control, code backup. [git cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)
- GitHub: git hosting and repo manager. [GitHub guides](https://guides.github.com/)
  - Recently GitHub has removed password authentication when using git. You can authenticate with GitHub using [SSH key](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh) (more complicated) or use [GitHub CLI](https://cli.github.com/) (easier)
  - Otherwise, you can use a GUI git client, like [GitHub Desktop](https://desktop.github.com/), [GitKraken](https://www.gitkraken.com/). Your editor may have built-in git support also, like [VS Code](https://code.visualstudio.com/docs/editor/github)
- conda: package manager and virtual environment manager
  - Generally conda resolves dependency issues better than pip. Also, conda can install non-python packages, like CUDA toolkit. This is very convenient when different deep learning libraries (TensorFlow or PyTorch) may require a specific version of CUDA

Topics covered

- Create a GitHub repo. Push code to and pull code from GitHub
  - **VERY USEFUL**: `git status`
  - Push: `git add your_file.py`, `git commit -m "Your message"`, `git push`
  - Pull: `git fetch`, `git pull`
  - Other git concepts good to know: branch, remote, rebase, fork, pull request, resolve conflict
- Collaborating with GitHub. [Git Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows). 3 main workflows
  - Everyone work on `main` branch directly
  - Each person works on a separate feature branch. `main` branch should always work
  - Each person fork the repo, and create a pull request (PR) to merge back to the main repo
- Set up virtual environment using conda. Install packages
  - Create a new virtual environment: `conda create -n data-science python=3.8`
  - Activate, deactivate, and list environment: `conda activate`, `conda deactivate`, `conda env list`
  - Install packages: `conda install numpy`, `pip install opencv-python`
  - Manage dependencies: `conda list`, `conda env export -f environment.yaml`, `conda env create -f environment.yaml`

Editors for Data Science and Machine Learning

- Jupyter (Notebook or Lab) (free)
- VS Code (free, **recommended**)
- PyCharm (free for student)

## Mini Data Science project on Wine dataset

Some interesting ideas for a Data Science project: [UpLevel](https://dataprojects.uplevel.work/store)

Dataset: [Wine Quality](https://archive.ics.uci.edu/ml/datasets/Wine+Quality)

Notebook: [wine quality](wine_quality.ipynb)

General steps in a Data Science project

1. Download and import the data
2. Inspect the data
    - Are there missing entries? Are there obviously wrong data? e.g. age = 1000. Are they critical?
    - Are the data types correctly interpreted? e.g. if there are "NA" values in a numerical column, `pandas` will interpret the whole column as string
    - How many columns (number of features) and rows (number of samples) are there? Is it sufficient for building an ML model?
3. Data cleaning
    - Remove missing data: you can remove rows (samples) or columns (features). If a feature has too many missing values, we can drop that column. Similarly for row
    - Transform or clean the data if needed. This is dependent on your data. e.g. remove stop words in NLP, remove outliers
    - Instead of removing missing data, you can fill values to them instead. The method is specific to the data e.g. fill missing values with mean of the column
4. Exploratory Data Analysis (EDA)
    - Use appropriate data visualization tools to study the distributions of each feature, and the relationships among the features.
    - Observe the trends and optionally transform the data e.g. you see exponential relationship, so you take logarithm of that feature
    - We can drop the features with weak correlation with the target variable. However, in small datasets, we can just keep them for now 
5. Preparing data for building ML model
    - Normalize the data. Two popular methods are Standard normalization (normalize to Normal distribution `N(0,1)`) and Min-max normalization (normalize to range `[0,1]`)
    - Train-test split: either 2-way split (train-test or train-validation) or 3-way split (train-validation-test)
    - (Optional): write or serialize data to disk, so that you don't need to run preprocessing code again during training. Only needed when the dataset is huge
6. Building ML model
    - Select a baseline model to train and evaluate its performance. It should be a simple model that you can train and evaluate using it quickly e.g. linear regression, logistic regression
    - Identify potential models for your task e.g. for classifications, we can use logistic regression, support vector machine, or random forest
    - Train the model on the train set
    - Evaluate model's performance on the test/validation set. NOTE: for specialized tasks, you may want to define your own evaluation metrics BEFORE you start building your model
    - Tune model's hyperparameters **on the validation set**. Most models have extra parameters that you can tune, such as regularization factor. Three common methods for hyperparameters tuning: grid search, random search, and Bayesian optimization. Read more [here](https://neptune.ai/blog/hyperparameter-tuning-in-python-a-complete-guide-2020)
    - NOTE: if you tune too much, you might overfit the validation set
7. (Optional) Explore and explain the model
    - Each model will have a specific way to interpret how the model makes prediction e.g. in linear regression, if a particular weight is large, it means that the feature corresponding to that weight is important in making predictions (NOTE: your data must be normalized first)
    - Check the bad predictions. Try to identify why those samples have bad predictions e.g. maybe those are outlier examples? noisy data? Think of how you can overcom this
