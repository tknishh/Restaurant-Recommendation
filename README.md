# Submission for NLP Intern

## Abstract

After going through the task the first thing that I did was to analyze the task thoroughly and break it up into sub tasks. Going through the attached video gave me a clear picture of the practical application of this given task.

## Approach

### Generating Tags
* After scrapping the data I created a Preprocessor function that removes the punctuation and stops words from the text and makes the data ready for further processing.
* After trying various approaches to vectorize the text, I tried using Word2Vec, GloVe, FastText and several others and observed TFIDF was performing better and working fine with the current data. 
* Used TFIDF transformer for features extraction from the data which will give attention to important words in a given text.
* The code can extract 'n' number of tags from the text according to the user's choice and save it into a file.

### Text similarity score
* Build the term dictionary, TF-idf model. 
* Used gensim module to make a api call to load **Glove Wiki gigaword-50** which gave **similarity index** by comparing with our dicttionary
* Using similarity index, dictionary and tfidf I created the term similarity matrix.
* I used **SoftCosineSimilarity** which provides score of similarity between tags

### Suggesting tags
* After generating tags from data I used them as an input to generate score for tag similarity for a set of tags.
* To suggest most relevant tags from the set of tags I calculated individual tag similarity between them.
* This approach of checking tag similarity twice for already high score set of tags resulted into suggestion of better and more relevant tags. 


## Testing
Used auto scrapper to scrape the data attached with the task because no API was available. After thorough testing, I concluded that the model was performing efficiently, and the desired results were obtained, which were tags similar to the actual text provided by the author. Testing results were approximately 60 %, which was pretty good for the base model.




### Instructions
`run Tagger.ipynb`  which generate tags
`run multiple_tag_similarity.ipynb` which calculates tag similarity and suggest relevant tags to user.
