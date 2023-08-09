
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .


<http://example.org/openWEMI/> a owl:Ontology ;
  rdfs:label "openWEMI ontology" ;
  rdfs:comment "The openWEMI ontology provides a high-level framework for vocabularies related to creations, from abstract notions of a work to tangible items. The classes and properties defined by openWEMI are intentionally broad and unrestricted, allowing for implementing vocabularies to better describe their specific target creations through subclasses, subproperties and other alignments. openWEMI builds on the work done in the library community (FRBR) but with many fewer constraints, thus improving reuse for metadata communities."@en .

<http://example.org/openWEMI/Endeavor>
  a owl:Class ;
  rdfs:label "Endeavor"@en ;
  skos:definition "A creation."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:comment "Endeavor is an umbrella class that unites the classes Work, Expression, Manifestation, Item."@en .
  
<http://example.org/openWEMI/Work>
  a owl:Class ;
  rdfs:label "Work"@en ;
  skos:definition "An abstract notion of an artistic or intellectual creation."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subClassOf <http://example.org/openWEMI/Endeavor> ;
  rdfs:comment " A work is an abstraction that represents the concepts behind a creation. Each metadata community will have a different definition of Work, but it should be the broadest definition of the creations being described."@en .
  
<http://example.org/openWEMI/Expression>
  a owl:Class ;
  rdfs:label "Expression"@en ;
  skos:definition "A perceivable form of the creation."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subClassOf <http://example.org/openWEMI/Endeavor> ;
  rdfs:comment "Creations are made tangible through some kind of expression, such as text, sound, or a visual form. There may be more than one expression of a work of the same type or of different types."@en ;
  skos:example "An expression could be a text, a recorded sound, a blueprint."@en.

<http://example.org/openWEMI/Manifestation>
  a owl:Class ;
  rdfs:label "Manifestation"@en ;
  skos:definition "The physical embodiment of a creation."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subClassOf <http://example.org/openWEMI/Endeavor> ;
  rdfs:comment "A manifestation is a creation that has been realized in some physical or digital form. A manifestation may be a single realization or a realization that is produced in multiple copies such as the publication of a music compact disk or the manufacture of a shirt."@en ;
  skos:example "A published book or article, a film issued on DVD, a sculpture, a manufactured thing, usually in multiple copies, such as a television, a shirt, a package of frozen peas."@en .
  
<http://example.org/openWEMI/Item>
  a owl:Class ;
  rdfs:label "Item"@en ;
  skos:definition "An exemplar of a creation."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subClassOf <http://example.org/openWEMI/Endeavor> ;
  rdfs:comment "An Item is a single instance of the creation, something that can have a place on a shelf or a location online."@en ;
  skos:example "Your copy of a book, the shirt you own, the frozen peas in your freezer" @en .

<http://example.org/openWEMI/responsibleEntity>
  a rdfs:Property ;
  rdfs:label "responsible entity"@en ;
  skos:definition "One responsible for the creation, production, distribution, maintenance, or ownership of a created entity."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:domain <http://example.org/openWEMI/Endeavor> ;
  rdfs:comment "It is assumed that creations have been affected by an agent with the ability to act. The types of agents is very broad and not constrained by this property."@en ;
  skos:example "An author, a manufacturing company, a performer, a legislative body."@en .
      
<http://example.org/openWEMI/relatedEndeavor>
  a rdfs:Property ;
  rdfs:label "related endeavor"@en ;
  skos:definition "An Endeavor that is related in some way to a different Endeavor."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:domain <http://example.org/openWEMI/Endeavor> ;
  rdfs:range <http://example.org/openWEMI/Endeavor> ;
  rdfs:comment "This provides a non-specific relationship between two Endeavors. The specific relationship type can be defined as a sub-property of relatedEndeavor."@en .

<http://example.org/openWEMI/relatedWork>
  a rdfs:Property ;
  rdfs:label "related work"@en ;
  skos:definition "Another work that is related in some way to a work."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:domain <http://example.org/openWEMI/Work> ;
  rdfs:range <http://example.org/openWEMI/Work> ;
  rdfs:comment "This provides a non-specific relationship between two Works. The specific relationship type can be defined as a sub-property of relatedWork."@en ;
  skos:example "A movie based on a book ("Gone with the Wind"); a sculpture based on another sculpture (a replica of Michelangelo's David)."@en .

<http://example.org/openWEMI/relatedExpression>
  a rdfs:Property ;
  rdfs:label "related expression"@en ;
  skos:definition "Another expression that is related in some way to an expression."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:domain <http://example.org/openWEMI/Expression> ;
  rdfs:range <http://example.org/openWEMI/Expression> ;
  rdfs:comment "This provides a non-specific relationship between two Expressions. The specific relationship type can be defined as a sub-property of relatedExpression."@en ;
  skos:example "A remix of a sound file; a translation of a text."@en .

