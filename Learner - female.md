Learner - female
        - adhd
        - career goals
        - study goals 

study goals - [
    desired_skills : esco skill 
    desired_occupation_field : 
]

career goals = esco occupation

medical condition - [

]

@prefix icd10: <http://purl.bioontology.org/ontology/ICD10/> .

pkgf:adhd owl:sameAs icd10:F90.0 .
 

From ESCO 

<!-- http://data.europa.eu/esco/model#Occupation -->

    <owl:Class rdf:about="http://data.europa.eu/esco/model#Occupation">
        <rdfs:subClassOf rdf:resource="http://data.europa.eu/esco/model#MemberConcept"/>
        <owl:disjointWith rdf:resource="http://data.europa.eu/esco/model#Qualification"/>
        <owl:disjointWith rdf:resource="http://data.europa.eu/esco/model#Skill"/>
        <terms:issued rdf:datatype="http://www.w3.org/2001/XMLSchema#date">2013-06-27</terms:issued>
        <terms:modified rdf:datatype="http://www.w3.org/2001/XMLSchema#date">2017-02-10</terms:modified>
        <rdfs:comment xml:lang="en">The class of ESCO Occupation concepts. An Occuaption is an ESCO pillar concept (see http://data.europa.eu/esco/model#MemberConcept).

<!-- http://data.europa.eu/esco/model#Skill -->

    <owl:Class rdf:about="http://data.europa.eu/esco/model#Skill">
        <rdfs:subClassOf rdf:resource="http://data.europa.eu/esco/model#MemberConcept"/>
        <terms:issued rdf:datatype="http://www.w3.org/2001/XMLSchema#date">2013-06-27</terms:issued>
        <terms:modified rdf:datatype="http://www.w3.org/2001/XMLSchema#date">2013-12-03</terms:modified>
        <rdfs:comment xml:lang="en">The class of ESCO Skill concepts.

ESCO skills are sub-typed (e.g. to differentiate between knowledge and competence).
This sub-typing is modelled using the concept class http://data.europa.eu/esco/model#SkillCompetenceType

Concept class for organization is http://data.europa.eu/esco/model#SkillReuseLevel
ESCO skills with a different re-use applicability across sectors can be put in a hierarchical relation (skos:broader and skos:narrower) in acordance with the rules detailed by http://data.europa.eu/esco/model#SkillReuseLevel.

Characteristics
- An ESCO skill sub-type is given by http://data.europa.eu/esco/model#skillType
- An ESCO skill re-use level is given by http://data.europa.eu/esco/model#skillReuseLevel

An ESCO Skill may be related to other ESCO concepts.
- Essential related concepts of class esco:Skills are indicated by http://data.europa.eu/esco/model#isEssentialSkillFor and http://data.europa.eu/esco/model#relatedEssentialSkill
- Optional related concepts of class esco:Skills are indicated http://data.europa.eu/esco/model#isOptionalSkillFor and http://data.europa.eu/esco/model#relatedOptionalSkill
- Occupations a skill is essential for are concepts of type esco:Occupation indicated by http://data.europa.eu/esco/model#isEssentialSkillFor
- Occupations a skill is optional for are concepts of type esco:Occupation indicated by http://data.europa.eu/esco/model#isEssentialSkillFor
The property http://data.europa.eu/esco/model#hasRelationship details the relationships (see http://data.europa.eu/esco/model#Relationship)</rdfs:comment>
        <rdfs:isDefinedBy rdf:resource="http://data.europa.eu/esco/model"/>
        <rdfs:label xml:lang="en">Skill</rdfs:label>
        <rdfs:seeAlso rdf:resource="http://data.europa.eu/esco/model#Qualification"/>
        <rdfs:seeAlso rdf:resource="http://data.europa.eu/esco/model#SkillReuseLevel"/>
        <rdfs:seeAlso rdf:resource="http://data.europa.eu/esco/model#skillType"/>
        <skos:definition xml:lang="en">A skill may also be an informal recognition of a competence.
The recognition typically is obtained by experience, practice or informal tests.</skos:definition>
        <skos:historyNote xml:lang="en">2013-06-27:
A Skill that is a MemberConcept:
- Initially (i.e. ESCOv0) coming from the Swedisch PES Skills tab in file Taxonomy 3 - Taxonomy db DB 20 l-corr.xls.
- Initially (i.e. ESCOv0) linked as related concepts to leaf occupation groups as described in ISCO_SKILLS.xls.
A Skill that is a GroupConcept:
- Is created by ESCO</skos:historyNote>
    </owl:Class>

       <!-- http://data.europa.eu/esco/model#hasAccreditation -->

    <owl:ObjectProperty rdf:about="http://data.europa.eu/esco/model#hasAccreditation">
        <rdfs:domain rdf:resource="http://data.europa.eu/esco/model#Qualification"/>
        <rdfs:range rdf:resource="http://data.europa.eu/esco/model#Accreditation"/>
        <rdfs:comment xml:lang="en"></rdfs:comment>
        <rdfs:isDefinedBy rdf:resource="http://data.europa.eu/esco/model"/>
        <rdfs:label xml:lang="en">has accreditation</rdfs:label>
        <rdfs:seeAlso rdf:resource="http://data.europa.eu/esco/model#Accreditation"/>
        <owl:deprecated rdf:datatype="http://www.w3.org/2001/XMLSchema#boolean">true</owl:deprecated>
    </owl:ObjectProperty>

    <!-- http://data.europa.eu/esco/model#Qualification -->

    <owl:Class rdf:about="http://data.europa.eu/esco/model#Qualification">
        <rdfs:subClassOf rdf:resource="http://www.w3.org/2004/02/skos/core#Concept"/>
        <rdfs:subClassOf rdf:resource="http://www.w3.org/2004/02/skos/core#MemberConcept"/>
        <rdfs:comment xml:lang="en">A qualification is a formal outcome of an assessment and validation process, which is obtained when a competent body determines that an individual has achieved learning outcomes to given standards.</rdfs:comment>
        <rdfs:comment xml:lang="en">List of properties on a qualification defined by the QMS application profile:
	- adms:identifier (1..n)
	- esco:referenceLanguage (0..n)
	- skos:prefLabel (1..n)
	- skos:altLabel (0..n)
	- skos:definition (0..n)
	- dcterms:description (1..n)
	- esco:hasISCED-FCode (1..n)
	- esco:hasAssociation (0..n)
	- esco:hasECTSCreditPoints (0..1)
	- esco:volumeOfLearning (0..1)
	- esco:isPartialQualification (0..1)
	- esco:waysToAcquire (0..n)
	- esco:expiryPeriod (0..n)
	- esco:hasRecognition (0..n)
	- esco:hasAwardingActivity (0..n)
	- esco:hasAccreditation (0..n)
	- foaf:homepage (0..n)
	- dcat:landingPage (0..n)
	- esco:supplementaryDoc (0..n)
	- dcterms:issued (1..1)
	- dcterms:modified (1..1)
	- skos:changeNote (0..1)
	- skos:historyNote (0..1)
	- esco:additionalNote (0..n)
	- dcterms:replaces  (0..n)
	- dcterms:isReplacedBy  (0..n)
	- iso-thes:status (0..1)
	- dcterms:creator (0..1)
	- dcterms:rightsHolder (0..1)
	- dcterms:publisher (1..1)</rdfs:comment>
        <rdfs:isDefinedBy rdf:resource="http://data.europa.eu/esco/model"/>
        <rdfs:label xml:lang="en">Qualification</rdfs:label>
        <owl:deprecated rdf:datatype="http://www.w3.org/2001/XMLSchema#boolean">true</owl:deprecated>
    </owl:Class>