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
