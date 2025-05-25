# ML-CHEM-prediction
Molecular Feature Analysis using Random Forests

Description: This project aims to investigate the transformative role of machine learning (ML) in the field of chemistry, with a particular focus on its ability to predict molecular properties using alternative input features—typically obtained through experimental methods or quantum chemical calculations. The study will explore how effectively machine learning models can approximate or even replace traditional computational approaches in property prediction. Furthermore, the project seeks to examine whether these models can empirically uncover and quantify the underlying physical laws, such as the first law of thermodynamics, through ML.
I will use a large existing chemical database from Ramakrishnan et al. paper (doi: 10.1038/sdata.2014.22) to train my machine learning algorithms. This database consists of 133k molecules, ranging from the smallest like water to big hydrocarbons and heterocycles. Each entry is represented in .xyz file format (typical for chemical software) which includes the computational data, including but not limited to the number of atoms, types of atoms, their relative positions in cartesian coordinates (input features), as well total internal energy, constant-volume heat capacity (targets) etc.
For my project, I plan to mainly rely on decision-tree based models (i.e. Decision Tree, Random Forest, Bagging Ensemble of Random Forests) with 20% of the training set and 80% of the testing set based on the existing chemical literature on machine learning applications in chemistry. To improve the accuracy score of all models, each run will be cross validated before finally being tested on the real testing set with best hyperparameters. Due the large size of the database, all models will be only trained on a small portion of it and put on the Amherst College FrostByte server to facilitate computations. To better quantify the relationships observed in the dataset, Symbolic Regression will be also employed in conjunction with the above-mentioned models.

The main results will be reported primarily as models’ accuracies (i.e. mean squared error and R2 of training and testing sets), as well as plots of feature importances regarding a specific target. A low error and high R2 would serve as an indicator of a strong and distinct relationship between features and a target. In contrast, a high error and low R2 will be interpreted as a lack of a clear correlation between variables. The same metrics for a training and a testing set will inform us whether the model is underfitted (high bias) or overfitted (high variance) which will help us to regularize a model’s performance. “Feature Importance” plots will be compared to the known relationships in physical chemistry. In some cases, we will observe that the ML model empirically derives a known relationship, demonstrating the highest importance of only a few features and yielding a high accuracy. On the other hand, in other cases, we will see no clear correlation with specific variables, indicating the importance of excessively many features with significantly lower accuracy.

In addition to the main analysis just mentioned, I implemented other dataset characterization techniques, including PCA, heatmaps, and pair plots, to further confirm/refute models’ accuracies.





Status:

Done: The project is done. The work included:
•	obtaining the dataset from the above-mentioned paper
•	preprocessing the dataset according to the .xyz files guidelines as well as splitting it into training and testing sets
•	finding the best model configuration using GridSearch in conjunction with cross validation (cv=5)
•	fitting the obtained model and analyzing using regression metrics (i.e. MSE and R2)
•	plotting the “Feature Importance” plot and comparing it with the known chemistry relationships
•	Testing ensembles of Random Forests as well as Decision Trees to see if there is any improvement in accuracy.
•	Using Symbolic Regression to determine an empirical numeric formula for chemical relationships.
•	Using PCA, pair plots, and heatmaps to describe the dataset.
All the computations were run on FrostByte to reduce program runtime.

Results and Discussion: 

All the results of this project are described in the Jupyter Notebook. In general, though, the project was fully accomplished and was proven to be successful. Indeed, the decision-tree-based models performed particularly well for molecular predictions; in fact, so well, that they were able to determine some laws of physical chemistry (or more specifically their variables) and achieve a high accuracy in predicting numerous features. Surely, these models won’t substitute the quantum chemical computation; however, they have a potential to serve as a general framework one could use to get an approximate answer fast. 

Conclusions: 
This project successfully demonstrated the potential of machine learning, particularly decision-tree-based models, to predict molecular properties using structural data derived from chemical .xyz files. By leveraging a large and diverse chemical dataset, models such as Decision Trees, Random Forests, and ensembles were trained and validated to approximate quantum chemical computations with high accuracy. The use of symbolic regression further highlighted the ability of these models to capture known physical relationships, such as the first law of thermodynamics.
While traditional quantum methods remain more precise, this study underscores the utility of ML models as powerful tools for preliminary analysis. Additionally, the incorporation of PCA, heatmaps, and pair plots offered valuable insights into the dataset's structure, further reinforcing the validity of the results. Overall, the outcomes affirm that machine learning can act as a complementary approach in chemical research, potentially guiding future discoveries in the field.

Suggestions:
1.	Use other supervised models (or deep neural networks) for further investigation of chemical systems. 
2.	Expand the database to more compounds with different elements and functional groups for better generalization and broader scope of model fitting.
3.	Use other metrics for models’ evaluations.
   
Related Work:
•	https://www.nature.com/articles/sdata201422 (original paper with the dataset)
•	https://www-sciencedirect-com.amherst.idm.oclc.org/science/article/pii/S2666352X22000218
•	https://pubs.acs.org/doi/10.1021/ci034160g
•	https://www.nature.com/articles/s41598-021-93070-6
 


Figures:
 
Figure 1. Feature Correlation Map
 
 
Figure 2. Feature importances of the whole dataset using Random Forest
 
 
 
Figure 3. Feature importances of the whole dataset using Decision Tree
 
 
Figure 4. Feature importance of the reduced dataset using Random Forest
 

 
 

Figure 5. Feature importance of the reduced dataset using Decision Tree

Figure 6. PCA of Cv298 for the whole and reduced dataset.
 
Figure 7. Pair plots of seven most important features in the whole dataset.
 
