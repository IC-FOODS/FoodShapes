## Wikidata captures different types of Milk

The following query currently returns what is in Wikidata
```sparql
 SELECT ?mamalian_milk ?mamalian_milkLabel ?species ?speciesLabel WHERE {
   ?mamalian_milk p:P279  ?milk .
   ?milk ps:P279 wd:Q8495 ;
         pq:P642 ?species .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```
[Try me...](http://tinyurl.com/y9e4w2me)

A first Shape Expression to harmonize the data on the different mammalian milk items in Wikidata, has been made. 
```rdf
BASE <https://raw.githubusercontent.com/IC-FOODS/FoodShapes/master/milk_shape/wd_milk.shex>
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
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

start = @<#mammalian_milk>

<#mammalian_milk> {
	#statements 
	p:P279     @<#P279_subclass_of> ; 
	p:P1582    @<#P1582_natural_product_of_taxon> ;

	#identifiers
	p:P244     @<#P244_Library_of_Congress_authority_ID>? ;
	p:P268     @<#P268_BnF_ID>? ;
	p:P349     @<#P349_NDL_Auth_ID>? ;
	p:P1051    @<#P1051_PSH_ID>? ;
	p:P1748    @<#P1748_NCI_thesaurus_ID>? ;
	p:P1978    @<#P1978_USDA_NDB_number>* ;
	p:P2892  @<#P2892_UMLS_CUI>? ;
	p:P4637  @<#P4637_FoodEx2_code> ;
} 

<#P279_subclass_of> {
	ps:P279 	[wd:Q8495] ;
	pq:P642     @<#mamallian> ;
}

<#P1582_natural_product_of_taxon> {
	ps:P1582    @<#mamallian> ;
}

<#mamallian> {
	wdt:P31  [wd:Q16521] ;
}

<#P244_Library_of_Congress_authority_ID> {
	ps:P244  xsd:string ;
}

<#P268_BnF_ID> {
	ps:P268  xsd:string ;
}
<#P349_NDL_Auth_ID> {
	ps:P349  xsd:string ;
}
<#P1051_PSH_ID> {
	ps:P1051  xsd:string ;
}
<#P1748_NCI_thesaurus_ID> {
	ps:P1748  xsd:string ;
}

<#P1978_USDA_NDB_number> {
	ps:P1978  xsd:string ;
}
<#P2892_UMLS_CUI> {
	ps:P2892  xsd:string ;
}

<#P4637_FoodEx2_code> {
	ps:P4637  xsd:string ;
}
```

Currently there are only two milk items that adhere to this schema description. See: [ShEx validation](https://rawgit.com/shexSpec/shex.js/wikidata/doc/shex-simple.html?manifestURL=https://raw.githubusercontent.com/IC-FOODS/FoodShapes/master/milk_shape/manifest.json) 

## Future work
* We need to find public data on different types of mammalian milk, to enrich wikidata with knowledge on milk
* Extend the Shape expressions to cover more data. Currently, all identifiers are made optional since it still is unknown which identifier schemes cover all types of milk. 

