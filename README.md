# Synopsis Keyword Extraction
## Motivation
One day I was talking to a friend about how hard it is to find a good title: you should either read the whole synopsis or rely on not-so-useful tags that may be lacking or too abstract or too specific.
So I decided what if we could get some really meaningful tags from the text itself. 
 
## Approach
First we generate a list of possible keywords, finding all consistent phrases with a noun in it. Fortunately, spaCy has a fantastic dependency parser, so it is not a problem.
Next we should get the embeddings from the keyword candidates and the synopsis as a whole. Then we find the closest candidates to the synopsis in the embedding space and expect them to be our keywords.
 
Then I intend to cluster the resulting keywords so I can treat similar tags as a single token and compute the  TF-IDF for them, so I give less importance to keywords that are too widespread and don't help me in my search.
 
Thus, I expect to get keywords which are grammatically accurate, represent the synopsis text well enough and not too common to make them unusable for search.

