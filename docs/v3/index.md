<!-- remove all comments before releasing -->
<!-- This is the name of the module as it will appear in GenePatter, and its version, for clarity -->
# tfsites.MapTfDNAInteractions (v1)

<!-- A brief text description of the module, usually one sentence in length. -->
**Description**: Maps the crystal structure for TF-DNA interaction.

<!-- This field is for the author or creator of the module. If the algorithm of the module is from a published paper, this is usually the first or corresponding author from the paper. If the module algorithm is unpublished, this is usually the developer of the module itself. This field can simply be a name of a person or group. -->
**Authors**: Joe Solvasson; UCSD - Farley Lab, UCSD; Simran Jandu - Farley Lab, UCSD; Ted Liefeld - Mesirov Lab, Broad Institute

<!--This field is used for responding to help requests for the module, and should be an email address or a link to a website with contact information or a help forum. -->
**Contact**: [Forum Link](https://groups.google.com/forum/?utm_medium=email&utm_source=footer#!forum/genepattern-help)


<!-- Why use this module? What does it do? If this is one of a set of modules, how does this module fit in the set? How does it work? write overview as if you are explaining to a novice. Include any links or images which would serve to clarify -->
## Summary

Maps the crystal structure for TF-DNA interaction.

<!-- appropriate papers should be cited here -->
## References

<!-- links to your source repository **specific to the release version**, the Docker image used by the module (as specified in your manifest), and (if applicable) the sha link to the Dockerfile used to build your Docker image -->
## Source Links
* [Source repository]([https://github.com/genepattern/ExampleModule/tree/v2](https://github.com/genepattern/tfsites.MapTfDNAInteractions))

## Parameters
<!-- short description of the module parameters and their default values, as well as whether they are required -->

| Name | Description <!--short description--> | Default Value |
---------|--------------|----------------
| pdb or cif file * |  The file to be read in pdb or cif format |
| outpiut filename * | he basename to use for output file  |
| tf name*  | Transcription Factor name |
| aa number adjuster * | aa number adjuster?? |
| keep chains * | keep chains?? |
| direct hbond distance * | direct hbond distance?? |
| alpha fold * | alpha fold?? |
| add hydrogens * | add hydrogens?? |
| model number * | model number?? |


\*  required

## Input Files
<!-- longer descriptions of the module input files. Include information about format and/or preprocessing...etc -->

1. pdb or cif file  
    A long form explanation of the parameter. For example: This is the file which will be read in by the python script and to which text will be added, if add_custom_message is set to true. The parameter expects a text file with a .txt extension (e.g. file.txt)
    
## Output Files
<!-- list and describe any files output by the module -->



## Example Data
<!-- provide links to example data so that users can see what input & output should look like and so that they and we can use it to test -->

Input:  
[Example pbm input file](https://github.com/jsolvason/tfsites-webportal/blob/335ea88a7a03633ba0f2726019d00591011ac419/05-mapTfDnaInteractions/05-input_1pue.pdb)


## Requirements
<!--This section is typically used to list any special requirements for running the module, such as, language/operating system requirements and Docker images. -->

Requires the [genepattern/example-module:2 Docker image](https://hub.docker.com/layers/150060459/genepattern/example-module/2/images/sha256-ae4fffff67672e46b251f954ad226b7ad99403c456c1c19911b6ac82f1a27f2f?context=explore).

## License

`tfsites.MapTfDNAInteractions` is distributed under a modified BSD license available at [https://github.com/genepattern/tfsites.MapTfDNAInteractions/blob/develop/LICENSE](https://github.com/genepattern/tfsites.MapTfDNAInteractions/blob/develop/LICENSE)

## Version Comments
<!--For each version of a module, provide a short comment about what was changed in the new version of a module. Version comments consist of 3 parts: a date, a version number, and a short description. The date should be the release date of that version of the module, and the version number should match the version of the module for which it corresponds to. The description can be short, but should be informative (e.g. "added support for log transformed data", or "fixed bug with out of memory exception"). When a user views the documentation, all version comments up to and including the current version will be displayed, and act as a short version history for the module. -->

| Version | Release Date | Description                                 |
----------|--------------|---------------------------------------------|
| 1 | March 11, 2025 | Initial version for team use. |
