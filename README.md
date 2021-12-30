
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



# KinasePhos-3.0-executable-file

KinasePhos3.exe is a downloadable prediction tool of KinasePhos 3.0

Example Input.txt is an example input file that can be used in the KinasePhos3.exe

Tutorial:
1. Click the KinasePhos3.exe

2. After it is opened, click the Browse button to upload the user's own data file; it 
   should be a text file with fasta format. Under the "Input file name:", user can see
   the file path and name just uploaded. In the box below, it shows the content of the 
   file.

3. User can tick check boxes of interest.
   There are three types of models in this tool, i.e., models at kinase group level, 
   models at kinase family level, models at individual kinase level.

   3.1 If "Kinase groups" is checked, all models at the kinase group level will be executed. 
       Users can also check group model separately by ticking "AGC", "Atypical", "CAMK", "CK1",
      "CMGC", "Other", "PKL", "STE", "TK" and "TKL" checkbox.

   3.2 If "Kinase families" is checked, all models at the kinase family level will be executed.
       Users can also check kinase family models separately if required. These family models are
       grouped into 10 scroll areas, corresponding to the 10 kinase groups.

   3.3 If "Kinases" is checked, all models at the individual kinase level will be executed. 
       Users can also check individual kinase models separately if required. The kinase models are
       separated as humans and other organisms, with both types grouped into 10 scroll areas, 
       corresponding to the 10 kinase groups.

4. After model checkboxes are checked, the user can click "Run and save"
   After clicking, the models are running. It may take some time if users selected many models and 
   their data are large. After all models are executed, it will props up a window that allows the 
   user to specify the address and file names to save results, which will be store as a csv file, 
   with the format as demonstrated below.

Example results
"""

Input_ID	Position	Code	Peptide		Kinase	Source	Probability

Q6GZX3		2		S	******MSIIGATRL	AGC	Pred.	1

Q6GZX3		7		T	*MSIIGATRLQNDKS	AGC	Pred.	0.945

Q6GZX3		14		S	TRLQNDKSDTYSAGP	AGC	Pred.	0.996

.
.
.

"""
