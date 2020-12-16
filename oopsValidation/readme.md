# What we did
sao.rdf and rains.rdf were used with the OOPS! online service at http://oops.linkeddata.es/. The content of each file was checked directly by copy and pasting into the direct input field. The files contain imports for PROV-O, DC, EP-Plan, P-Plan and ML Schema. The imports for ontologies using the w3id permanent identifier was replaced with direct links as the OOPS! service seems to be struggling with those.  

# About SAO results

We treat the suggestion of the tool that https://w3id.org/sao#System and  http://www.w3.org/ns/prov#Organization may be equivalent (highlighted as important issue) as a false positive, perhaps caused by the specific NLP mechanisms used to compare concept names. 


# About RAINS results

The tool suggested that the following relations could be defined as equivalent: https://w3id.org/ep-plan#achieves, http://www.w3.org/ns/mls#achieves
and  http://www.w3.org/ns/mls#hasPart, https://w3id.org/ep-plan#hasPart. These are however, not  equivalent and they are not even needed/used in the context of the Rains ontology. 

# Issues identified within imported ontologies

The tool  identified some issues related to all of the imported ontologies, however, these are outwith our control. 
