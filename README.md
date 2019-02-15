# Named Entity Recognition and Linking over DBpediaQA Dataset

This work is as part of the Lab - Natural Language Processing at University of Bonn.

1. 'entity_extraction.py': Here SPARQL queries for DBpedia are written for getting the entity labels and the type of the entity 
and data preprocessing is done on the 'train.txt' file and extracted the entities. 

2. 'entity_extraction_model_to_train_File.py': In this file the extracted entities are trained by creating a model in spacy 
over the traindata.txt which is obtained after the data pre-processing. The trained model is stored and tested on testdata.txt .
Also I have trained the model over wikidata to increase the model performance.

3. 'model_evaluation.py': The trained model is evaluted both on the train and test datasets.

4. 'entity_linking.py': Once the entites are recognised, linking is done using the project EARL that is developed in the paper: 
Dubey, Mohnish & Banerjee, Debayan & Chaudhuri, Debanjan & Lehmann, Jens. (2018). EARL: Joint Entity and Relation Linking 
for Question Answering over Knowledge Graphs.

Example:

#Question: 
          ‘what movie is produced by Warner Bros’
#Model Output: 

Entities:[('Warner Bros', 'Company')]
Tokens[('what', '', 2), ('movie', '', 2), ('was', '', 2), ('produced', '', 2), ('by', '', 2), ('Warner', 'Company', 3), ('Bros', 'Company', 1)]

#Entity Linking Output:

Link Types : ['relation', 'entity', 'relation']
‘Word : Type’ =  [{'movie': 'relation', 'Warner Bros': 'entity', 'produced': 'relation'}]
