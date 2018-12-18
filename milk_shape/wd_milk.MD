## Wikidata captures different types of Milk

The following query currently returns what is in Wikidata

 SELECT ?mamalian_milk ?mamalian_milkLabel ?species ?speciesLabel WHERE {
   ?mamalian_milk p:P279  ?milk .
   ?milk ps:P279 wd:Q8495 ;
         pq:P642 ?species .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
