# Blockchain_file_storage_system
This is a web-based application for decentralized file storing using blockchain. In this application any user can upload as many files(one at a time) as he/she likes. All other peers and the user himself can download and access those file in their system. File can be of any type and any size.<br />
Randomly generated nonce in proof of work concept is used to acheive the required difficulty (diff = 3). Once peer uploads the file, the file is stored in a block including username, filesize and file data. These block gets appended to the current blockchain, which makes it impossible to edit or delete the file/block.<br /> 
The reason to implement file storing using blockchain is its abilitiy to avoid any modification or deletion. No one can delete or corrupt our files that are stored.
<h2>Proof of Work Algorithm:</h2>

Blockchain-based applications are typically peer-to-peer networks that must be as decentralized as possible. To support and enhance network decentralization, all peers in the network should be able to add new blocks to the network. Proof of work algorithms simulate the idea of each peer being able to add a new block. The goal of proof of work algorithms is to solve various cryptographic puzzles. Peers who solve these puzzles more quickly can add a new block to the blockchain.

Two different proof of work algorithms are included in our blockchain implementation. Both are attempting to solve the same cryptographic puzzle, but in different ways. According to these proof of work algorithms, whoever finds a hash value for their block that contains a certain number of leading zeros will be able to announce it to the chain. For example, our blockchain only allows miners to add a block if the hash value of their block begins with three zeros, indicating that the difficulty of the blockchain is 3. The term miner refers to peers who attempt to add blocks to the blockchain.

Based on this idea, we have implemented two algorithms. Both calculate nonce differently. One calculates nonce randomly in each iteration and another one simply increments nonce by one in each iteration. We have analyzed running time and behavior of both algorithms in the file named POW_Comparison.py. Based on the output of the file, we have concluded some results for both the methods.

<h2>Comparison of proof of work algorithms:</h2>

<h3>Difference:</h3>

1. Nonce = random.randint(0,99999999) (first algorithm: p_o_w)
2. Nonce += 1 (second algorithm: p_o_w_2)

The running time for first algorithm:

|               | Attempt #1 | Attempt #2 | Attempt #3 | Attempt #4 |
|---------------|------------|------------|------------|------------|
| Difficulty #2 | 0.00018    | 0.00281    | 0.00102    | 0.00039    |            
| Difficulty #3 | 0.00069    | 0.03207    | 0.00485    | 0.00356    |            
| Difficulty #4 | 0.13479    | 0.22688    | 0.34565    | 0.19841    |            
| Difficulty #5 | 4.06034    | 2.08288    | 0.58391    | 0.2094     |            

The running time of Second algorithm:

|               | Attempt #1 | Attempt #2 | Attempt #3 | Attempt #4 |
|---------------|------------|------------|------------|------------|
| Difficulty #2 | 0.00035    | 0.00080    | 0.00062    | 0.00108    |            
| Difficulty #3 | 0.02190    | 0.02463    | 0.02104    | 0.01625    |            
| Difficulty #4 | 0.00366    | 0.03813    | 0.32095    | 0.02145    |            
| Difficulty #5 | 0.04403    | 3.10820    | 1.53688    | 1.50288    |     
