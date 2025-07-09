What we want (I think):
- Separation of concerns. In particular: there shouldn't be many places in code that a programmer concerned with changing a single aspect of functionality must change. (Ideally one)
- Un-opinionated-ness: A programmer who desires to use the pipe processor code in some external project shouldn't have to learn too many conventions. (Ideally three or less)

Theses:
- On the most basic level, a pipe ingestor/processor is a dependency graph of components
- There are two fundamental ways in which the data can flow through that graph in runtime proper: unidirectional and bidirectional
  * Unidirectional looks neat but introduces a lot of limitations
  * Bidirectional is just a pile of functions and should be executed with a regular stack

Suggestions/ideas:
- Components should map to NPM packages
- Recognize the three stages of program lifecycle: compile time, runtime initialization and runtime proper
- We may want to separate the layer that handles runtime dependencies from the layer that executes things in runtime proper
  * The latter might be just a loose collection of functions explicitly called in a certain way
  * The former will have to give up un-opinionated-ness by necessity
