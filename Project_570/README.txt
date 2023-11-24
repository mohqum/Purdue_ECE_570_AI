Which code files have been copied from other repositories with references to these repositories:
	The code was cloned from the repository 
	https://github.com/DeepGraphLearning/ContinuousGNN.git
        ContinuousGNN_master folder is the author's code.

	The code base or the changes I made or experimented is stored under my git repository
	https://github.com/mohqum/ContinuousGNN.git
	I have also added my project work implementation in ContinuousGNN_570 folder apart from the github repo link for easy access.

Explain how to run the experiments:
	Additionally I have provided with the ipnyb note book too. You just need to run all the cells for my reproduced work. The html file is the output of the implemented code whereas the ipnyb is the notebook 	where you can download and re run all the cells. The output may have a variation of +1 	or -1 percent accuracy.

Which code files have been modified and how they have been modified:
	If you cd into the ContinuosGNN folder and again into the src folder I have made a few 	reimplementation changes in below files:

	gnn.py:
		I have define my own GNN model class (Custom_GNN). There I have added two GCN layers instead of linear layers as self.conv1 and self.conv2. Also added a few more changes.

		Similarly I define my own Custom ODEFunc class (Custom_ODEFunc) where I use leaky relu instead of sigmoid based on trial and error for better accuracy.

	wgnn.py:

 		I have define my own WGNN model class (Custom_WGNN). There I have added two GCN layers 	instead of linear layers as self.conv1 and self.conv2 and also a third layer which is a linear 			layer as self.linear_layer for weight Initialization done in trainer.py. Also changed the reset function and made a few other changes.

	trainer.py:

		In class Trainer I have defined a new function called weight_initialize() where a weight Initialization is done for linear layers. There is one linear layer defined in wgcnn as it has 		weights. 
		cgnn does not undergo weight initialization as it does not have any weights. 

		In update function in the Trainer class, I made a feew channges by adding L1 regularizaton and L2 regularization and added a new loss formulae adding both the l1 and l2 regularization.

		Similarly in updatew function in the Trainer class, I made a feew channges by adding L1 regularizaton and L2 regularization and added a new loss formulae adding both the l1 and l2 			regularization.

	train.py:
		I added a new argument called decay_l1 in the main function which acts as a new hyperparameter in the dictionary dict(). This hyperparameter is used for L1 regularization.

	run_cora_cgnn.py:
		I added a new hyperparameter decay_l1.

	run_cora_wcgnn:
		Added decay_l1 hyperparameter, changed the hidden_dim from 16 to 40, reduced the alpha 	from 0.97 to 0.6 based on trial and error for better accuracy.

Include a description of the datasets you used and where you obtained them:
	The dataset is contained in ContinuosGNN_570 folder in the data folder. The dataset used is the author's original dataset which is the CORA dataset. I have removed the dataset in the ContinuousGNN 	folder 	but when you run the code on google colab it takes the repo from my github and so the dataset is contained in the online repository not in this folder. You can access the dataset from 	my github repo 	link given above.

