# On Biases of Attention in Scientific Discovery

This repository provides a reference data used in the paper:<br>
> On Biases of Attention in Scientific Discovery<br>
> Uriel Singer, Kira Radinsky and Eric Horvitz<br>
> Bioinformatics<br>

### Data
The protein interaction information used in the study was drawn from HitPredict [[1]](#1). HitPredict contains a list of all protein interactions, where each interaction includes a list of all published articles where it is mentioned.
We perform a preprocessing phase, where we filter to retrieve studies with homo sapiens and then identify the discovery date as publication date of the earliest associated article.
Once established, we create a topological graph that includes all interactions with their first publication dates. By using this method, we construct a graph that evolves over time.
Protein interactions with no associated articles are not included in the graph.
In the experiments, the PPI graph of year y includes all interactions among proteins that are confirmed by the end of year y.

### Columns
| Column            	| Explanation                                                                	|
|-------------------	|----------------------------------------------------------------------------	|
| Uniprot           	| Uniport ID of protein                                                      	|
| Name              	| Name of protain                                                            	|
| Entrez            	| Entrez ID of protein                                                       	|
| Ensembl           	| Ensembl ID of protein                                                      	|
| Taxonomy          	| Specie ID (9606 == Homo-sapiens)                                           	|
| Type              	| Interaction type                                                           	|
| Source_db         	| Which DB mentioned this interaction                                        	|
| Homologs          	| Number of homologs found for this interaction                              	|
| Method_score      	| Score based on the experimental information available for the interactions 	|
| Annotation_score  	| Score based on the likelihood ratio using naive Bayesian networks          	|
| Interaction_score 	| Confidence of existence of the interaction                                 	|
| Confidence        	| Confidence level                                                           	|
| pubmed_ids        	| List of all pubmed ids associated with the interaction                     	|
| publication_dates 	| Publication date of the pubmed papers (extracted using pubmed crawler)     	|
| discovery_date    	| The minumum publication date                                               	|

For further explainations you may visit [HitPredict](http://www.hitpredict.org/help.html)

### Citing
If you find this repository useful for your research, please consider citing the following paper:

	@inproceedings{biases-of-attention,
	  title     = {On Biases of Attention in Scientific Discovery},
	  author    = {Singer, Uriel and Radinsky, Kira and Horvitz, Eric},
	}


### References
<a id="1">[1]</a> 
López, Yosvany and Nakai, Kenta and Patil, Ashwini (2015). 
HitPredict version 4: comprehensive reliability scoring of physical protein--protein interactions from more than 100 species
Narnia, Database
