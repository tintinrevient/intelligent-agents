## RDF (Resource Description Framework)

### Install rdflib, rdflib-sqlite, sqlite3 modules in Python

```
pip3 install rdflib
pip3 install rdflib-sqlite

pip3 install sqlite3
```

### Parse RDF file

```
from rdflib.graph import ConjunctiveGraph

g = ConjunctiveGraph()
g.parse("data/wine.rdf")

for triple in g:
	print(triple)
```

### Save RDF in SQLite Database

```
import rdflib
from rdflib.graph import ConjunctiveGraph
from rdflib import Literal

store = rdflib.plugin.register('SQLite', rdflib.store.Store, 'rdflib_sqlite.SQLite', 'SQLite')
store = rdflib.plugin.get('SQLite', rdflib.store.Store)('test.ts')
store.open('test.ts', create=True)
g = ConjunctiveGraph(store)

me = rdflib.Namespace("http://self.com/people/")
foaf = rdflib.Namespace("http://xmlns.com/foaf/0.1/")
g.add((me["jamie"], foaf["name"], Literal("Jamie Taylor"))
g.add((me["jamie"], foaf["mbox"], Literal("jamie@me.com"))
g.serialize(format="nt")
g.commit()
```

### Query RDF in N3 format

```
from rdflib.graph import ConjunctiveGraph
from rdflib import Namespace

g = ConjunctiveGraph()
g.parse("data/wine.rdf")
g.serialize(format="n3")

results = g.query("""SELECT ?wine WHERE {?wine wine:hasBody wine:Medium. }""", initNs={'wine': Namespace("http://www.w3.org/TR/2003/PR-owl-guide-20031209/wine#")})

for triple in results:
	print(triple)

file = open("data/wine.n3", "wb")
file.write(g)
file.close()
```
