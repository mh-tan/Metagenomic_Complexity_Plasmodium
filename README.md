# Metagenomic_Complexity_Plasmodium

Description of files available in the 'data' folder. If you use data or code from this work, please cite:

Tan, M.H., Bangre, O., Rios-Teran, C.A., Tiedje, K.E., Deed, S.L., Zhan, Q., Rasyidi, F., Pascual, M., Ansah, P.O. and Day, K.P. 2025. Metagenomic analysis reveals extreme complexity of *Plasmodium* spp. infections in high transmission in West Africa. medRxiv, pp.2025-04.
https://www.medrxiv.org/content/10.1101/2025.04.29.25326533v1
<br></br>

If you use *var* DBLα primers and the *var*coding approach, please cite the following:

Tan, M.H., Bangre, O., Rios-Teran, C.A., Tiedje, K.E., Deed, S.L., Zhan, Q., Rasyidi, F., Pascual, M., Ansah, P.O. and Day, K.P. 2025. Metagenomic analysis reveals extreme complexity of *Plasmodium* spp. infections in high transmission in West Africa. medRxiv, pp.2025-04.
https://www.medrxiv.org/content/10.1101/2025.04.29.25326533v1

Tiedje, K.E., Zhan, Q., Ruybal-Pésantez, S., Tonkin-Hill, G., He, Q., Tan, M.H., Argyropoulos, D.C., Deed, S.L., Ghansah, A., Bangre, O., Oduro, A.R., Koram, K.A., Pascual, M., Day, K.P. 2023. Measuring changes in *Plasmodium falciparum* census population size in response to sequential malaria control interventions. eLife 12:RP91411
https://doi.org/10.7554/eLife.91411.2

=====

gadm41_GHA_shp.zip: Shapefile for Ghana needs to be downloaded from https://gadm.org/download_country.html
<br></br>

#### pRBC_varcoding_primerSeqs.txt
Primer sequences used for amplifying DBLα tags included forward barcoded primers and an unbarcoded reverse primer. Both forward and reverse primers also contain Illumina Nextera overhangs to facilitate subsequent preparation of sequencing libraries.

#### data/PilotS1toS8_DBS_pRBC.id96.DBLaTypes.fasta.gz
*P. falciparum* DBLα type sequences generated from post-clusterDBLa.

#### data/S8_DBS_pRBC_Repeats_OtuTable.txt.gz
Matrix detailing presence/absence of each DBLα type in isolates.

#### data/S8_pRBC_Field_IsolateMetadata.txt, S8_DBS_Field_IsolateMetadata.txt, S8_pRBC_Repeats_IsolateMetadata.txt
Contains general isolate metadata, outcomes of species-specific PCR based on 18S rRNA for DBS and 100μL pRBC samples, and MOI estimated based on various assays.
- **Isolate**: General identifier of isolate
- **IsolateID**: Identifier of isolate, including details on pRBC volume, repeat number (if any), MID barcode, and pool number
- **Survey**: Survey number during which the isolate was collected
- **MID**: Barcode number used for multiplexing
- **Control**: Whether the isolate is a control isolate (Yes/No)
- **Repeat**: Whether the isolate was repeated (R1/R2/No)
- **AgeGrp**: Age group of host individual from which isolate was sampled
- **ParasiteuL**: Parasite density (parasites/μL)
- **DBS_Pf/Pm/Po/Pv**: Outcome of species-specific PCR on DBS based on 18S rRNA (0: undetected, 1: detected)
- **WB100_Pf/Pm/Po/Pv**: Outcome of species-specific PCR on 100μL pRBC based on 18S rRNA (0: undetected, 1: detected)
- **Pf/Pm/Poc/PowMOI**: Outcome of MOI estimation for the different *Plasmodium* spp. based on various assays (Pf: varcoding, Pm: microsatellites, Poc/Pow: potra)
- **upsA**: Number of upsA DBLα types detected for the isolate
- **non-upsA**: Number of non-upsA DBLα types detected for the isolate
- **NumTypes**: Total number of DBLα types detected for the isolate (i.e. repertoire size)
- **found_min1_code**: A code to represent *P. falciparum* detection in the four pRBC volumes for the isolate, where >= 1 DBLα type was detected in the isolate (N-Y-Y-Y: undetected in 1μL pRBC but detected in 10, 50, and 100μL pRBC)
- **found_min20_code**: A code to represent *P. falciparum* detection in the four pRBC volumes for the isolate, where >= 20 DBLα types were detected in the isolate (N-N-Y-Y: undetected in 1 and 10μL pRBC but detected in 50 and 100μL pRBC)