<http://example.org/openWEMI/relatedManifestation>
  a rdfs:Property ;
  rdfs:label "related manifestation"@en ;
  skos:definition "Another manifestation that is related in some way to a manifestation."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:domain <http://example.org/openWEMI/Manifestation> ;
  rdfs:range <http://example.org/openWEMI/Manifestation> ;
  rdfs:comment "This provides a non-specific relationship between two Manifestations. The specific relationship type can be defined as a sub-property of relatedManifestation."@en ;
  skos:example "A reprint of a book; a sound file in WAV and one in MP3."@en .

<http://example.org/openWEMI/relatedItem>
  a rdfs:Property ;
  rdfs:label "related item"@en ;
  skos:definition "Another item that is related in some way to an item."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:domain <http://example.org/openWEMI/Item> ;
  rdfs:range <http://example.org/openWEMI/Item> ;
  rdfs:comment "This provides a non-specific relationship between two Items. The specific relationship type can be defined as a sub-property of relatedItem."@en .

<http://example.org/openWEMI/expresses>
  a rdfs:Property ;
  rdfs:label "expresses"@en ;
  skos:definition "An endeavor that expresses a work."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subPropertyOf <http://example.org/openWEMI/relatedEndeavor> ;
  rdfs:domain <http://example.org/openWEMI/Expression> ;
  rdfs:range <http://example.org/openWEMI/Work> ;
  rdfs:comment "A relationship asserted from an Expression to a Work that it expresses."@en .


 <http://example.org/openWEMI/expressedBy>
  a rdfs:Property ;
  rdfs:label "expressed by"@en ;
  skos:definition "An expression of a work."@en ;
  owl:inverseOf <http://example.org/openWEMI/expresses> ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subPropertyOf <http://example.org/openWEMI/relatedEndeavor> ;
  rdfs:domain <http://example.org/openWEMI/Work> ;
  rdfs:range <http://example.org/openWEMI/Expression> ; 
  rdfs:comment "A relationship asserted from a Work to an Expression that expresses the Work."@en .


<http://example.org/openWEMI/manifests>
  a rdfs:Property ;
  rdfs:label "manifests"@en ;
  skos:definition "An endeavor that manifests an expression or a work."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subPropertyOf <http://example.org/openWEMI/relatedEndeavor> ;
  rdfs:domain <http://example.org/openWEMI/Manifestation> ;
  rdfs:range [
    a owl:Class ;
    owl:unionOf (
      <http://example.org/openWEMI/Work> 
      <http://example.org/openWEMI/Expression>
    )
  ] ;
rdfs:comment "A relationship asserted from a Manifestation to an Expression or a Work."@en .

<http://example.org/openWEMI/manifestedBy>
  a rdfs:Property ;
  rdfs:label "manifested by"@en ;
  skos:definition "A manifestation of a work or an expression."@en ;
  owl:inverseOf <http://example.org/openWEMI/manifests> ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subPropertyOf <http://example.org/openWEMI/relatedEndeavor> ;
  rdfs:domain [
      a owl:Class ;
      owl:unionOf (
       <http://example.org/openWEMI/Work> 
       <http://example.org/openWEMI/Expression>
     )
    ] ;
  rdfs:range <http://example.org/openWEMI/Manifestation> ;
rdfs:comment "A relationship asserted from a Work or an Expression to a Manifestation."@en .

    
<http://example.org/openWEMI/instantiates>
  a rdfs:Property ;
  rdfs:label "instantiates"@en ;
  skos:definition "An Endeavor that instantiates a Manifestation, an Expression or a Work."@en ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subPropertyOf <http://example.org/openWEMI/relatedEndeavor> ;
  rdfs:domain <http://example.org/openWEMI/Item> ;
  rdfs:range [
    a owl:Class ;
    owl:unionOf (
      <http://example.org/openWEMI/Work>
      <http://example.org/openWEMI/Expression>
      <http://example.org/openWEMI/Manifestation>
    )
  ] ;
rdfs:comment "A relationship asserted from an Item to a Manifestation, an Expression, or a Work."@en .


<http://example.org/openWEMI/instantiatedBy>
  a rdfs:Property ;
  rdfs:label "instantiated by"@en ;
  skos:definition "An instatiation of a manifestation, an expression or a work."@en ;
  owl:inverseOf <http://example.org/openWEMI/instantiates> ;
  rdfs:isDefinedBy <http://example.org/openWEMI/> ;
  rdfs:subPropertyOf <http://example.org/openWEMI/relatedEndeavor> ;
  rdfs:domain [
      a owl:Class ;
      owl:unionOf (
       <http://example.org/openWEMI/Work> 
       <http://example.org/openWEMI/Expression>
       <http://example.org/openWEMI/Manifestation>
     )
    ] ;
  rdfs:range <http://example.org/openWEMI/Item> ;
  rdfs:comment "A relationship asserted from a Work, an Expression, or a Manifestation to an Item."@en .

