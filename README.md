# Guide to running sequence-structure-function pipeline

- Collection of jupyter notebook scripts demonstrating various aspects of pipeline.
- Conda enviornments required to run pipeline and jupyter notebooks are located in conda_yml.
    - alphafold2.yml for Step 2
    - seq_struct_func.yml for steps 1 and 3-6 
        - step 4 requires pyCHARMM to be installed (https://academiccharmm.org/documentation/latest/pycharmm)
- Recommended to use 1 GPU and 4-8 CPUs for examples.
- Scripts are listed in the order they should be run.

### Data: (si_data/)     Data necessary for running examples 
- asr_seq_annotations.xlsx
    - All enzymes, sequences, and annotations from structure-function pipeline
- extant_msa.fasta
    - Multiple sequence alignment used previously to construct ancestral sequence resurrects
- fasta/
    - Sequences in asr_seq_annotations.xlsx written as fasta format
- pdb_with_fad/
    - Directory containing all AlphaFold2 models with FAD cofactor
- top_dock_pose/
    - Directory cotaining lowest energy poses from minimization in explicit protein
- log_reg_models/
    - Pretrained statsmodels logistic regression models 

### Toppar: (toppar/)   CHARMM Topology and Parameter files 

### Step 1: (consensus/) Generating consensus sequence hits library
- gen_consensus_db.ipynb 

### Step 2: (model/)     Generating AlphaFold2 Structures
- run_alphafold_consensus.ipynb 

### Step 3: (cofactor/)  Adding FAD Cofactor
- fad.ipynb

### Step 4: (dock/)      Docking Array of Ligands
- fftdock.ipynb
- prot_min.ipynb
- cluster.ipynb

### Step 5: (pred/)      Prediction of Stereochemistry and Reactivity
- stereo.ipynb
- reactivity.ipynb
- vis_pred.ipynb

### Step 6: (seq_func/)   Training Sequence-Function Model and SHAP Analysis
- run_automl.ipynb
- shap_analysis.ipynb

