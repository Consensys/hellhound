# HellHound - Black Paper
## Mission statement document

### Authors</br>
**[Amira Bouguera, co-founder](https://www.linkedin.com/in/amira-bouguera-282025a6/)** (MS Applied Mathematics, MS Cryptography and Security)</br>
**[Sajida Zouarhi, co-founder](https://www.linkedin.com/in/sajidazouarhi/)** (MS Engineering, Computer Science researcher)


<div align="center"> <a data-flickr-embed="true" href="https://www.flickr.com/photos/185058771@N07/48920282966/in/dateposted-public/" title="HH_logo_black-1"><img src="https://live.staticflickr.com/65535/48920282966_ebf52d5c60.jpg" width="500" height="333" alt="HH_logo_black-1"></a></div> 
<div align="center">PRIVACY BY DESIGN FOR ALL (D)APPS</div>
</br>
</br>
</br>

*“If you want to keep a secret, you must also hide it from yourself.”*</br>
**― George Orwell, 1984**
</br>
</br>


# Table of contents

[Abstract](#asbtract) </br>
1. [Introduction](#introduction) </br>
    1.2. [A decentralized environment for trusted computation](#decentralized) </br>
    1.3. [Privacy by design for dApps, now!](#privacy) </br>
    1.4. [State of the art - Actors of the Data Computation Ecosystem](#stateoftheart) </br>
    1.5. [Why a Software-based approach?](#softwarebased) </br>
   
2. [Introducing the HellHound project](#hellhound) </br>
    2.1. [HellHound Triptych △    ](#triptych) </br>
    2.2. [HellHound Architecture Overview](#architecture) </br>
    2.3. [Pythia - Recommendation Engine](#pythia) </br>
    2.4. [HellHound nodes](#nodes) </br>
    2.5. [HOWL](#howl) </br>
    2.6. [Cerberus -  Light client for the user](#cerberusclient) </br>
    2.7. [Styx - Smart Contracts suite](#styx) </br>
3. [How to use HellHound](#usehh) </br>
    3.1. [Deployment on Hellhound](#deployhh) </br>
    3.2. [Cryptosystems](#cryptosystems) </br>
    3.3. [Verification of computation on HellHound](#verification) </br>
4. [HellHound Use cases](#usecases) </br>
    4.1. [Key custody - key management](#keycustody) </br>
    4.2. [DNA sequence searching](#dna) </br>
    4.3. [Salaries - analytics without disclosing salaries](#analytics) </br>
    4.4. [Kidner - matching algorithm](#matching) </br>
    4.5. [Voting](#voting) </br>
    4.6. [Quantum safe approaches](#quantum) </br>
5. [Economical model](#model) </br>
    5.2. [Business model](#businessmodel) </br>
    5.3. [Incentivization system](#incentivization) </br>
    5.4. [Node incentivization](#nodeincentivization) </br>
    5.5. [Decentralized reward delivery mechanism](#reward) </br>
    5.6. [Cerberus incentivization](#subreward) </br>
6. [HellHound attacks resistance](#attacks) </br>
7. [Roadmap](#roadmap) </br>
8. [Join us in the HellHound journey](#joinus) </br>
9. [Conclusion](#conclusion) </br>
10. [Acknowledgments](#acknowledgments) </br>
11. [References](#references) </br>



## Abstract <a name="abstract"></a>


**HellHound is a decentralized blind computation platform.**

Blind computation is a process by which a function (or circuit) is successfully applied on encrypted inputs to provide the expected output. This output, depending on the use case, can be encrypted as well or it can be a plain text. 
It is called a “Blind” computation since no one, except the data provider, know the actual data being computed. </br>
HellHound’s goal is to provide a truly decentralized computing environment and a set of cryptographic tools to enable dapps developers to implement privacy-by-design. </br>
Cryptography has been around for a long time and is used in several industries to secure exchanges and protect data. It has however often been out of reach for developers with no computer science or mathematical background. </br>
The reality is that not all developers need these scientific backgrounds to build their great applications or services. Unfortunately for their users, implementing security and privacy takes time and skills which most early stage startups don't have. We also believe that blockchain startups of today might be the big players of tomorrow's web 3.0. </br>
We think that by making the developer’s tasks easier, more startups and companies will adopt best practices in terms of privacy and foster the emergence of self-sovereignty for their users. We also strongly believe that providing a blind and verifiable computation platform, without the need of having an omniscient third part in the process, will unlock a large pool of untapped opportunities. </br>
We have a chance at rebuilding the internet, so as Richard Branson put it "let's not screw it, let's just do it". </br></br>


## Introduction <a name="introduction"></a>

  ### Privacy by design for dApps, now!  <a name="privacy"></a>

What is Privacy?</br>

**<div align="center">The right to be let alone</div>**

In 1890 (future U.S. Supreme Court Justices) Samuel Warren and Louis Brandeis defined privacy as the right to “personal autonomy, freedom of association, moments of reserve, solitude, intimacy, and independence”. (1)
</br>

More than a century later, we now have another term, “informational privacy,” which means that all information about a person is in a fundamental way her own, for her to communicate or retain as she sees fit.
</br>
We consider privacy to revolve around control, use and disclosure of one’s personally identifiable information.</br>
Privacy is the cornerstone of many rights and freedoms that are important to us, and will always be a vital component of free and democratic societies. 
</br>
However, our increasingly technologically-driven world puts great pressure on privacy. This is why designing an information technology (a system, a service, an application) without taking into account Privacy from the very beginning is dangerous and hostile to freedom.
</br></br>

*The Facebook/Cambridge Analytica example*</br>

Facebook exposed data on up to 87 million Facebook users to a researcher who worked at Cambridge Analytica, which worked for the Trump campaign.
This amount of data was harvested through a Facebook app (a quiz). </br>
It not only collected data from people who took the quiz but exploited a loophole in Facebook API that allowed it to collect data from the Facebook friends of the quiz takers as well. Facebook prohibited the selling of data collected with this method, but Cambridge Analytica sold the data anyway.
</br>
Privacy by design could have helped avoid such thing to happen at different stage of the process (data were sold, data were used but the intent wasn’t disclosed to the users, data of friends of the user were used without consent etc.)
The Facebook/Cambridge Analytica scandal suggests that the EU has made the right choice to propose and carry out the GDPR (General Data Protection Regulation).
Applied since 25th May 2018, this regulation will bring several improvements to deal with data protection violations in the future.</br>


*Privacy by Design*</br>

Privacy by design is an approach to systems engineering initially developed by Dr Ann Cavoukian. The privacy by design framework was published in 2009 and adopted by the International Assembly of Privacy Commissioners and Data Protection Authorities in 2010. Privacy by design calls for privacy to be taken into account throughout the whole engineering process. 
The European GDPR (General Data Protection Regulation) incorporates Privacy by Design. </br>
Business processes that handle personal data need to be designed and built in alignment with principles such as pseudonymization, full anonymization when appropriate, highest-possible privacy settings by default. Data is not available publicly without explicit, informed consent, and cannot be used to identify a subject without additional information stored separately. The data subject has the right to revoke this consent at any time.
</br>

  ### A decentralized environment for trusted computation <a name="decentralized"></a>
  
Throughout history, technological advances have tremendously expanded trust through innovations such as the internet, secure e-commerce, social networks, exchange platforms for services etc. 
Each of these innovations requires some trusted parties to engage together.  </br> However, these parties can be hacked, compromised or even dishonest. Blockchain technology has the potential to revolutionize the digital world by enabling a distributed consensus where each and every online transaction, past and present, involving digital assets, is trustless, practically immutable, and can be verified at any time in the future.
Ethereum blockchain offers more than peer-to-peer digital assets transfer. It has the capacity to perform any complex computation using fully trustless, quasi turing-complete smart contracts.
Despite the great potential Ethereum has to offer, it still suffers from two major issues: </br>
- **Scalability**: Ethereum is not scalable due to the fact that every node in the network needs to process every transaction, validate it and store a copy of the entire state. The number of transactions Ethereum can process cannot exceed that of a single node which is currently 15 transactions per second due to the gas limit. Also transaction processing and verification speed is low to execute on any type of computation whether simple arithmetic or heavy computation.
- **Privacy**:  Information is published unencrypted to the public ledger and does not have any restrictions on access permission since everyone is able to read and process it. 
</br> </br>

There have been multiple solutions proposed to treat both of these problems such as sharding and off-chain computation. Both of these solutions intend to create a second layer of computation in order to reduce the load on the Ethereum network. Off-chain computing allows data to be processed off-chain and not published on the mainnet. However, the main issues for users are security and privacy since they interact with untrusted parties. 
How to guarantee data confidentiality while being be able to perform any sort of computation on it? How to provide sound proofs that a computation was done correctly? 
These are the main scientific challenges tackled by HellHound.</br> </br>

HellHound will enable an off-chain network of nodes to execute various types of computation over encrypted data and verifies the integrity of these calculations using different cryptographic tools.   
</br>


  ### State of the art - Actors of the Data Computation Ecosystem <a name="stateoftheart"></a>
  
Outsourced computation allows users with low computation power to delegate the heavy computation tasks to large data centers with more computation power. This delegation saves time and money for users while relying on a managed service platform. Ethereum blockchain suffers from scalability issues because smart contracts cannot perform large computation on-chain. The reason why smart contracts are constrained is the GasLimit, which is used to ensure the computation is bounded and it’s a countermeasure for DOS attacks. Another issue is that the same computation are run by all the nodes of the network which is not optimized. Nor is it necessary if the trust in the computation doesn’t rely on having a majority of honest nodes which is a requirement for most Blockchain protocols. Last but not least, we mention one of the biggest bottlenecks for scalability “Verifier’s Dilemma”. In Proof of Work models, miners get rewarded by solving a cryptographic puzzle. In order to solve this puzzle, miners spend computation power and verify the integrity of the transactions committed to the blockchain. The problem with this mechanism is that miners are not incentivized to participate in the verification process when they have a computational intensive transactions. This could allow a bad actor to compromise the integrity of the network by publishing invalid transactions. Another outcome could be that a bad actor would mislead miners to try and verify intensive transactions and exhaust their computational resources while it is mining the new blocks in the network.
 </br>
In order to solve these scalability issues, several actors in the space have started developing off-chain solutions where they do all heavy computation off-chain and commit only results back on-chain. However, this raises two problems:
- **Data privacy**: is data being shared publicly with those untrusted actors? </br>
- **Verified computation**: how do we guarantee that those actors were honest and delivered back correct results? </br> </br>

We will mention here some of the well-known actors in the blockchain space working on solving the problems of scalability, privacy and verification. 
IExec, Enigma, Golem and Truebit are developing solutions to do off-chain computation in exchange for rewards. Most of them use hardware approaches (i.e secure enclaves) for this role and provide verification using different methods which will be discussed in the next paragraph.
On IExec, worker nodes use secure enclaves to conduct computation over data in plaintext (non-encrypted) and submit their results back to the user.
The user then compares the different results she receives and will accept only one based on the likelihood threshold between results using Sarmenta’s voting mechanism (2). This validation method relies on the fact that multiple nodes of the network will do the same computation task and send back their responses. If kout of n, (k<n) number of results matches, then the result will be accepted and considered to be valid. This method however is easily attacked as it does not conduct an actual verification of the result correctness which leaves the risk of colluded malicious workers sending false results. Also, our research has shown that the hardware approach IExec is taking for computation is vulnerable to attacks (more on this in the following section).
Golem is using another verification approach called “probabilistic verification". (3) </br>
This verification method only calculates a fraction of the task, if this fraction is verified as correct then the system accepts the full result. The problem we see with this method is that for some stateful-dependent use cases such as 3D rendering (i.e. the use case that Golem is approaching), verifying a fraction of the task will not be enough to conclude whether the computation was done correctly or not. 
TrueBit, on the other hand does not verify computation unless a dispute is raised about the integrity of a calculation by a worker. Dispute resolution occurs as an on-chain verification game where miners are the judges between a challenger and a solver (both are workers). The verification will only be done on the targeted part of the dispute but the workers needs to narrow it down by search through the merkle hash root of computation results (4). 
This raises the following question: if any worker can raise a dispute, a malicious worker can launch a DOS attack on (or at least waste computation resources of) the network. The network of workers will spend time trying to solve the disputes which means searching through the merkle hash roots for several rounds. To mitigate this issue, Truebit uses staking with slashing conditions so that if a verifier triggers a false dispute to spam the network for example, the verifier loses its stake - if not, it is returned to the verifier.
However this ultimately doesn’t prove correctness of the whole computation since incorrect results can stay unverified. </br>

All of the previous mentioned solutions focus on solving the scalability problem and not the data privacy challenge.  </br>

Enigma is working on solving privacy issues (5). To do so, they partnered with Intel to use their SGX enclaves for computation over private data (6).
In the next section we will see that hardware approaches like Intel SGX are not enough to guarantee privacy preserving computation. In some cases, they can even leak sensitive data to attackers.
 </br>
 
The following table compares the different approaches: </br> </br>


| Decentralized Cloud computing projects | TrueBit              | Enigma              | Golem                | Iexec               | HellHound      |
|----------------------------------------|----------------------|---------------------|----------------------|---------------------|----------------|
| Privacy Approach                       | Software based       | Hardware based      | Hardware based       | Hardware based      | Software based |
| Decentralized computing                | Yes                  | Yes                 | Yes                  | Yes                 | Yes            |
| Verifiable computing                   | Yes (1)              | No                  | Yes (2)              | Yes (3)             | Yes            |
| Recommendation engine                  | No                   | No                  | No                   | No                  | Yes            |
| Blind computation                      | No                   | No                  | No                   | No                  | Yes            |
| Decryption side                        | No use of encryption | Server (inside SGX) | No use of encryption | Server (inside SGX) | Client side    |


*Fig **X**. Overview of the actors our our ecosystem* </br>
(1) Challenge a computation by taking it to a court (miners are the judges) and there are a challenger and a solver. If the challenger questions the integrity of computation, the solver will be forced to play a verification game </br>
(2) There is a portion of computed value to be verified </br>
(3) The accepted result must reach the expected likelihood threshold of votes to reach consensus </br>

There are other projects working on solving both privacy and scalability problems like Monero(7), Zcash (8) and Starkware (9).  </br>
The previous mentioned projects rely on advanced zero knowledge verifiable computing techniques like Bulletproofs (10), ZKSnarks (11) and ZKStarks (12).  </br>
These techniques allow a prover to convince a verifier about a certain claim by only sharing a proof which backs up the prover’s claim without sharing any private information. 
These sort of techniques are usually used to send confidential transactions, where the transaction amount is hidden from public view in the blockchain. By including a zero-knowledge proof of validity in each of these transactions, network validators or miners can still verify transaction integrity without reading its amount. </br> 
 </br>


The following table compares the previous techniques in terms of complexity, the need for a trusted setup and interactivity: </br>

| Protocol     | Prover time  | Verification time | Proof size                          | Trusted setup | Interactivity | Quantum resistance |
|--------------|--------------|-------------------|-------------------------------------|---------------|---------------|--------------------|
| ZKSnarks     | Quasi-linear | Logarithmic       | *                                   | Yes           | No            | No                 |
| BulletProofs | Linear       | Linear            | Scales linearly with computing time | No            | No            | No                 |
| ZKStarks     | Quasi-linear | Poly-logarithmic  | *                                   | No            | No            | Yes                |



- **Trusted setup**: It is a process performed by a trusted party or parties to generate a pair of keys to be used by the prover and verifier later on to generate and verify proofs. 
The trusted party uses a random secret as a seed to generate the key pairs, this seed is destroyed afterwards. </br>
The challenges regarding this process are as follow:</br>
  1. Possibility to generate false proofs if prover gets access to the secret seed or if the trusted party is malicious.</br>
  2. Not scalable: The trusted setup scales linearly with the computing time in ZKSnarks.  This is way, the key and proof generation are done only once off-chain. </br>
- **Quantum resistance**: ZKSnarks and Bulletproofs are not quantum resistant which means the security assumption behind each of these protocols could be broken eventually by quantum computers (see the quantum resistance section for more details).</br>
- **Interactivity**: Prover and verifier exchange messages (challenges and responses) so that the verifier checks the validity of a certain proof sent by the prover. All the previous mentioned protocols can be made non-interactive by replacing the communicated messages by cryptographic random functions.</br>
- **Performance**: ZKStarks is the most scalable solution between all of them and Starkware is currently using it as a scalability solution while Zcash for example is focusing more on the privacy aspect.</br>


  ### Why a Software-based approach?  <a name="softwarebased"></a>

We will define here both software and hardware approaches and their concepts. Then we will compare them in terms of privacy vulnerability to determine the best approach to consider.
</br>

**Software: Homomorphic Encryption (HE) / Multiparty Computation (MPC)** </br>

Software based approaches leverage the usage of cryptographic algorithms such as HE and MPC while doing computation over data. </br>
- **Homomorphic Encryption** methods allow calculation and search to be made over encrypted data without the need to decrypt it. </br>
- **Multiparty computation** methods allow data to be split between multiple servers, where each of these servers apply computation on the data share they have. Data might not be encrypted but then will be unreadable unless there is a collusion between servers above a certain threshold. 
More explanation about these protocols in the cryptosystems section.</br>


**Hardware: Secure Enclaves** </br>

Secure enclaves are hardware components which allow an isolated execution of code and data in an untrusted environment while protecting the areas of execution in memory. The access to application memory is restricted by hardware and remains secure even if the OS kernel is being hacked.  
</br>
There are different technologies that provide secure enclaves solutions such as Intel SGX, AMD Secure Encrypted Virtualization, IBM SecureBlue++ .etc. In this paper, we will mostly focus our comparison on Software Extension or “Intel SGX” Trusted Execution Environments.


**Why Hardware approaches can be dangerous?** </br>
Different decentralized cloud services such as Enigma and IExec have partnered with Intel to use Hardware solutions like Intel SGX in order to execute computation over sensitive data. In this computation context, data should be protected from any type of modification or access. However, most of Intel Hardware chips have been found to be vulnerable to some attacks (Meltdown, Spectre (13) and Foreshadow (14). 
</br>

The first two attacks (Meltdown, Spectre) allow an attacker to access private data by misleading speculative scouts into a speculative execution attack. Speculative scouts’ original mission is to improve performance by guessing values to complete future tasks. Compared to other Intel Hardware chips, the SGX is resilient to speculative attacks as it uses a security mechanism called Abort Page Semantics which denies writing attempts and always returns the same value for reading attempts from outside the enclave.
</br>
Unfortunately, SGX are vulnerable to another type of attack called Foreshadow. This vulnerability enables an attacker to create a shadow copy of the protected data into a different unprotected location. Then the speculative attacks are redirected to this new location and can now read the entire SGX enclave’s memory content.  
</br>
Another reason why hardware approaches are not privacy preserving is that data is encrypted on the client side with the public key of the server (which is an untrusted party), instead of being encrypted with the client public key. This system requires data within the enclave to be decrypted before being processed. If an attacker manage to access the enclave, it will then be easy to recover plain text data.
</br>
We will show in the following paragraph why it is considered to be a disadvantage.</br>


**Client vs Server side encryption** </br>
Data encryption is a very essential security measure when dealing with untrusted servers to perform computation over users’ sensitive information.

There are two types of encryption depending on who owns the private key to decrypt data, whether it is the client or the server. 
</br>
- **Homomorphic Encryption** 
Homomorphic encryption allows data to be encrypted using the user’s public key on the client side. Encrypted data is then sent to the server where computation will be performed. This method guarantees data privacy since information will never be disclosed to untrusted third parties, including HellHound nodes.
- **Memory Encryption** 
With a secure enclave, data is encrypted using the enclave’s public key, decrypted when it is inside the enclave and computation happens on plaintext data.
Then a Memory Encryption Engine (15) is used to encrypt data on the way out of the enclave. This method represents a risk for privacy. With attacks like Spectre, Meltdown and Foreshadow, attackers will be able to access the sensitive data stored in the enclave and since it will not be encrypted, they will be able to both read and modify it. These attacks don’t leave a trace, which means the client might never know it happened. 
</br>

Both methods have their advantages and disadvantages, server side encryption will allow faster computation process than client side encryption but it does not protect data confidentiality nor integrity. 
In this project, we leverage software cryptographic approaches to tackle privacy issues.</br>
Our commitment is that we will never decrypt user’s data.</br>


    
## Introducing the HellHound project   <a name="hellhound"></a>

  ### HellHound Triptych △    <a name="triptych"></a>


HellHound is a modular platform that provides 3 main components which constitutes the pillars of our triptych:</br>
1. a **recommendation engine** based on an expert system used for helping the user in her decision-making process on which cryptosystem to use;</br>
2. a **blind computation platform** enabling privacy as a decentralized service (PAADS) and verifiable computation;</br>
3. a **framework composed of verified crypto libraries** that will be in the future integrated with the favourite tools of dApp developers.</br></br>

Each one of these components can be used independently.


**Recommendation engine**  </br>
One of the three main components of HellHound is the recommendation engine, Pythia.</br>
Pythia’s role is to help the user select the best cryptosystem for her use case.</br>
Depending on which inputs her dApp is processing and what computation she is seeking, the user is able to tap into the expert curated knowledge database of Pythia.</br>
Pythia is a bridge between the user world and the HellHound world. It doesn’t require any advanced mathematical or cryptographical knowledge.</br>
There is a challenge in terms of ontology creation and search algorithm to provide the best recommendation. Our main challenge for Pythia will be the design of a user-friendly UX to make it simple to interact with.</br>
*To learn more about the Recommendation engine, see - Pythia section for more detail.*</br></br>

**Privacy as a decentralized service (PaaDS)**  </br>
The core of the HellHound platform is the network of HellHound nodes. It can be viewed as a sidechain that aims to extend the current functionalities of the Ethereum main chain regarding privacy and scalability for heavy computation tasks.
This network of nodes communicates using the HOWL protocol (see section about HOWL for more details).</br>
Their goal is to perform computation in a (truly) decentralized fashion.</br>
Computation is not always duplicated on the different nodes; each HellHound node can work on a different set of instructions. HellHound nodes are not all mobilized for each computation, they work in a cluster (or “pack”).
</br>
“Privacy as a decentralized service” conveys the idea that any user (developer, company) can leverage our system without having to deploy a dedicated infrastructure.
We added the term “decentralized” to highlight the fact that this service is not owned by a central authority (e.g. HellHound).
This platform can be used by anyone to interact with the Hellhound nodes using tokens. </br>
HellHound Tokens are part of the delivery mechanism for nodes’ reward. Each HellHound node receives upon completion of its task an amount of tokens that is calculated based on the heaviness of the computation it just performed. We will not discuss a Token model in this paper but the idea is pretty straight forward if we compare it to Ethereum computation formula.
</br></br>
Our client is named Cerberus. Cerberus will provide a UI enabling the user to monitor any deployed services and to manage her token balance.
It can be accessed on a web app or it can run on the user’s desktop as a light-client depending on the features embedded (e.g. key management).
</br></br>
HellHound platform provides a suite of smart contracts known as the STYX. Their main role is to anchor the critical elements (proofs) that the user, the hellhound nodes, or anyone else, might need to prove a computation.
The STYX also manages the reward distribution in a decentralized manner as well as the deposits (staking) needed in the platform. We provide a decentralized reputation system that will also be anchored in the STYX to express the current reputation of the HellHound nodes (16).
</br>
*To learn more about the HellHound nodes, Cerberus, Styx and the Howl protocol, see the respective sections.*</br></br>


**Framework and libraries**  </br>

Our goal is to make the task of implementing privacy by design as easy as possible for developers.</br>
This is why we are going to propose open source libraries and smart contracts for the community.</br>
Developers will be able to use them to start implementing privacy by design in their dApps.</br>
We are discussing with other projects in the blockchain space the possibility to integrate general purpose HellHound smart contracts in their development frameworks.</br>
We also plan to release Cryptographic Libraries that other protocols or projects can use safely. Developers of traditional Apps or dApps will be able to leverage this list of certified crypto libraries in their architecture with no technical overhead.
</br></br>

*Making available to the community verified cryptographic libraries*</br>

Cryptographic libraries are used as tools to implement security and privacy measures into applications. The fact that application developers rely on these libraries brings the need to make sure that they are not vulnerable and exploitable by hackers.  In the last few years, many widely used libraries have suffered from critical flaws.
</br>For example, the OpenSSL library has suffered from different types of bugs affecting the TLS protocol layer, such as the HeartBleed attack (17), as well CacheBleed vulnerability (18) which was a side channel attack against RSA implementation and many others over the years. 
</br>The Libsnark library used to implement ZK-SNARKS protocol has also suffered from a vulnerability affecting the soundness property of the protocol (19). This bug allowed the protocol’s implementation in libsnark to accept false proofs, such a vulnerability could have affected the whole verification system Zcash is based on.
</br>
In order to find bugs in the cryptographic code, there have been different methods used like testing, fuzzing, formal verification etc. Formal verification proves or disprove mathematically the correctness of a protocol implementation as a whole.
</br>
We aim to provide a curated registry of verified secure cryptographic libraries to the community in order to minimize the exposure of dApps to these types of attacks. This work will be done by HellHound in collaboration with researchers from the Formal Verification space.
</br></br>


  ### HellHound Architecture Overview   <a name="architecture"></a>
  ### Pythia - Recommendation Engine   <a name="pythia"></a>
  
  Our approach for the Pythia Recommendation Engine is to model an ontology that will:</br>
- contain the logic and knowledge needed by the recommendation engine.</br>
- provide a construction algorithm that will create combinations under constraint by finding a path in the graph.</br>
- compute the corresponding QoS (quality of service).</br>
- create an answer for the UI component of Cerberus for an intuitive visualization of the results.</br></br>

The recommendation engine is constituted of two main components :</br>
- database containing rules and facts (ontology, graph)</br>
- combination algorithm for the decision making</br>
</br>
The knowledge database contains the current state of the art for HE, SMPC and VC (verified computation). It also contains the logic rules based on criterias explained in the CryptoMap (a document we are working on that we will release for the community).
</br>
Based on that, Pythia decides which CryptoSystems, Settings to select in order to match the Client request with the best QoS possible. 

    **Query**
The user fills the form presented on the interface of our website. Her query is sent to Pythia to be analyzed.

Pythia takes these parameters as input.
Using the knowledge database and the decision algorithm, recommendation of CryptoSystems are generated. This step is always free and can be done by the user as many times as she wants.

    **Analyze**
In this step, we assume that the user has an algorithm ready and wants to use Hellhound to run it, following the recommendation Pythia just provided. The user needs to stake to access the following step.
Once done, the user will send her algorithm code on the platform for analysis. 
Cost computation is estimated in order to determine the price of the computation that the user will have to pay (hellhound nodes reward). 

    **Validate**
If the user agrees on the price, the HellHound nodes selection starts (see HellHound node selection for more information). A pack is formed.
The user, through her client Cerberus, sends a transaction of “initialization” to the blockchain with the cost of the computation (the Styx will keep it safe in an escrow and will only pay the HH nodes involved after completion of their task).
This will also trigger the deployment of the virtual machines (or containers) on the selected HellHound nodes. The Pack is ready to start. The next step will be to use Cerberus to encrypt locally the user’s data and then send it directly to the selected HellHound Nodes.

    **The Service is deployed on HellHound**
Each HellHound node runs a virtual machine, just like the EVM on Ethereum.
Using a dockerized approach, each new cryptosystem (previously selected by Pythia and approved by the user) will trigger the creation of new containers embedding the cryptographic set up needed for computation and ready to receive the information.
After a computation is completed and all proofs are saved, the HH node can destroy its containers and move on to the next job in its queue.



  ### HellHound nodes <a name="nodes"></a>

**Cerberus client and the Howl protocol** </br>

Cerberus client and HellHound nodes have in common these components: </br>
- they have a Virtual machine, </br>
- they maintain a Local storage (file system, reputation matrix), </br>
- they use the HOWL protocol to communicate. </br>

Any user can download a Cerberus client for free. They can use it as such (to perform computation on HellHound) or they can become a HellHound node. Being certified as a HellHound node requires going through a vetting process.
Installing Cerberus isn’t needed to interact with Pythia. She will be available online as a free service. However installing Cerberus is required if the user select a multi-party computation approach, Cerberus becomes one of the parties involved in the computation alongside HellHound nodes. This is why a Cerberus client and a HellHound client have so much in common.
 </br> </br>
Main attributes of Cerberus Clients or HellHound nodes: </br>
- Available memory </br>
- Available processing power </br>
- Geographical location </br>
- Reputation matrix </br> </br>


One needs a certified client to become a HellHound node. Certification is delivered upon completion of the *Purgatory* vetting process.
 </br>

| Features                | Cerberus | HellHound |
|-------------------------|----------|-----------|
| Local storage           | yes      | yes       |
| Computation power       | yes      | yes       |
| Reputation matrix       | yes      | yes       |
| Certificate             | no       | yes       |
| Human Interface         | yes      | no        |
| HOWL protocol           | yes      | yes       |


</br>
All HellHound clients (Cerberus, HellHound nodes) share the same communication protocol: the **HOWL**.</br>
The HOWL protocol defines all communications happening between cerberus nodes from the authentication of a new client (Cerberus trying to connect to the HellHound platform) to the P2P auditing mechanisms between HellHound nodes (see Howl’s decentralized reputation system).
</br>


**HH Node Purgatory** </br>

Only nodes who have successfully completed Purgatory (vetting process) can register to become a HellHound. </br>
Nodes which want to join the network as dedicated computing resources will apply on-chain to the STYX contract. This application mechanism allows Hellhound  to have a permanent transparent record of the participating nodes. 
 </br>
Purgatory steps: </br>

Requirements: computing power, resources, legal commitment, SLA etc. </br>
    - **Private key storage**: the private key of each node must be protected and stay safe (e.g. in a cold storage such as Ledger). </br>
    - **Identity verification**: The STYX contract will verify the identity of each node on the public blockchain with some information related to the node owner IRL since the participation is not anonymous and there is a legal framework around this participation. </br>
    - **Staking**: Each node which want to join the network as a computing service must put an amount of HellHound tokens at stake. Doing so can be made easy since HellHound accepts other cryptocurrency and even fiat, but everything is converted to HH tokens in the Smart contract.   </br>The stake is a way for the nodes to prove their commitment and to make sure they act honestly during computation/verification rounds. The security deposit will be locked in an escrow smart contract. The value of the security deposit will be set according to the risk parameters of the node (unfriendly legal framework in the country of the node will increase the stake). It also depend if the node wants to run very heavy computations (more costly so more lucrative), if yes the stake will be higher (more to gain if honest, more to lose if not). </br>
    - **Confirmation**: After all requirements are verified and the nodes submit their stake, HellHound contract will confirm their registration to the network both legally and on-chain. </br>

**HH Node Selection** </br>
**HellHound Node participation** </br>


  ### HOWL   <a name="howl"></a>
  ### Cerberus -  Light client for the user   <a name="cerberusclient"></a>
  ### Styx - Smart Contracts suite <a name="styx"></a>
  
## How to use HellHound <a name="usehh"></a> </br>

  ### Deployment on Hellhound <a name="deployhh"></a> 
  ### Cryptosystems <a name="cryptosystems"></a>
**MPC - multi party computation** </br>
**HE - homomorphic encryption** </br>
**ZKP - zero knowledge proof** </br>
  
  ### Verification of computation on HellHound  <a name="verification"></a>
  
## HellHound Use cases  <a name="usecases"></a>

  ### Key custody - key management <a name="keycustody"></a>
  ### DNA sequence searching <a name="dna"></a>
  ### Salaries - analytics without disclosing salaries <a name="analytics"></a>
  ### Kidner - matching algorithm    <a name="matching"></a>
  ### Voting    <a name="voting"></a>
  ### Quantum safe approaches    <a name="quantum"></a>


## Economical model   <a name="model"></a>
  ### Business model    <a name="businessmodel"></a>
  ### Incentivization system    <a name="incentivization"></a>
  ### Node incentivization    <a name="nodeincentivization"></a>
  ### Decentralized reward delivery mechanism    <a name="reward"></a>
  ### Cerberus incentivization  <a name="subreward"></a>
  
## HellHound attacks resistance  <a name="attacks"></a>
## Roadmap  <a name="roadmap"></a>
## Join us in the HellHound journey  <a name="joinus"></a>
## Conclusion  <a name="conclusion"></a>
## Acknowledgments  <a name="acknowledgments"></a>
## References <a name="references"></a>



