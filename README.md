# Script-for-CNVsDetection
Python script to detect CNVs after a Galaxy Diagnostic Analysis based on coverage variability between patients of a same Illumina run. 
This script compares depth and coverage data generated by Picard Metrics, previously downloaded from GalaxyDiagnostic via BioBlend. 
Coverage data are obtained in galaxy for each patient (23 patients, including at least 6 female individuals), from the BAM alignment file using the Picard metrics (Compute both the depth and breadth of coverage, galaxy, tool version 2.22.1, see also reposetory Scripts-for-GalalaxyDiagnostic-Paris-Saclay-Worflow and the workflow Galaxy-Workflow-2016-11-14_SNV_generic_GATK3.4.ga). The individual data of each patient are then compared to the average of all female individuals analyzed together in the run with this Python script.

To use the script :

1) create 2 directories : 
Patients/ to put all XXXXX_count_sorted.bed (23 files, one per patient) from our galaxy workflow (Files generated at step 30 of the workflow).
Females/ to put among patients files those (at least 6 files) corresponding to a caryotype 46,XX (females)

2) command line to run the script : python CNV4X.py -p Patients/ -t Females/

Note : Python script for Python version 2.7

Author : Christophe Habib, Bioinformatician (2015-2017 in our lab - email : christophe.habib@gmail.com)
