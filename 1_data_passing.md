### Passing data between Kubeflow components

Writing code in components requires certain considerations that might not be obvious in your first attempts. [Link](https://jortizta.github.io/kubeflow-gcp/README.md)
Components are meant to be modular, isolated and reusable, they are executed independently in different containers. To transfer information between different components, at runtime, the Kubeflow backend converts any parameter in a serialized JSON that is passed through the command line to the receiving container. This means that passing parameters like strings or dictionaries is trivial but passing large objects – like a dataframe or a model – can only be done by first saving the object and then returning the object location in a shared storage.
