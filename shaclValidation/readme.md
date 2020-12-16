# Tools needed

We have used a binary distribution of the tool (version 1.3.2)  from TopQuadrant https://github.com/TopQuadrant/shacl. 

Files used in the evaluation were: 
 - accountabilityTrace.ttl (an example paret of an execution trace annotated using EP-Plan, PROV-O, RAInS, and SAO ontologies
 
 - includeLimitationElementShape.ttl (A file containing a SHACL rule stating that an instance of sao:InformationRealization produced by activity corresponding to a step for which this constraint was defined must include an element of type rains:Limitation)

After downloading the tool we run the command 

```
./shaclvalidate.sh -datafile accountabilityTrace.ttl -shapesfile includeLimitationElementShape.ttl
```

The output shoudl confirm that the constriant has been satisfied. 

```
@prefix sao:   <https://w3id.org/sao#> .
@prefix ex:    <http://example.com/ns#> .
@prefix rdf:   <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix owl:   <http://www.w3.org/2002/07/owl#> .
@prefix xsd:   <http://www.w3.org/2001/XMLSchema#> .
@prefix ep-plan: <https://w3id.org/ep-plan#> .
@prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rains: <https://w3id.org/rains#> .
@prefix prov:  <http://www.w3.org/ns/prov#> .

[ a       <http://www.w3.org/ns/shacl#ValidationReport> ;
  <http://www.w3.org/ns/shacl#conforms>
          true
] .
```

If the prov:hadMember ex:LimitationDesc triple is removed from the  accountabilityTrace.ttl the output inidcates that the costraints has been violated

```

[ a       <http://www.w3.org/ns/shacl#ValidationReport> ;
  <http://www.w3.org/ns/shacl#conforms>
          false ;
  <http://www.w3.org/ns/shacl#result>
          [ a       <http://www.w3.org/ns/shacl#ValidationResult> ;
            <http://www.w3.org/ns/shacl#focusNode>
                    ex:ProduceSpecificationStep1 ;
            <http://www.w3.org/ns/shacl#resultMessage>
                    "The rains:Limitation element is missing" ;
            <http://www.w3.org/ns/shacl#resultSeverity>
                    <http://www.w3.org/ns/shacl#Violation> ;
            <http://www.w3.org/ns/shacl#sourceConstraint>
                    []  ;
            <http://www.w3.org/ns/shacl#sourceConstraintComponent>
                    <http://www.w3.org/ns/shacl#SPARQLConstraintComponent> ;
            <http://www.w3.org/ns/shacl#sourceShape>
                    ex:RequiredElementShape ;
            <http://www.w3.org/ns/shacl#value>
                    ex:ProduceSpecificationStep1
          ]
] .
```
