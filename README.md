## wat-go
The Cloud Compute golang software development kit (sdk).

# Cloud Compute
Cloud Computeb (CC) is a framework that remotely runs a set of linked plugins. CC is a framework that provides structure to the declaration of attributes, inputs, and outputs for a software, facilitates the linking of those attributes, inputs, and outputs for a series of plugins, and distributes the computation of each plugin within the CC simulation.
A CC compute consists of a list of linked plugins represented by a directed acyclic graph (DAG) which defines the computational sequence of the plugins for a given event. CC also allows for multiple executions of that DAG by allowing the specification of many events to be computed. CC allows for events to be run in parallel as well as nodes within the DAG (as far as the DAG will allow) to be computed in parallel. 

# Plugins
A plugin is a central idea to CC. A plugin simply allows for an externally generated software package to be integrated into the framework. CC plugins take an input ModelPayload that defines the resolved paths to resources defined as inputs necessary for compute. A plugin typically is some process model which CC runs once all inputs have been generated by nodes above the plugin in the DAG. A plugin could be as simple as the generation of a set of random numbers for other plugins to consume, or as complex as a dynamic time-step coupled physics based watershed hydraulics model.

# Payload
A plugin computes off of a Payload. A Payload is defined by a dictionary of string and empty interface that describes a model for a plugin as well as a slice of DataSources that are inputs, and a slice of DataSources that are outputs. This is the structured way that CC can provide plugins information to compute within the framework.

# Software Development Kit
The software development kit (SDK) provides the essential data structures and a handful of utility services to provide the necessary consistency needed for a framework like CC. 