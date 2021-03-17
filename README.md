# ESWC_2021_Evaluation

## SHACL proof of concept test 

See the folder shaclValidationExample

## Using OOPS! Ontology Pitfall Scanner  

See the folder oopsValidation for details.

## Creation of Example Knowledge Graph 

We have used the accountability fabric tool in https://github.com/RAINS-UOA/rains-workflow-builder/tree/ESWC-2021. The branch remains frozen with the snapshoot of the tool used for generating and querying the example knowledge graph. 

For details about the knowledge graph see and how the tool was used see the exampleKnowledgeGraph folder 

## Limitations of the tool

The version of the tool used for evaluation is a proof of concept and not a serious piece of software. It serves a specific purpose and it was mostly used by researchers who were aware of its insufficencies. Use at your own risk..

If you attempt to run the tool please be aware of some unpredictable behaviour that may prevent your data to be saved in the graph store. This is likely related to a bug in the connection pool whcih will be looked at in future. In the meantime, to make sure that your plans and execution traces are saved always restart the server app before pressing save from the HTML page, which reduces the chances of connection freezing. Also the code currently has various validations missing including not escaping special characters that may break JSON-LD payload so be cautios when creating free text (e.g., for labels and comments) and do not use ", etc.   

---
The work presented here is licensed under a Creative Commons Attribution NonCommercial ShareAlike 4.0 International License (CC BY-NC-SA 4.0) https://creativecommons.org/licenses/by-nc-sa/4.0/
