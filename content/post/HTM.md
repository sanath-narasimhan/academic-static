+++
title = "The quest for Artificial General Intelligence."
+++

<body>
In the recent years the quest for Artificial Intelligence has become wide spread and everyone is getting on the band wangon. 
The current state of AI, that is the deep Neural Networks, Reinforcement learning,and Machine Learning are pretty impressive intheir performance. But the question is Are they really intelligent? 
We now have to define and think about two concepts, Learning and intelligence. In my opinion Learning is the process of understanding how to execute a particular task, and Intelligence is the ability to associate different tasks. 
Intelligence can also be learned. This is what **Jeff Hawkins** discuss about in his boot **On Intelligence**. He argues that truly intelligent systems cannot be built without first understanding the working of a brain, specifically the Neocortex, outtermost part of the brain.
</body>
  
![On intelligence](/img/onin.jpg)

<h1>Heirarchical Temporal Memory (HTM)</h1>
<body>
**HTM** is a hypothesis that explains the workings of the **neocortex**, the largest part of the brain and how it can be implemented to build a truly intelligent system. The book dwells upon the idea of intelligence of the human brain and the true working of the neurons. The key is to understand the working of neurons in the outter most layer of the brain, the **Neocortex**. There are about **six columned layers** in the human neocortex, highest in any mammal. The neurons are arranged in a set of column vertically and are connected horizontally across a layer.
![On intelligence](/img/column.PNG)

![On intelligence](/img/Cross.PNG)

He proposes that the neocortex at its core is running a __**simple algorithm**__ at every level, from the neuron to the top of the six layers to recognize, process and remember patterns over time. This is the **Cortical Learning Algorithm(CLA)** also known as **Temporal Algorithm**. The Temporal algorithm has a key component that is the use of **Sparse Distributed Representation(SDR)** of data. SDR are what seperates this approach from its predecessors allowing us to actually implement learning the way our brain does, usually there are a lot of neurons in the brain but only about __**2%**__ are active at any given moment. This is the reason we choose a sparse representation of data giving us the advantage of storing data in a truly **invarient form**, making it easy to pick up and associate similar patterns and be able to differentiate between them **auto-associatively**. The core rule of learning is observing __**sequence of patterns**__ and __**associating their occurrence over time**__. The input that reaches the neocortex activates very few neurons at every layer, hence the representation is called sparse, if you think of the input as a binary array vector, with each bit representing a neuron being **active __(1)__** or **passive __(0)__**. 
![On intelligence](/img/SDR.PNG)

![On intelligence](/img/SDRP.PNG)

>**SDR is the main thing that differentiates HTM from other approaches towards AI. SDR is robust and fault tolerant and learns patterns quickly compared to the traditional approaches. Every input and output from any layer of the neocortex is in SDR form, it is the means of communication within the neocortex.**


**Spatial pooling** is observation of how the **SDR change over time**. This keeps track of __**all the seen sequence of patterns over time**__ and is able to tell __if a new input sequence is similar to the sequences already observed__. 

>**Observing and following the working to the neuron gives us an idea of how SDR is used to predict the occurrence of patterns.Essentially these rules are applied at every level in the neocortex.**

A neuron can be in **three states**, **Active**, **Predictive**, and **Passive** state. A neuron has __**proximal connections** that are directly connected to a feed-forward input, **distal dendritic connections** giving it the context signals and **distal dendritic axion connections** that give  feedbackinputs__. The connection between neurons occur through connections called **synapsis**. 
> * When a new pattern is observer, random neurons in a column are selected to represent the pattern. This is the active state of the neuron, when a feed-forward input causes it to fire. 
> * When an existing pattern is observed, the hierarchy recognises this and puts the neurons next in the sequence in a predictive state, depending on whether the prediction was right or wrong the connection to these neurons are strengthened or weakened respectively.
> * When the neuron is not associated with any sequence of patterns, it is in a passive state.
>**The hierarchy is not an absolute, but rather adds more abstraction to store an invariant representation the sequence of pattern. This is what allows the brain to actually understand variations of the same patterns represented by different sequences of neurons getting triggered**. 

![On intelligence](/img/Capture.PNG)
![On intelligence](/img/Capture2.PNG)
</body>

<h2> Now lets look at an example </h2>
![On intelligence](/img/Capture3.PNG)
![On intelligence](/img/Capture4.PNG)
![On intelligence](/img/Capture5.PNG)
![On intelligence](/img/Capture6.PNG)
Reading materials:
https://numenta.com/resources/biological-and-machine-intelligence/
https://www.ncbi.nlm.nih.gov/pubmed/23354386
https://www.youtube.com/watch?v=6ufPpZDmPKA&t=22s
https://ti.arc.nasa.gov/m/events/hawkins/2013-09-17-nasa-jh.pdf
http://www.ldv.ei.tum.de/fileadmin/w00bfa/www/Vorlesungen/Brain_Mind_Cognition/A-On-Intelligence-v2.pdf
https://numenta.com/neuroscience-research/research-publications/papers/a-framework-for-intelligence-and-cortical-function-based-on-grid-cells-in-the-neocortex/
https://en.wikipedia.org/wiki/Grid_cell


