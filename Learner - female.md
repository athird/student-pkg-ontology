## WebID
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix schema: <http://schema.org/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix pim: <http://www.w3.org/ns/pim/space#> .

<https://id.somewhere.co.uk/melissa> a foaf:Agent ;
	pim:storage <https://pods.somewhere.co.uk/melissa> ;
	<http://www.w3.org/ns/solid/terms#oidcIssuer> <https://id.somewhere.co.uk/login> ;
	foaf:isPrimaryTopicOf <https://pods.somewhere.co.uk/melissa/profile> .

## private personal information, e.g., in pod-private:me
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix schema: <http://schema.org/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix pim: <http://www.w3.org/ns/pim/space#> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .
@prefix pkg: <http://cupa.example.org/pkg> .
@prefix pod: <https://pods.somewhere.co.uk/melissa/> .
@prefix pod-private: <https://pods.somewhere.co.uk/melissa/private/> .
@prefix me: <https://id.somewhere.co.uk/> .

me:melissa a foaf:Person ;
    foaf:name "Melissa Surname" ;
    foaf:depiction <http://id.somewhere.co.uk/melissa/me.jpg> ;
    foaf:address me:home .
    
me:home a vcard:VCard ;
        vcard:email <mailto:mel@somewhere.co.uk>;
        vcard:adr [
            a vcard:Home;
            vcard:country-name "United Kingdom" ;
            vcard:locality "Milton Keynes" ;
            vcard:postal-code "MK9" ;
            vcard:street-address "Campbell Park Gate"
        ] .

pkg:Plan foaf:page pod_private:tasklist .
pkg:Education 
    foaf:page pod:education ;
    foaf:page pod_private:education .

pkg:Health 
    foaf:page pod_private:health .

## pod_private:health 
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix schema: <https://schema.org/> .
@prefix icd10: <http://purl.bioontology.org/ontology/ICD10/> .
@prefix me: <https://id.somewhere.co.uk/> .

me:melissa schema:healthCondition [
    a schema:MedicalCondition ;
    schema:name "Attention Deficit Hyperactivity Disorder" ;
    schema:alternateName "ADHD" ;
    schema:code [
        schema:codeValue "F90.9" ;
        schema:codingSystem "ICD-10" ;
        rdfs:seeAlso icd10:F90.0 
    ] ;
    me:adhd_strats "Multitask",
                "Movement for Concentration" .
] .

## pod_private:education   
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix schema: <https://schema.org/> .
@prefix ou: <https://onlinenow.ac.uk/>
@prefix me: <https://id.somewhere.co.uk/> .

me:melissa schema:memberOf ou:OnlineNow ;
    schema:educationalEnrollment ou:MBA ;
    schema:educationalEnrollment ou:BZVM802 .
    foaf:project me:study_plan .   

## pod_private:tasklist
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix schema: <https://schema.org/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix ou: <https://onlinenow.ac.uk/> .
@prefix me: <https://id.somewhere.co.uk/> .

me:study_plan schema:PlanActions [
    a ScheduleAction ;
    schema:agent me:melissa ;
    schema:scheduledTime "Today" ;
    schema:location me:home ;
    schema:description "Revise units 3 & 4 for BZVM802" ;
    skos:relatedTo ou:BZVM802 .
]

## Tidy and move to institutional KG
ou:OnlineNow schema:offersCourse ou:MBA .
ou:MBA a schema:EducationalOccupationalProgram ;
        schema:courseName "Master of Business Administration" ;
        schema:offersCourse ou:BZVM802 [
            schema:courseCode "BZVM802" ;
            schema:name "Management of change: organisation development and design" 
        ] .

ou:OnlineNow foaf:name "OnlineNow University" .