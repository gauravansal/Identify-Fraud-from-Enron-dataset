### Identify Fraud from Enron dataset

#### Project Overview
In 2000, Enron was one of the largest companies in the United States. By 2002, it had collapsed into bankruptcy due to widespread corporate fraud. In the resulting Federal investigation, a significant amount of typically confidential information entered into the public record, including tens of thousands of emails and detailed financial data for top executives. In this project, you will play detective, and put your new skills to use by building a person of interest identifier based on financial and email data made public as a result of the Enron scandal. To assist you in your detective work, we've combined this data with a hand-generated list of persons of interest in the fraud case, which means individuals who were indicted, reached a settlement or plea deal with the government, or testified in exchange for prosecution immunity.

#### Resources Needed
You should have python and sklearn running on your computer, as well as the starter code (both python scripts and the Enron dataset) that you downloaded as part of the first mini-project in the Intro to Machine Learning course. You can get the starter code on git: 
git clone https://github.com/udacity/ud120-projects.git

The starter code can be found in the final_project directory of the codebase that you downloaded for use with the mini-projects. Some relevant files: 

**poi_id.py** : Starter code for the POI identifier, you will write your analysis here. You will also submit a version of this file for your evaluator to verify your algorithm and results. 

**final_project_dataset.pkl** : The dataset for the project, more details below. 

**tester.py** : When you turn in your analysis for evaluation by Udacity, you will submit the algorithm, dataset and list of features that you use (these are created automatically in poi_id.py). The evaluator will then use this code to test your result, to make sure we see performance that’s similar to what you report. You don’t need to do anything with this code, but we provide it for transparency and for your reference. 

**emails_by_address** : this directory contains many text files, each of which contains all the messages to or from a particular email address. It is for your reference, if you want to create more advanced features based on the details of the emails dataset. You do not need to process the e-mail corpus in order to complete the project.

#### Steps to Success
We will provide you with starter code that reads in the data, takes your features of choice, then puts them into a numpy array, which is the input form that most sklearn functions assume. Your job is to engineer the features, pick and tune an algorithm, and to test and evaluate your identifier. Several of the mini-projects were designed with this final project in mind, so be on the lookout for ways to use the work you’ve already done.

As preprocessing to this project, we've combined the Enron email and financial data into a dictionary, where each key-value pair in the dictionary corresponds to one person. The dictionary key is the person's name, and the value is another dictionary, which contains the names of all the features and their values for that person. The features in the data fall into three major types, namely financial features, email features and POI labels.

**financial features**: ['salary', 'deferral_payments', 'total_payments', 'loan_advances', 'bonus', 'restricted_stock_deferred', 'deferred_income', 'total_stock_value', 'expenses', 'exercised_stock_options', 'other', 'long_term_incentive', 'restricted_stock', 'director_fees'] (all units are in US dollars)

**email features**: ['to_messages', 'email_address', 'from_poi_to_this_person', 'from_messages', 'from_this_person_to_poi', 'shared_receipt_with_poi'] (units are generally number of emails messages; notable exception is ‘email_address’, which is a text string)

**POI label**: [‘poi’] (boolean, represented as integer)

You are encouraged to make, transform or rescale new features from the starter features. If you do this, you should store the new feature to my_dataset, and if you use the new feature in the final algorithm, you should also add the feature name to my_feature_list, so your evaluator can access it during testing. For a concrete example of a new feature that you could add to the dataset, refer to the lesson on Feature Selection.

n addition, we advise that you keep notes as you work through the project. As part of your project submission, you will compose answers to a [series of questions](https://docs.google.com/document/d/1NDgi1PrNJP7WTbfSUuRUnz8yzs5nGVTSzpO7oeNTEWA/pub?embedded=true) to understand your approach towards different aspects of the analysis. Your thought process is, in many ways, more important than your final project and we will by trying to probe your thought process in these questions.

#### Items to include in submission:

- **Code/Classifier** - When making your classifier, you will create three pickle files (my_dataset.pkl, my_classifier.pkl, my_feature_list.pkl). The project evaluator will test these using the tester.py script. You are encouraged to use this script before submitting to gauge if your performance is good enough. You should also include your modified poi_id.py file in case of any issues with running your code or to verify what is reported in your question responses (see next paragraph). Notably, we should be able to run poi_id.py to generate the three pickle files that reflect your final algorithm, without needing to modify the script in any way. If you have intermediate code that you would like to provide as supplemental materials, it is encouraged for you to save them in files separate from poi_id.py. If you do so, be sure to provide a readme file that explains what each file is for. If you used a Jupyter notebook to work on the project, make sure that your finished code is transferred to the poi_id.py script to generate your final work.

- **Documentation of Your Work** - Document the work you've done by answering (in about one or two paragraphs each) the questions found here. You can write your answers in a PDF, text/markdown file, HTML, or similar format. The responses in your documentation should allow a reviewer to understand and follow the steps you took in your project and to verify your understanding of the methods you have performed.

#### Note -
1. Please use IPython shell to run the poi_id.py script instead of ordinary shell 'python'
2. I have used jupyter notebook for my analysis. Please follow through the jupyter notebook and its html file to better understand the flow and thoughts behind the analysis.
3. poi_id.py has been generated from jupyter notebook. poi_id.py script may take upto 5-7 min. to complete.
4. Please keep the jupyter notebook as well as poi_id.py script in the location as tester.py file.
5. If Github viewer fails to load .ipynb file, please follow the link at Jupyter Notebook viewer for the complete analysis - https://nbviewer.jupyter.org/github/gauravansal/Identify-Fraud-from-Enron-dataset/blob/master/Identify%20Fraud%20from%20Enron%20Email.ipynb

#### Additional  Note - 
Checkout this link for [Class Imbalance Problem](http://www.chioka.in/class-imbalance-problem/).
