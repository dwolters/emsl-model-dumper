# Dumping eMSL Models
This project allows dumping NeoCore models stored in a Neo4j database as textual eMSL models.
eMSL is a textual transformation and (meta)modelling language.
NeoCore allows to describe metamodels are Neo4j graphs. 
It follows the structure of [ECore](https://eclipse.dev/modeling/emf/).
NeoCore and eMSL are used by the graph transformation engine [eMoflon::Neo](https://github.com/eMoflon/emoflon-neo).

```sh
git clone https://github.com/dwolters/emsl-model-dumper.git
npm install
```

Copy [`example.json`](config/example.json) to the folder [`config`](config/) and add the details for your Neo4j database.

To dump the models in the database to the standard output run:

```sh
node dump
```

It will by dump all models contained in the database.
It queries the NeoCore metamodel to automatically identify attributes that are not specified by the metamodel.
Those attributes use a `~` instead of a `.` before the attribute name in the eMSL model.
It also checks the data type in the metamodel to identify enum values.