# RNA_Motif_ID

#Overview
Analysis a CSV file of RNA structure from scanfold to appened data on local motifs that ar present in each structure.

#Methodology 
The program uses a recursive algorithm to identify stems. Once stems are identified each stem is read individually to find each motif. The stems are idenfied by reading the DBN from left to right once a ")" is found it will count untill it finds a "(". Then, it reverse the ittreation to pair every ")" with the corresponding "(". Finally, the indentifed stem is abstracted from the DBN leaving "[n]" where n is number of nucleotides abstracted, this is important for finding correct index locations of necleotides in each stem. When itreating through the DBN to find each stem if a "[n]" is encountred the correct pairing of "(" and ")" can be over counted so the algorithm keeps track of any "(" found before the "[n]" and notes them as error brackets that should be paired with the overcounted ")".

#Insitlation and Dependencies
Program is written in python 3.11.9 and uses the pandas libary. Program was designed with local machines in mind. It has been running of off my computer with data input of 35,000 elements. The program finish with in a couple minutes at this size.

#Usuage Instructions
Program needs a CSV file that contains scanfold data with "gene_name,transcript_id,structure_number,i,j,sequence,DBN-mfe,DBN-refold,MFE,z-score,ED,tID_version,UTR" as the first line. The name of this file must match the output variable in the program. The output will be a ASV file ("*" sepreated file) it can be a CSV as the lists that are appened use commas.
