# Simple-Summarizing-tool-using-Python
The intersection function:  This function receives two sentences, and returns a score for the intersection between them. We just split each sentence into words/tokens, count how many common tokens we have, and then we normalize the result with the average length of the two sentences. Computer Science: f(s1, s2) = |{w | w in s1 and w in s2}| / ((|s1| + |s2|) / 2)   The sentences dictionary:  This part is actually the “Heart” of the algorithm. It receives our text as input, and calculates a score for each sentence. The calculations is composed of two steps:  In the first step we split the text into sentences, and store the intersection value between each two sentences in a matrix (two-dimensional array). So values[0][2] will hold the intersection score between sentence #1 and sentence #3. Computer Science: In fact, we just converted our text into a fully-connected weighted graph! Each sentence is a node in the graph and the two-dimensional array holds the weight of each edge!  In the second step we calculate an individual score for each sentence and store it in a key-value dictionary, where the sentence itself is the key and the value is the total score. We do that just by summing up all its intersections with the other sentences in the text (not including itself). Computer Science: We calculates the score for each node in our graph. We simply do that by summing all the edges that are connected to the node.  Building the summary:  Obviously, the final step of our algorithm is generating the final summary. We do that by splitting our text into paragraphs, and then we choose the best sentence from each paragraph according to our sentences dictionary. Computer Science: The Idea here is that every paragraph in the text represents some logical subset of our graph, so we just pick the most valuable node from each subset!
The intersection function:

This function receives two sentences, and returns a score for the intersection between them.
We just split each sentence into words/tokens, count how many common tokens we have, and then we normalize the result with the average length of the two sentences.
Computer Science: f(s1, s2) = |{w | w in s1 and w in s2}| / ((|s1| + |s2|) / 2)


The sentences dictionary:

This part is actually the “Heart” of the algorithm. It receives our text as input, and calculates a score for each sentence. The calculations is composed of two steps:

In the first step we split the text into sentences, and store the intersection value between each two sentences in a matrix (two-dimensional array). So values[0][2] will hold the intersection score between sentence #1 and sentence #3.
Computer Science: In fact, we just converted our text into a fully-connected weighted graph! Each sentence is a node in the graph and the two-dimensional array holds the weight of each edge!

In the second step we calculate an individual score for each sentence and store it in a key-value dictionary, where the sentence itself is the key and the value is the total score. We do that just by summing up all its intersections with the other sentences in the text (not including itself).
Computer Science: We calculates the score for each node in our graph. We simply do that by summing all the edges that are connected to the node.

Building the summary:

Obviously, the final step of our algorithm is generating the final summary. We do that by splitting our text into paragraphs, and then we choose the best sentence from each paragraph according to our sentences dictionary.
Computer Science: The Idea here is that every paragraph in the text represents some logical subset of our graph, so we just pick the most valuable node from each subset!


Reference :http://thetokenizer.com/2013/04/28/build-your-own-summary-tool/
