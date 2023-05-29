Ki Kwong Arthur Poon Applied Data Analysis Final Project Repository

Directory Structure:

1) README.md
This README.md file

2) Ki Kwong Arthur Poon_ADA Final Project.pdf: PDF of report

3) Ki_Kwong_Arthur_Poon_bert_num_shape.ipynb: Google Colab Notebook (Colab does not have line count, so I do not have lines of count for my produced file) <https://colab.research.google.com/drive/1T94gu2-PhPRnNLSm7tiTxDvRNRc0fHZy?usp=sharing>. The colab notebook runtime was not saved down because I was using my personal g-suite account because I had bought compute units to accelerate the computation. Thus, in order for it to be shareable with uchicago credentials by default, I hosted the file on my uchicago g-suite account which does not contain my results output run using the accelerated resources.

4) Cloned directory from Loukas et al. **NOTE THIS CODE WAS NOT WRITTEN BY ME, BUT BY LOUKAS et al.
/finer-main/finer-main

README for this directory can be found within
finer-main/finer-main/README.md

Modifications relative to original repository:

finer.py: 
- modified lines 282:289 to include structure to randomly deploy shape or numeric tokens when replacing numeric values
- added lines 455 and 465 to decrease the training and validation sets to expedite training time of program

requirements.txt:
- there was a typo in the “tensorflow-addons==1.16.1” package, modified this to “tensorflow-addons==0.16.1”

Cloned directory structure:

/configurations/ 
- contains json files and python scripts for configuring models that are to be trained when the script “/models/run_experiment.py” is run

	__init__.py: 3 lines, for initiaing specific configurations when run_experiment.py is run
	bilstm.json: 35 lines, json file containing configurations for bilstm models to be used
	configuration.py: 132 lines, python script to apply configurations during run_experiment.py
	transformer.json: 33 lines, contains configurations for BERT models
	transformer_bilstm.json: 35 lines, contains configurations for BERT BILSTM models used in Loukas et al.
	
/data/
- contains “shape_special_tokens.txt”, which contains the special tokens to replace in the FiNER dataset

	__inity__.py: 4 lines, for loading data modificaitons when run_experiment.py is run
	shape_special_tokens.txt: 214 lines, contains the special tokens to replace numeric values with when we want to only have shape.

/models/
- contains the scripts to run the variety of models use in the Loukas et al paper. These contain the BILSTM model, transformer model (which is the BERT model). I use this in my solution.

	__inity__.py:  3 lines, loads models for execution during run_experiment.py
	bilstm.py: 135 lines, script containing the BILSTM model
	callbacks.py: 148 lines, script containing callbacks model
	transformer.py: 142 lines, script containing BERT model
	transofmer_bilstm.py: 165 lines, script containing BERT BILSTM model

LICENSE
- license to utilize the repository

README.md
- README about the original directory

finer.py 
- 757 lines, python script to control how FiNER dataset is modified / tokenized based on the configurations in the /configurations/ directory

requirements.txt
- 14 lines, text file containing all the required packages for running the scripts in the finer repository

run_experiment.py
- 60 lines, python script for training models and calculating result statistics and controls the storage of results
