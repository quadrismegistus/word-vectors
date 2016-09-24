
# Word2Vec Models for Twenty-year Periods of 18C (ECCO, "Literature and Language")
Creator: Ryan Heuser (heuser@stanford.edu | @quadrismegistus)<br/>
License: GNU

=======

This is a zipped folder of five word2vec models. Each model was trained on a 150 million word sample from the "Literature and Language" subcorpus from Eighteenth-Century Collections Online (Gale). The five models correspond to the five twenty-year periods of the 18C: 1700-19, 1720-39, 1740-59, 1760-79, 1780-1799. 

Each period has two files: a gzipped word2vec model, saved in Google's word2vec format, which is readable by word2vec, gensim, and GloVe. The other is a plain text file of the form [word][space][count][newline]. Both files can be easily imported with gensim like this:

	import gensim
	
	# Load word2vec model in the form: load_word2vec_format([gzipped model filename], [vocabulary filename])
	model = gensim.models.Word2Vec.load_word2vec_format('word2vec.ECCO.1700-1719.skipgram_n=10.model.txt.gz', 'word2vec.ECCO.1700-1719.skipgram_n=10.model.vocab.txt')

	# Test an analogy: Man is to woman as king is to ____?
	print model.most_similar(['woman','king'], ['man'])
	
Test.