#### data/id96.FIELD.fold_diff.txt
Contains estimation of fold difference in Pf-MOI between pairwise pRBC volumes
- **Isolate**: General identifier of isolate
- **volS_name**: States the smaller pRBC volume in the pairwise comparison
- **volB_name**: States the bigger (larger) pRBC volume in the pairwise comparison
- **label**: Label of the pairwise comparison
- **diff_metric**: Metric for which the fold difference is calculated
- **volS_value**: Pf-MOI estimated in the smaller pRBC volume
- **volB_value**: Pf-MOI estimated in the bigger (larger) pRBC volume
- **diff_value**: Fold difference in Pf-MOI (i.e. volB_value/volS_value)
- **label_long**: Longer label of the pairwise comparison for visualisation

#### data/id96.FIELD.PTS.txt
Contains estimation of genetic similarity between pairwise pRBC volumes for a same isolate, based on pairwise type sharing (PTS)
- **Isolate**: General identifier of isolate
- **stateA**: States the smaller pRBC volume in the pairwise comparison
- **stateB**: States the bigger (larger) pRBC volume in the pairwise comparison
- **sampleA**: States the IsolateID of stateA in the pairwise comparison
- **sampleB**: States the IsolateID of stateB in the pairwise comparison
- **PTS_AtoB**: Directional PTS, with repertoire size of sampleA as the denominator (PTS = number of shared DBLα types / repertoire size of sampleA)
- **PTS_BtoA**: Directional PTS, with repertoire size of sampleB as the denominator (PTS = number of shared DBLα types / repertoire size of sampleB)
- **Pf-MOI_A**: Pf-MOI estimated in stateA of an isolate
- **Pf-MOI_B**: Pf-MOI estimated in stateB of an isolate
- **ParasiteuL**: Parasite density (parasites/μL)
- **AgeGrp**: Age group of host individual from which isolate was sampled
- **found_min_code**: A code to represent *P. falciparum* detection in the four pRBC volumes for the isolate, where >= 20 DBLα types were detected in the isolate (N-N-Y-Y: undetected in 1 and 10μL pRBC but detected in 50 and 100μL pRBC)
- **label_long**: Longer label of the pairwise comparison for visualisation

#### data/id96.FIELD_POP.PTS.txt
Contains population-level genetic similarity among isolates, based on pairwise type sharing (PTS)
- **IsolateID1**: Identifier of isolate, including details on pRBC volume, repeat number (if any), MID barcode, and pool number
- **IsolateID2**: Identifier of isolate, including details on pRBC volume, repeat number (if any), MID barcode, and pool number
- **PTS_score**: PTS, with sum of repertoire size of SampleID1 and SampleID2 as the denominator (PTS = number of shared DBLα types / (SampleID1 repertoire size + SampleID2 repertoire size))
- **label**: The pRBC volume for which the population estimation was performed

#### data/MAPS_prevalence_data.txt
Infection prevalence (PfPr2-10) for Ghana from the Malaria Atlas Project

#### data/S8MRS_DBS_Bongo_prevalence_data.txt
Parasite prevalence in Bongo District calculated based on different levels of datasets: (1) Survey DBS from host 2-10yr, (2) Survey DBS from all ages, (3) Survey DBS from all ages and adjusted for deep sampling with 100μL pRBC

