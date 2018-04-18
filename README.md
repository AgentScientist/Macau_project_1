# Linking drug target and pathway activation for effective therapy using multi-task learning

## Introduction to Macau

Macau installation: https://github.com/jaak-s/macau

Macau tutorial can be found here: http://macau.readthedocs.io/en/latest/source/examples.html#

Macau pharmacogenomics paper: https://www.biorxiv.org/content/early/2018/01/27/225573

Macau technical overview paper: http://ieeexplore.ieee.org/document/8168143/

Macau technical paper (extended):  https://arxiv.org/pdf/1509.04610.pdf

To understand more about MCMC Sampling: http://twiecki.github.io/blog/2015/11/10/mcmc-sampling/

![Alt text](https://github.com/Katan5555/Macau_project_1/blob/master/image/Figure_1.png)

## Drug response prediction in 4 different settings: 

Setting 1: **macau_GDSC.py**

Setting 2: **macau_GDSC_pred_new_drug.py**

Setting 3: **macau_GDSC_transduction.py**

Setting 4: **macau_GDSC_pred_new_drug_new_cell.py**

You may need a certain environment to submit your job (depending on the cluster): **cluster_script_GDSC.sh**

## Divide the data into 16 different tissues 

Use **prepare_data_cancer_type.R** to divide the data contained in the DATA folder into 16 subfolders for each tissue type. 


## Generate the interaction matrix: 

Step 1: use **macau_GDSC_pred_new_drug_new_cell.py** (for one tissue) or **macau_GDSC_interaction_tissue_QC.py** (for all tissues) to check the quality of the features. Make sure the performance is greater than 0.3.

Step 2: Generate the interaction matrix using **macau_GDSC_interaction_transduction.py** (for one tissue) or **macau_GDSC_interaction_tissue.py** (for all tissues)

Step 3: use **macau_GDSC_interaction_tissue_PERMUTATION.py** to do random permutation of the cell lines side features. This gives p-value for each data point of the interaction matrix.

## Plot the results:

Analyse the drug response prediction result: **Drug_response_analysis.Rmd**

Analysis feature interaction result: **GDSC_interaction_analysis_Tissue.Rmd**

Scatter plot of the result using: **Scatter_plots.Rmd**

## Simply download the results:

In folder **target_progeny11**: interaction matrices for 16 GDSC tissues. Since drug target is binary, make sure to ONLY CONSIDER proteins targeted by at least 2 differents drugs. 

In folder **target_progeny11_PERMUTATION**: one file about the counts generated by the permutation in order to compute the p-value ; one file for the p-value matrix ; one file for the BHY corrected p-value. 

## License

Distributed under the GNU GPLv3 License. See accompanying file LICENSE.txt or copy at http://www.gnu.org/licenses/gpl-3.0.html.


