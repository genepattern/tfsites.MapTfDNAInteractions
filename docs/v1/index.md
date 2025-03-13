<!-- remove all comments before releasing -->
<!-- This is the name of the module as it will appear in GenePatter, and its version, for clarity -->
# tfsites.MapTfDNAInteractions (v1)

<!-- A brief text description of the module, usually one sentence in length. -->
**Description**: Maps the crystal structure for TF-DNA interaction.

<!-- This field is for the author or creator of the module. If the algorithm of the module is from a published paper, this is usually the first or corresponding author from the paper. If the module algorithm is unpublished, this is usually the developer of the module itself. This field can simply be a name of a person or group. -->
**Authors**: Joe Solvason - Farley Lab, UCSD; Simran Jandu - Farley Lab, UCSD; Ted Liefeld - Mesirov Lab, Broad Institute

<!--This field is used for responding to help requests for the module, and should be an email address or a link to a website with contact information or a help forum. -->
**Contact**: [Forum Link](https://groups.google.com/forum/?utm_medium=email&utm_source=footer#!forum/genepattern-help)


<!-- Why use this module? What does it do? If this is one of a set of modules, how does this module fit in the set? How does it work? write overview as if you are explaining to a novice. Include any links or images which would serve to clarify -->
## Summary

This module takes a TF-DNA crystal structure as input and reports all hydrogen bonds which stabilize the TF-DNA complex. A two-dimensional map is generated, which shows every base of the DNA binding site, which bases make hydrogen bonds with the transcription factor, and which part of the DNA polymer is interacting (nucleotide, deoxyribose, or phosphate). The essential positions are the bases in which the nucleotide makes direct hydrogen bonds with the transcription factor. 

<!-- appropriate papers should be cited here -->
## References

<!-- links to your source repository **specific to the release version**, the Docker image used by the module (as specified in your manifest), and (if applicable) the sha link to the Dockerfile used to build your Docker image -->
## Source Links
* [Source repository]([https://github.com/genepattern/ExampleModule/tree/v2](https://github.com/genepattern/tfsites.MapTfDNAInteractions))

## Parameters
<!-- short description of the module parameters and their default values, as well as whether they are required -->

| Name | Description <!--short description--> | Default Value |
---------|--------------|----------------
| pdb or cif file * |  File containing the TF-DNA crystal structure. |
| output filename * | The basename to use for output visualization file.  |
| tf name *  | Name of the transcription factor to use for crystal structure analysis. |
| keep chains | Only one protein chain and 2 strands of DNA (forward and reverse) can be analyzed at once. Use this option to select the chains to analyze if there are additional chains in the file. For example, if the structure is a dimer you must analyze one monomer at a time. Let's assume the two monomer proteins make up chains A and B, and two DNA molecules C and D. You will run the program once with chains "ACD" and once with "BCD". | All |
| aa number adjuster | This will add all amino acid positions by this number. If you are inputting a PDB-formatted file, you do not need to use this parameter. If you are inputting an mmCIF file outputted from AlphaFold, then you can enter the starting position of the DNA binding domain here. For example, if the full-sized protein is 500 amino acids long, but you only fold the inner 50-350 amino acids, you can set aa_number_adjuster to 50 to correct the amino acid number. | 0 |
| direct hbond distance | The number of angstroms allowed between a hydrogen bond donor and acceptor to predict a hydrogen bond exists. For crystal structures generated from real data, 3.5 angstroms is common. If the structure was generated from AlphaFold, you can go as high as 5 angstroms. | 3.5 |
| alpha fold | Indicate whether AlphaFold was used to generate the crystal structure. This is important because of assumptions made about the input file. | False |
| model number | If AlphaFold is used, it will output different model numbers. Determine which model you want to choose, and indicate it here. Unless you are an expert and there is a particular reason to use an alternative model, you should use Model 1. | 1 |
| plot width | Width of the output figure, in inches. | 10 |
| plot height | Height of the output figure, in inches. | 20 |
| aa label text size | Font size for the amino acid labels. For most structures, 9 point font works. However if the text is too large or too small, this parameter can be adjusted as needed. | 9 |
| add hydrogens | Whether to add hydrogens to the crystal structure. Hydrogens are not included in the PDB files downloaded from the protein data bank, nor the mmCIF files downloaded from AlphaFold.  | False |

\*  required

## Input Files
<!-- longer descriptions of the module input files. Include information about format and/or preprocessing...etc -->

1. pdb or cif file
- This file can be either a PDB file (.pdb extension) or mmCIF file (.cif extension). If add hydrogens is set to true, then this file will be modified to add hydrogens to the crystal structure. 
    
## Output Files
<!-- list and describe any files output by the module -->
1. output filename
- This file outputted as an SVG (.svg extension). This file contains the two-dimensional map that displays the interactions between the TF and DNA. 

## Example Data
<!-- provide links to example data so that users can see what input & output should look like and so that they and we can use it to test -->

PDB Input: [Example file](https://github.com/jsolvason/tfsites-webportal/blob/genepattern/05-mapTfDnaInteractions/05-input_1pue.pdb)

CIF Input: [Example file](https://github.com/jsolvason/tfsites-webportal/edit/genepattern/05-mapTfDnaInteractions/05-input_1pue.cif)

SVG Output: [Example file](https://github.com/jsolvason/tfsites-webportal/blob/genepattern/05-mapTfDnaInteractions/05-output/05-output_crystal-structure-map.svg)


## Requirements
<!--This section is typically used to list any special requirements for running the module, such as, language/operating system requirements and Docker images. -->

Requires the [genepattern/tfsites:15.5.1 or later Docker image](https://hub.docker.com/r/genepattern/tfsite)).

## License

`tfsites.MapTfDNAInteractions` is distributed under a modified BSD license available at [https://github.com/genepattern/tfsites.MapTfDNAInteractions/blob/develop/LICENSE](https://github.com/genepattern/tfsites.MapTfDNAInteractions/blob/develop/LICENSE)

## Version Comments
<!--For each version of a module, provide a short comment about what was changed in the new version of a module. Version comments consist of 3 parts: a date, a version number, and a short description. The date should be the release date of that version of the module, and the version number should match the version of the module for which it corresponds to. The description can be short, but should be informative (e.g. "added support for log transformed data", or "fixed bug with out of memory exception"). When a user views the documentation, all version comments up to and including the current version will be displayed, and act as a short version history for the module. -->

| Version | Release Date | Description                                 |
----------|--------------|---------------------------------------------|
| 1 | March 11, 2025 | Initial version for team use. |
