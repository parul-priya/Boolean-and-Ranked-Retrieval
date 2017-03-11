# Boolean-and-Ranked-Retrieval
Boolean retrieval(wiki : https://en.wikipedia.org/wiki/Standard_Boolean_model) works on matching the given query  with each of our documents and finding the EXACT matches.

If you know exactly what you ar looking for, then boolean retrieval can result in fast and efficient searches.

But there are certain issues also with this algorithm.
For example, there is no ranking of resulting pages
The user has to know about how to form proper queries
Even a single typo can result in either no results or completely different results.

Solution?????

Of course there is one!
The vector space model! (wiki : https://en.wikipedia.org/wiki/Vector_space_model)

Idea : Represent each term in your vocabulary as a different axis in space.
Obviously there would be thousands of axes for even a small set of data, so we will be dealing with multi - dimensionality.
Sounds fancy right, but the concept is pretty easy.

Use the term frequency of a term in a given document to calculate its length along that axix, do this for all the distict terms occuring in the document and voila! you document vector is ready!

Now how to find matches???
Well using the similar process, we can have our query vector, the next step is to somehow calculate the similarity between our query and each of the documents. For this we need to associate some sort of query dependent score with each of our documents in order to rank them.

Which score??
The COSINE!
It is actually easier to visualize it for now.Two documents which are similar to each other should also be closer to each other in the vocabulary space we just created, right(as they have very similar words)?
And what's a better way to measure closeness than the angle between the two vectors!
But we must normalize the vectors here if we want to compare them, without normalization the comparison makes no sense, since the length of the document vectors are very different from each other. So normalize them, i.e consider their unit vectors and do the same for your query vector. 
And just do the DOT product to find the cosine score for each normalized query-doc pair.
Finally we can rank them according to their cosine scores. The one having the highest score will be the most similar  to the query.

You can check out the implementation in Python in this repository.
Thanks for reading!
                   
