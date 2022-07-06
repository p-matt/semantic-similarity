# Semantics similarities - Natural Language Processing 
 Use case of NLP and word embedding that aims to detect and visualize potentials cluster from sentences.
___
# General approach
- Data mining  
  First thing first I required data, and I decided to focus on 3 main fields:
    - Statistics
    - Artificial intelligence
    - Computer science  
    
  Actually I achieved to scrap data from online glossaries thanks to Power BI.  
  For these 3 main fields I retrieved their proper labels and descriptions terms into pandas Dataframe, to finally concatenate them.  
  Necessarily this method induces significant bias because there are many ways to define terms, there must be majors likeness though.  
  
- Estimate sentence similarity  
  I separately used BERT and Spacy models to process words embedding and to compare from which one I can get better results.  
  When embedding is done I can compute sentences similarity through a cosines similarity between 2 vectors and set a "minimum similarity" threshold to define later non-connected nodes.  
  For each sentence I calculate the cosines similarity with all others sentences one by one.  
  Also make sure to store the data in an common structure ([adjacency matrix](data/adj_matrix.csv) for example).  

- Data visualisation  
  Since networkx is limited to display wide network interactively I also used Gephi tools.  
  Both tools detect 3 main clusters which logically are the same as original ones (orange cluster mostly include AI glossary terms, when purple and green respectively correspond to Computer Science and Statistics terms)
  Clusters are identified through the same method based on the [modularity](https://en.wikipedia.org/wiki/Louvain_method#Modularity_optimization).  


![Graph](data/graph.svg "Title")

![Graph2](data/network.png "Title")
