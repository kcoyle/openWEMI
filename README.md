# openWEMI

This is work to create a non-constrained version of FRBR's Work, Expression, Manifestation, Item. In particular it removes any disjoint rules between the WEMI entities. It is based on the [FRBR Core](http://purl.org/vocab/frbr/core) created by Ian Davis and Richard Newman, with contributions by Bruce D'Arcus. 

The minimal WEMI set has these classes and subclasses:
* Endeavor
  * Work
  * Expression
  * Manifestation
  * Item
* ResponsibleEntity

It has these properties which define the primary relationships between WEMI:
* related endeavor
  * expresses (range: Work)
  * manifests (range: Work or Expression)
  * instantiates (range: Work or Expression or Manifestation)

It does not include the FRBR Group2 or Group3 entities (responsible bodies and subjects). It does include the superclass Endeavor, which is not part of the FRBR group of entities but was added by the authors of FRBR core. 

## Files

* openWEMI.ttl (October, 2020) - this defines the WEMI classes as being sub-classes of "/Endeavor/". Endeavor encompasses the entire creation. Endeavor was introduced in [frbrCore](https://vocab.org/frbr/core). It also includes property "relatedEndeavor" from that vocabulary which is a general relationship between endeavors and "ResponsibleEntity", a general class to define the agent responsible for the creation. 
* cwo.rdf (January, 2022)- this defines the WEMI classes and their relationships but does not include "/Endeavor/" nor "ResponsibleEntity". The assumption is that the super-class level will be owl:Thing. It remains to be seen if it is desirable to include additional base classes, such as for ResponsibleEntity. It might be best to leave this as simple as possible at this time, allowing for discussion of the bare basics before taking on more elements. This file is in RDF/XML and primarily makes use of OWL encoding, but could obviously be converted to ttl and some aspects could be expressed in RDFS in place of OWL. 
