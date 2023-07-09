# Knowledge_Graphs

### Introduction

Knowledge graphs have emerged as powerful tools for representing and organizing complex information in a structured and interconnected manner. In this project, our objective is to provide a comprehensive demonstration of the structure, mapping procedure, and various tools employed in the creation of typical RDF files. It is assumed that you already possess a familiarity with concepts such as the semantic web, RDF files, and knowledge graphs.

### RDF Schema and Ontology

To ensure the effective utilization of RDF data, the first step is to establish a well-defined schema. RDF Schema (RDFS) serves as a data-modeling vocabulary for RDF data, providing a framework for describing the basic concepts and abstract syntax of RDF. It encompasses various concrete syntaxes for RDF, such as Turtle and JSON-LD. Moreover, RDFS extends its functionality by enabling the creation of ontologies. An ontology is a formal representation of knowledge within a specific domain, encompassing concepts, relationships, and rules. By employing ontologies, not only can we describe the structure of knowledge, but we can also introduce new insights into the domain. To facilitate the creation and editing of ontologies, tools like Protégé offer a customizable user interface and support for visualizing ontology relationships.

Within the project's 'onto' directory, a customized ontology based on the formal SOSA W3C standard ontology is provided. This modified version enhances the schema's classes and relations, adding value to the project's objectives. With the aid of tools like Protégé, the ontology can be manipulated and enriched to align with the specific requirements of the knowledge graph.The customized ontology based on the SOSA, empowers users to capture sensor data effectively while incorporating the necessary classes and relations.

### Mapping

For the mapping phase of the project, a language and engine are required. R2RML (RDB to RDF Mapping Language) serves as a language specifically designed to express customized mappings from relational databases to RDF datasets. It allows for the transformation of structured data stored in a relational database into RDF format. Another alternative is RML (RDF Mapping Language), which offers even greater flexibility by allowing mapping not only from relational databases but also from various other data formats such as CSV, Excel, and more. In the project's 'mapping' directory, you can find the mapper file in Turtle format, which describes the ontology based on the R2RML mapping language. An R2RML mapping involves defining logical tables, which can be base tables, views, or valid SQL queries, to retrieve data from the input database. Each logical table is then mapped to RDF using a triples map, which specifies how each row in the logical table is transformed into a set of RDF triples.

To execute the mapping process efficiently, the Morph-KGC engine comes into play. Morph-KGC is an engine that constructs RDF knowledge graphs from heterogeneous data sources, leveraging the power of the R2RML and RML mapping languages. It is built on top of the pandas library and incorporates mapping partitions to optimize execution times and memory consumption, particularly for large data sources. By running your mapper script with the Morph-KGC engine, you can generate RDF files that represent the transformed data according to the defined mappings. This combination of language and engine enables the seamless conversion of relational and other structured data into RDF, facilitating the creation of comprehensive and interconnected knowledge graphs.

### RDFLib and Oxigraph

RDFLib, a Python package dedicated to working with RDF, offers a comprehensive set of functionalities for RDF-related tasks. It encompasses various essential components, such as parsers and serializers, a Graph interface for handling RDF data, store implementations for storing RDF triples, and SPARQL function extension mechanisms. SPARQL is a query language for retrieving and manipulating data stored in RDF format, providing powerful capabilities for querying and analyzing RDF-based knowledge graphs.

In the context of knowledge graph construction, Morph-KGC serves as a valuable library that seamlessly integrates with RDFLib. This integration empowers developers to effortlessly create and manipulate knowledge graphs within their Python applications. By leveraging the capabilities of Morph-KGC and RDFLib together, developers can build and work with knowledge graphs efficiently, enabling advanced data representation and exploration.

### Storing

In the final step of the project, the data is stored in a database to ensure efficient management and retrieval. There are numerous databases available for this purpose, and for this particular project, Neo4j was chosen. Neo4j is an open-source, NoSQL graph database that has gained popularity since its release in 2007. It provides a robust and transactional backend for applications, ensuring the integrity and consistency of the stored data.

To leverage the capabilities of Neo4j for storing RDF triples, the project utilized the Neosemantics (n10s) plugin. This plugin enables the seamless integration of RDF and its associated vocabularies such as OWL, RDFS, SKOS, and others into the Neo4j database. Using Neosemantics, the project extracted the triples from the RDF file and transformed them into a graph structure within the database.

With the data now stored in the graph database, the power of Cypher comes into play. Cypher is a graph query language specifically designed for Neo4j, inheriting its structure from SPARQL. It allows for efficient and expressive querying of the graph database, enabling the retrieval of desired data based on complex patterns and relationships. By leveraging Cypher, the project was able to retrieve relevant information and insights from the graph database, further enhancing the analysis and exploration of the stored data.

