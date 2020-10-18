## Single-step Retrosynthesis Prediction based on the Identification of Potential Disconnection Sites using Molecular Substructure Fingerprints
A novel, template-free approach for the one-step retrosynthesis task described in a journal paper which is 
currently under review. Depending on the journal decision, the link will be posted here.

### Running the Code
This repository is still under construction, but it requires just a few more updates and it will be fully finished.
The main functionalities are now available to be ran as scripts, which is described later in the document.
There is still a high possibility of encountering bugs.  

#### Installation
The necessary Python environment can be set-up using ```conda``` by simply running:

```shell script
conda env create -f environment.yml
```
```shell script
conda activate one_step_retrosynth_ai
```

If you encounter errors or conflicts for whatever reason, you can manually re-construct the environment.
The following base libraries were used for the realization of the project:

* python: 3.6.10
* tensorflow-gpu: 1.12.0
* rdkit: 2018.03.3.0
* numpy: 1.16.0 (NOTE: This version is preferred to avoid annoying TF warnings.)
* pandas: 1.1.3

Additional libraries that are necessary for the code to be fully functional are:

* tqdm: 4.50.2
* scikit-learn: 0.23.2
* imbalanced-learn: 0.7.0
* matplotlib: 3.3.1
* cairosvg: 2.4.2

Everything else will be installed automatically as requirements for the base libraries.

#### Configuration
The general configuration of each step is stored in the ```config.json``` file.
It specifies all of the necessary dataset, descriptor and model configurations.

#### 1. Dataset Preparation
The dataset can be generated by running the following command:

```shell script
python -m scripts.prepare_dataset config.json
```
The process consists out of 5 steps and the final dataset is saved in the folder specified in the configuration. 

#### 2. Model Training
The specified model can be trained and assessed by running the following command:

```shell script
python -m scripts.train_model config.json
```
All of the hyper-parameters are specified in the configuration. 

#### 3. Full Pipeline Application
_NOTE: Still under construction. Requires additional parameter updates and cosmetics._
The full single-step retrosynthesis pipeline can be assessed by running the following command:

```shell script
python -m scripts.run_evaluation config.json
```
All of the hyper-parameters are specified in the configuration.

### Contact
For any questions and inquiries please feel free to [contact](mailto:hasic@cb.cs.titech.ac.jp) the authors.
