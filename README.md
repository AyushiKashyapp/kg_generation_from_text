# Knowledge Graph Generation From Text
A project to extract triples and generate knowledge graphs for short text, long test, single web news article and a list of web news articles.

A project to implement a pipeline for extracting a Knowledge Base from texts or online articles.

Find the project question bank here [QuestionBank](https://github.com/AyushiKashyapp/kg_generation_from_text/blob/main/QuestionBank.md)

Building a Knowledge Graph from text using following steps:

1. Extract entities, Named Entity Recognition (NER), to represent the nodes of the graph.
2. Extract relations between entities, Relation Classification (RC), to represent the edges of the graph.

These steps will be implemented in an end-to-end model called REBEL (Relation Extraction By End-to-end Language generation).
REBEL is a text2text model trained by BabelSpace by fine-tuning BART for translating a raw input sentence containing entities and implicit relations into a set of triples that explicitly refer to those relations.

# Steps to implement the Knowledge Graph Extraction Pipeline.

1. Load the Relation Extraction REBEL model.
2. Extract a knowledge base from short text.
3. Extract a knowledge base from large text.
4. Filter and normalize entities.
5. Extract a knowledge base from an article at a specific URL.
6. Extract a knowledge base from multiple URLs.
7. Visualize knowldege bases.
