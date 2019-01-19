# Flavouring agents
## Schema

## SPARQL
### Flavouring agents and their roles
```
SELECT ?item ?itemLabel ?role ?roleLabel WHERE {
   ?item wdt:P2868 wd:Q60678340, ?role .
   SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```
[Try me...](http://tinyurl.com/ybpt5ru2)
