# Graphs
This repository explores some basic blind search algorithms on graphs, such as Breadth First Search and Depth First Search. 

It also analyzes the Bow-Tie structure characteristic of many graphs, as shown in the following research papers:
https://www.researchgate.net/publication/200111010_Mining_the_Inner_Structure_of_the_Web_Graph
http://snap.stanford.edu/class/cs224w-readings/broder00bowtie.pdf
http://cs.wellesley.edu/~pmetaxas/Why_Is_the_the_Web_a_Bowtie.pdf



The Bow-Tie structure of the Epinions social network was used, using the dataset made available by Stanford. 
https://snap.stanford.edu/data/soc-Epinions1.html



The following method was used to compute the components of the Web Graph was as follows: 
1) Compute SCC of epinions network

2) Run BFS on any randomly selected node from SCC. This gives us SCC+OUT. We can now use this to get total nodes in OUT.
OUT = (SCC+OUT)-SCC

3) Run BFS on any randomly selected node from SCC, on the graph’s complement. This gives us SCC+IN. We can now use this to get total nodes in IN. This is the same as running BFS on the in-links of the node.
IN = (SCC+IN)-SCC

4) Now make the graph bidirectional and compute weakly connected components

5) Running BFS/DFS on weakly connected components gives us the large connected structure in one traversed path, and disconnected nodes in the other traversed paths

TENDRILS+TUBES = CONNECTED - (SCC + OUT + IN)
6) DISCONNECTED = V - CONNECTED



The components of the epinions network given by this implementation are as follows:
SCC:32220
IN:24228
OUT:15455
TENDRIL+TUBES:3966
DISCONNECTED:19
