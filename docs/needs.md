# Needs

## Environment

This package is coded in Pyspark language. Users must create a spark session.
C-Ways create a `cspark` package to easy spark usage : https://gitlab.com/tools-cways/c-spark

## Inputs

The main functions take as arguments several spark dataframes that have a homogenized format. Those dataframes should be the output of package `c-flash-preprocessing` (not ready yet).

The following dataframes can be required as inputs:

- **Clients**: each row is a client and some features must be there like `id_client`, `civilite`, `date_adhesion`, `age`, `classe_age`
- **Transactions**: each row is a transactions and some features must be there like `lbl_secteur`, `date_achat`, `mnt_net_ttc`, `qte`, `mnt_remise`, `lbl_produit`, `lbl_magasin`, `canal`

The feature `canal` modalities must be in ["BOUTIQUE", "WEB"]
The feature `civilite` modalities must be in ["HOMME", "FEMME"]

Besides, those two type of dataframes should be **split by Year of analysis N vs N-1**
