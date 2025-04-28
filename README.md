# AdaptyvBio EGFR Binder Competition Round 2 Neutralisation Analysis

This repo contains the follow-up analysis of the neutralisation data from the Round 2 AdaptyvBio EGFR Binder Design Competition

## Data Sources & Description:
`data/extract_predictions`
1. `Human_EGF.pdb`: This prediction pdb is obtained by running colabfold notebook with all default settings using the identical EGF and EGFR sequences reported in the competition. The source data can be found in the zip file `EGF_EGFR_61de7.result.zip` and the rank_001 model is used.
2. `Human_EGF_chain_A_only.pdb`: Same as `Human_EGF.pdb` but only chain A (EGF) is preserved.
3. `round1_winner.pdb`: Obtained from [predicted structures from the first round](https://api.adaptyvbio.com/storage/v1/object/public/egfr_design_competition/docking_predictions.zip) under `docking_predictions/predicted_structures/candidates/martin.pacesa-EGFR_l138_s90285_mpnn2_relaxed_rank_001_alphafold2_ptm_model_1_seed_000.pdb`.

`data/tables`
1. `foldseek_adaptyv_destress_binder_merged.tsv`: Destress & Other Biophysical Metrics of the binders obtained from https://github.com/wells-wood-research/adaptyv-bio-analysis/blob/main/data/foldseek_adaptyv_destress_binder_merged.tsv
2. `interchain_residue_indices.csv`: Set of residues within 4 angstrom of chain A and chain B
3. `neutralisation_coefficient.csv`: Manually extracted neutralisation coefficient
4. `tmscores_to_egf.csv`: TM-score of the binders to EGF
5. `neutralisation_df_filtered`: A merged dataframe of other tables in this directory filtered for binders tested with neutralisation assay. Constructed by the notebook

## Reproducing the analysis
Pre-requisite:

Foldseek (to compute binder TM-score against Human EGF)

1. Download and unzip the structure prediction zip files from https://github.com/adaptyvbio/egfr_competition_2 and place the output directory under `data/`
2. Copy the `Human_EGF.pdb` file to the unzipped `structure_predictions` directory
3. Run `bash make_tables.sh` under the `scripts` directory and provide a path to the FoldSeek executable
4. Now you have all the data required for running the Jupyter notebook!

Figures:

All figures are produced by the notebook with the exception of the EGFR structure which was produced using ChimeraX. 

Related Repos:
- https://github.com/adaptyvbio/egfr_competition_1
- https://github.com/adaptyvbio/egfr_competition_2

TODO: Add References and Acknowledgements
