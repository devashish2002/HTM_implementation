#(Under maintainance)

# HTM_implementation

The core idea of the project is to design an appropriate model for the prediction of a body
activity from the readings of three gyro sensors fitted on the body with the help of Hierarchical
Temporal Memory (HTM) algorithms. Unlike most other machine learning methods, HTM learns
time-based patterns in unlabeled data on a continuous basis and is thus able to give online predictions.

HTM network is a tree-shaped hierarchy of levels that are composed of smaller elements called
nodes or columns. A single level in the hierarchy is also called a region. Higher hierarchy levels
often have fewer nodes and therefore less spatial resolvability. Higher hierarchy levels can
reuse patterns learned at the lower levels by combining them to memorize more complex
patterns. In learning and inference modes, sensory data comes into the bottom level nodes. In
generation mode, the bottom level nodes output the generated pattern of a given category.

![screenshot from 2017-11-05 12-25-41](https://user-images.githubusercontent.com/24549241/32412884-ef702d88-c22a-11e7-8742-7403e4a9dd23.png)

# About Nupic
The Numenta Platform for Intelligent Computing (NuPIC) is a machine intelligence platform
that implements the HTM learning algorithms. NuPIC is suited to a variety of problems,
particularly anomaly detection and prediction of streaming data sources. It provides interfaces
for Python and C++.
For usage guides, quick starts, and API documentation, see http://nupic.docs.numenta.org/.

# Different steps of model
## SDR
An SDR consists of thousands of bits where at any point in time a small percentage of the bits
are 1’s and the rest are 0’s. The bits in an SDR correspond to neurons in the brain, a 1 being a
relatively active neuron and a 0 being a relatively inactive neuron. The most important property
of SDRs is that each bit has meaning. Therefore, the set of active bits in any particular
representation encodes the set of semantic attributes of what is being represented. If two SDRs have active bits in the same locations, they share the semantic attributes represented by those bits.

![screenshot from 2017-11-01 17-51-01](https://user-images.githubusercontent.com/24549241/32412885-f353fcfe-c22a-11e7-99bb-6427e0aeefee.png)

## Spatial pooling
The most fundamental function of the spatial pooler is to convert a region’s input into a sparse
pattern. This function is important because the mechanism used to learn sequences and make
predictions requires starting with sparse distributed patterns.

![screenshot from 2017-11-01 18-18-41](https://user-images.githubusercontent.com/24549241/32412887-f54682fc-c22a-11e7-8b40-ffd4a8ed5fb6.png)

## Temporal Pooling
The temporal pooler learns sequences and makes predictions. The basic method is that when a
cell becomes active, it forms connections to other cells that were active just prior. Cells can
then predict when they will become active by looking at their connections. If all the cells do
this, collectively they can store and recall sequences, and they can predict what is likely to
happen next.

![screenshot from 2017-11-01 18-24-20](https://user-images.githubusercontent.com/24549241/32412889-f76c6c86-c22a-11e7-8674-c0bb6f2348c4.png)

# Dataset
The dataset we worked on consisted of the X, Y and Z readings of the respective gyro sensors
fitted on a body and the position of the body corresponding to these values.
