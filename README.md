# Automated Identification of Food Substitutions Using Knowledge Graph Embeddings

This study presents an approach to find alternative food products with comparable or more favourable nutritional profiles that fall within a similar product category using knowledge graph embeddings to build a recommender system that suggests healthier substitutes for the ingredients and food products to its user. The knowledge graph of food is based on two open data sets, namely OpenFoodFacts, which is a food products database, and USDA, which provides nutritional information of food products. Furthermore, due to the low quality and unavailability of the existing ground truths, we curated an expert-verified data set for the evaluation of food substitution recommendations.

# Methodology

The first step was to construct knowledge graph data in RDF format and create semantically interlinked food knowledge by linking OpenFoodFacts and USDA. We used Limes to create relations between the food ingredients of USDA and OpenFoodFacts. Moreover, the KG was enriched by tagging the ingredients based on the nutritional content we calculated according to the U.S. FDA's Recommended Dietary Allowances (RDAs). The tags that indicate the presence of rich mineral or vitamin content were added to the knowledge graph. Each food was tagged as high in a nutrient if the level of that nutrient contained in the food per serving is more than 30% of its respective RDA.

In the second step, food substitution recommendations were extracted using the knowledge graph by applying different graph embedding approaches, namely, TransE, Complex and RDF2Vec. We applied TransE, Complex, and RDF2Vec models on 3 different subsets of the knowledge graph.

Finally, the quality of the KGEs were assessed against a newly created ground truth, which was verified by two domain experts and we evaluated the performance of the models by using Mean Reciprocal Rank (MRR), Mean Average Precision (MPA), and Recall Rate at k (RR@k).
