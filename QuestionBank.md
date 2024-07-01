# Project Question Bank

1. **Explain the main objective of the project on building a knowledge graph from text?**
The main objective of my project is to implement a pipeline for extracting a knowledge base from unstructured texts or online articles. This involves using Named Entity Recognition (NER) to identify entities and Relation Classification (RC) to identify relationships between these entities. The extracted entities and relationships form the nodes and edges of the knowledge graph, respectively.

2. **What is REBEL, and how does it contribute to the project?**
REBEL (Relation Extraction By End-to-end Language generation) is an end-to-end model fine-tuned from BART by BabelSpace. It translates raw input sentences containing entities and implicit relations into explicit triples that denote these relationships. REBEL is a text2text model that plays a crucial role in my project by extracting entities and their relationships from the text, which are then used to build the knowledge graph.

3. **What are the key steps in the knowledge graph extraction pipeline?**
The key steps in the knowledge graph extraction pipeline are:
1. **Loading the Relation Extraction REBEL model:** This involves initializing the pre-trained REBEL model and tokenizer.
2. **Extracting a knowledge base from short text:** Using REBEL to extract relations from short text segments.
3. **Extracting a knowledge base from long text:** Dividing long text into overlapping spans and extracting relations from each span.
4. **Filtering and normalizing entities:** Using Wikipedia to validate and normalize entities to ensure consistency.
5. **Extracting a knowledge base from a specific URL:** Parsing articles from URLs and extracting relations.
6. **Extracting a knowledge base from multiple URLs:** Aggregating knowledge bases from multiple articles.
7. **Visualizing knowledge bases:** Using pyvis to visualize the resulting knowledge graph.

4. **How to handle the extraction of relations from short text?**
 To extract relations from short text, I first tokenize the input text and use the REBEL model to generate potential relations. The generated output is then parsed to identify relation triples, which include the head (subject), type (relation), and tail (object). These triples are stored in a knowledge base object.

5. **Describe the process for handling longer texts in the project?**
For longer texts, I split the input text into overlapping spans of 128 tokens each to ensure coverage. Each span is processed independently to extract relations using the REBEL model. The extracted relations include metadata indicating the span boundaries. These relations are then aggregated into a single knowledge base, ensuring that relations identified in multiple spans are merged appropriately.

6. **What role does Wikipedia play in the project, and how to use it?**
Wikipedia is used for entity linking and normalization. After extracting entities from the text, I use the Wikipedia API to check if these entities have corresponding Wikipedia pages. If they do, I normalize the entities to the titles of their Wikipedia pages and store additional information such as the URL and summary. This ensures that the same entities are consistently represented across the knowledge graph.

7. **How to extract a knowledge base from web articles?**
To extract a knowledge base from web articles, I use the newspaper library to download and parse articles from URLs. The extracted text, along with the article's title and publish date, is then processed using the REBEL model to extract relations. These relations, along with metadata about their source, are added to the knowledge base.

8. **How to handle the extraction of knowledge bases from multiple articles?**
For multiple articles, I extract a separate knowledge base from each article and then merge them into a single knowledge base. This involves aggregating entities and relations from each article while ensuring that duplicate entities are normalized and relations from different articles are appropriately tracked and merged.

9. **Explain the visualization part of the project**
For visualization, I use the pyvis library to create interactive visualizations of the knowledge graph. This helps in representing the entities and their relationships in a graphical format, making it easier to analyze and understand the structure of the extracted knowledge base.

10. **What challenges faced during this project, and how to overcome them?**
One of the main challenges was ensuring the accuracy and consistency of the extracted entities and relations. This was addressed by using Wikipedia for entity validation and normalization. Another challenge was handling long texts, which was overcome by splitting the text into manageable spans and aggregating the extracted relations. Additionally, ensuring that the knowledge base correctly merges information from multiple sources required careful handling of metadata and relation merging logic.
