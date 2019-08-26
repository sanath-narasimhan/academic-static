+++
+++
HTM is a hypothesis by Jeff Hawkins that explains the workings of the neocortex, the largest part of the brain and how it can be
implemented to build a truly intelligent system. There are about six layers in the human neocortex, highest in any mammal. The neurons
are arranged in a set of column vertically and are connected horizontally across a layer. The Temporal algorithm is the key component 
that uses Sparse Distributed Representation(SDR) of data and Spatial pooling concept. SDR are the main concept that allows us to actually 
implement the way our brain learns things, usually there are a lot of neurons in the brain but only about 2% are active at any given moment.
The core rule of learning is observing sequence of patterns and associating their occurrence over time. The input that reaches the 
neocortex activates very few neurons at every layer, hence the representation is called sparse, if you think of the input as a binary array
vector, with each bit representing a neuron being active(1) or passive(0). SDR is the main thing that differentiates HTm from other 
approaches towards AI. SDR is robust and fault tolerant and learns patterns quickly compared to the traditional approaches. Every input and
output from any layer of the neocortex is in SDR form, it is the means of communication within the neocortex.

Spatial pooling is observation of how the SDR change over time. This keeps track of all the seen sequence of patterns over time and is able
to tell if a new input sequence is similar to the sequences already observed. Observing and following the working to the neuron gives us an
idea of how SDR is used to predict the occurrence of patterns.Essentially these rules are applied at every level in the neocortex. A neuron
can be in three states, Active, Predictive, and Passive state. A neuron has proximal connections that are directly connected to a 
feed-forward input, distal dendritic connections giving it the context signals and distal dendritic axion connections that give  feedback
inputs. The connection between neurons occur through connections called synapsis. When a new pattern is observer, random neurons in a 
column are selected to represent the pattern. This is the active state of the neuron, when a feed-forward input causes it to fire. 
When an existing pattern is observed, the hierarchy recognises this and puts the neurons next in the sequence in a predictive state, 
depending on whether the prediction was right or wrong the connection to these neurons are strengthened or weakened respectively.
When the neuron is not associated with any sequence of patterns, it is in a passive state.
The hierarchy is not an absolute, but rather adds more abstraction to store an invariant representation the sequence of pattern. This is 
what allows the brain to actually understand variations of the same patterns represented by different sequences of neurons getting 
triggered.  


Reading materials:
https://numenta.com/resources/biological-and-machine-intelligence/
https://www.ncbi.nlm.nih.gov/pubmed/23354386
https://www.youtube.com/watch?v=6ufPpZDmPKA&t=22s
https://ti.arc.nasa.gov/m/events/hawkins/2013-09-17-nasa-jh.pdf
http://www.ldv.ei.tum.de/fileadmin/w00bfa/www/Vorlesungen/Brain_Mind_Cognition/A-On-Intelligence-v2.pdf
https://numenta.com/neuroscience-research/research-publications/papers/a-framework-for-intelligence-and-cortical-function-based-on-grid-cells-in-the-neocortex/
https://en.wikipedia.org/wiki/Grid_cell


