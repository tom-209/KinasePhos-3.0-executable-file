This project contains the code to implement KinasePhos 3.0, if you use any of this code, please cite:

"Ma, Renfei, Shangfu Li, Wenshuo Li, Lantian Yao, Hsien-Da Huang, and Tzong-Yi Lee. "KinasePhos 3.0: Redesign and Expansion of the Prediction on Kinase-specific Phosphorylation Sites." bioRxiv (2021)."

************************************ Folders ******************************************
*********
./data:
  1.Family K-S sites: Original data of experimentally verified kinase-specific phosphorylation sites at family level
  2.Family positive: Experimentally verified kinase-specific phosphorylation sites extracted from 1. 
  3.Family negative: All the same types of residues in phosphorylated substrate proteins of a family, except those known to be positive phosphorylation sites, were regarded as negative data of that kinase family.
  .
  .
  .
 The same goes with the data at individual kinase level and group level.

 !!!It should be noted that CD-HIT and CD-HIT-2D were adopted to reduce data similarity.

*********
./features:
 This folder contains the features of positive and negative data encoded with BLOSUM62, the data were clustered at group, family, and individual kinase level.
 For family and individual kinase level, S/T/Y, S/T and Y sites were considered separately.

********* 
./pretrained XGBoost models
 This folder contains the pretrained XGBoost models of KinasePhos 3.0

*********
./results
 This folder contains the performance of all models resulting from using 10-fold cross-validation


************************************ Files ******************************************
~~~~~~~~~
./1_data preprocessing.ipynb
  This file precesses the original data in the "./data" folder, gets the positive and negative data, and saves them in "./data"

~~~~~~~~~
./2_feature extraction_BLOSUM62.ipynb
  This file encodes the positive and negative data in "./data" and saves the encoded features to "./features"
  !!!It is recommended for users to implement CD-HIT-2D and/or CD-HIT to reduce data similarity, otherwise the size of negative data is too large
~~~~~~~~~
./3_models.ipynb
  This file develops the machine learning-based models of KinasePhos 3.0

~~~~~~~~~
"./family 15.npy":     list of kinase families with experimentally verified kinase-specific phosphorylation S/T/Y sites more than 15
"./family_st 15.npy":  list of kinase families with experimentally verified kinase-specific phosphorylation S/T sites more than 15
"./family_y 15.npy":  list of kinase families with experimentally verified kinase-specific phosphorylation Y sites more than 15
"./kinase 15.npy":     list of kinases with experimentally verified kinase-specific phosphorylation S/T/Y sites more than 15
"./kinase_st 15.npy":  list of kinases with experimentally verified kinase-specific phosphorylation S/T sites more than 15
"./kinase_y 15.npy":  list of kinases with experimentally verified kinase-specific phosphorylation Y sites more than 15


************************************ Zip file ******************************************
./KinasePhosApp.zip
  This is the standalone tool of KinasePhos3.0, which is supported by Windows.