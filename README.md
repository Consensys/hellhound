
# Hellhound
HellHound is a **decentralized blind computation** platform.

## Escape game at DevCon 4

[![Hellhound](http://img.youtube.com/vi/mztQHrRXEXs/0.jpg)](http://www.youtube.com/watch?v=mztQHrRXEXs)

### Proof of concept.
#### Introduction

The Hellhound platform is divided in multiple components and designed as a microservices architecture. First of all, hellhound components are splitted in two major categories : **on-chain** and **off-chain**.

The on-chain category include all components related and running directly into the blockchain. The backing blockchain used is Ethereum thanks to the capability of building turing complete programs. It allow us to develop smart contracts to handle some critical parts of the systems. Basically on-chain smart contracts are used when we need transparency or the immutability intrinsic characteristic of the blockchain. We also use smart contracts to register computation proofs.

The off-chain category is designed as a Software As A Service platform including multiple microservices. This platform was designed to be scalable and highly available.

We use Kubernetes as the orchestrator of deployments. Kubernetes is defined as a Production-Grade Container Orchestration and it is a system for automating deployment, scaling, and management of containerized applications.

In order to have a highly available environment for the DevCon event, we have set a Kubernetes cluster on top of Google Kubernetes Engine platform.

The proof of concept was implemented to follow best practices and guidelines about microservices architecture. The main objective is to show team skills and to prove our capability to build a scalable and robust platform. We aim to target millions of users, that is why we have set such an architecture.

#### Architecture overview

![hellhound_architecture_overview](/Users/abdelhamid/Documents/GitHub/ext/hellhound/hellhound_architecture_overview.png)

#### Demo story

The purpose of the demo is to show how to use a decentralized blind computation platform to execute a service for the end user. We will describe the use case example and the related story presented during the showcase.

Some of the components were mocked or simplified for demonstration. For example instead of having a true decentralized peer to peer protocol between nodes, a centralized message broker is used to handle events and communication.

The message broker used for the Demo is NATS. The core principles underlying NATS are performance, scalability, and ease-of-use.

Here are the components implemented in the Demo PoC :

-   **Pythia** : Simplified recommendation engine

-   **Iris** : Authentication service

-   **Immersion & Retention** : Authentication Smart Contracts

-   **10 cerberus nodes** : 8 genuine and 2 **malicious** nodes

-   **Light cerberus** : UI/UX to interact with the platform




Pythia role is to recommend the best cryptosystem to the user for a specific computation. The scope of the Demo was reduced to only one cryptosystem : Paillier. Paillier is a homomorphic encryption scheme where you can perform the following operations on encrypted data :

-   Add 2 ciphers

-   Add 1 cipher and 1 constant

-   Multiply 1 cipher by 1 constant




The user is the only entity that can decrypt the result and retrieve it exactly as it was performed on plain data. It show the magical power of homomorphic encryption through a simple use case.



Iris role is to perform an off chain authentication using one classical authentication provider and OAuth protocol to generate a token that can therefore be used to authenticate to the blockchain using the offchain whitelist mechanism. In the Demo the user can authenticate using her Gitlab account.



In order to use the service, the user need to perform the staking operation. We wanted to show that Hellhound can interact with other blockchain related services like Fuel. Fuel enable to use meta transaction and can be considered as a gas provider for the end user. It allows to do the staking mechanism with a simple debit card payment using Stripe API. This is an easy to use way to encourage people to go to the blockchain ecosystem without having deep knowledge or understanding of the ecosystem.



Once authenticated to the blockchain with smart contract call to generate the authentication token, the end user can define the computation she wants to execute on the Hellhound platform. This operation consists in uploading a Hellhound byte code script that combines the 3 Paillier operations.

We perform the encryption on the client side prior to send data to the message broker.

Then we have the selection process that will randomly choose the desired number of nodes to perform the computation. Since it is not multi party computation, we offer the possibility to select multiple nodes for the computation. We can at the end of the computation perform a basic consensus algorithm to detect if some nodes are malicious.

In the demo, 2 nodes are malicious and always give false results for any computation. The demo shows that we can easily detect them if they are selected because they will provide different results that genuine nodes. So if the end user choose 5 nodes for the computation, the selection algorithm will select at least 3 genuine nodes.

We have intentionally slowed down the Virtual Machine instruction execution to have a graphical representation of the overall computation that can be understand by a human. The end user is able to see the live status of the computation because each individual instruction execution is traced in the system using the message broker.

Once the computation is done, the light client perform the decryption of the result and retrieve the plain output. Magical.
