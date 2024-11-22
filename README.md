# OOD Test

Out-Of-Distribution Test (OOD Test) is a benchmark developed from PDBbind v2020 to minimise dataset leakage between the train and test datasets, introduced in https://chemrxiv.org/engage/chemrxiv/article-details/6675a38d5101a2ffa8274f62

## Benchmark description

OOD Test is a split of the PDBbind v2020 dataset, created with the goal of minimising similarity between the training and test data.

The split can be found in the "split" column of *index_oodtest.csv*. OOD Test has the following properties:

- Test set complexes are from the Refined set of PDBbind v2020.
- All ligands in the training data have less than 0.5 Tanimoto similarity to the test set ligands, using ECFP6 fingerprints.
- All proteins in the training data have less than 50% sequence identity to test set proteins, calculated with MMseqs2.
- The test set excludes heavy ligands (molecular weight > 1000 Da) and ligands with more than 20 rotatable bonds.
- There is no Pocket Pfam cluster overlap between the training and test datapoints. The Pocket Pfam clusters are defined by Zhu et al. in *Assessment of the Generalization Abilities of Machine-Learning Scoring Functions for Structure-Based Virtual Screening (JCIM, 2022)*.
- The test and training sets include 295 and 18,402 complexes respectively.
