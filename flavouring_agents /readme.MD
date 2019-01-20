# Flavouring agents
## Schema
### Shape Expression (ShEx)
```
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX pr: <http://www.wikidata.org/prop/reference/>
PREFIX pq: <http://www.wikidata.org/prop/qualifier/>
PREFIX ps: <http://www.wikidata.org/prop/statement/>
PREFIX wdref: <http://www.wikidata.org/reference/>
PREFIX p: <http://www.wikidata.org/prop/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wikibase: <http://wikiba.se/ontology#>
PREFIX commons: <http://commons.wikimedia.org/wiki/Special:FilePath/>
PREFIX prov: <http://www.w3.org/ns/prov#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
start = @<#flavouring_agent>

<#flavouring_agent> {
    #statements
	p:P31 @<#P31_instance_of> ;
	p:P117 @<#P117_chemical_structure> ;
	p:P1582 @<#P1582_natural_product_of_taxon>+ ;
	p:P2849 @<#P2849_produced_by>+ ;

	#identifiers
	p:P662 @<#P662_PubChem_CID> ;
	p:P683 @<#P683_ChEBI> ;
}

<#P31_instance_of> {
	ps:P31 [wd:Q11173] ;
}

<#P117_chemical_structure> {
	ps:P117 [commons:~] ;
}

<#P1582_natural_product_of_taxon> {
	ps:P1582 @<#taxon> ;
	prov:wasDerivedFrom @<reference>+ ;
}

<#taxon> EXTRA wdt:P31 {
	wdt:P31 [wd:Q16521]
}

<#P2849_produced_by> {
	ps:P2849 [wd:~] ;
	pq:P2079 [
       wd:Q844704 # extraction
       wd:Q41760 # fermentation
       wd:Q580689 # bioengineering
	] ;
	prov:wasDerivedFrom @<reference>+ ;
}

<#P662_PubChem_CID> {
	ps:P662 xsd:string ;
}

<#P683_ChEBI> {
	ps:P683 xsd:string ;
}

<reference> {

}
```
[Try me on SimpleShEx ...](https://rawgit.com/shexSpec/shex.js/wikidata/doc/shex-simple.html?manifestURL=https://raw.githubusercontent.com/IC-FOODS/FoodShapes/master/flavouring_agents%20/manifest.json)



## SPARQL
### Flavouring agents and their roles
```
SELECT ?item ?itemLabel ?role ?roleLabel WHERE {
   ?item wdt:P2868 wd:Q60678340, ?role .
   SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```
[Try me...](http://tinyurl.com/ybpt5ru2)
