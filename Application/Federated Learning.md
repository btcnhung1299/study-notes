*Q: Explain Federated Learning (FL)*:
A: FL is a learning paradigm that allows a model to be trained across multiple decentralized device without direct access to the local data.

*Q: Describe a typical federated learning cycle*
A: In client-server architecture:
- Two entities involved: a coordinating server and the clients
- At the beginning of a communication round, the server will distribute parameters of a defined model to selected clients that are available for training
- The clients train them on their local dataset and then send them back to the server
- Then, the server performs aggregation of these updates using
- The procedure repeats until convergence 