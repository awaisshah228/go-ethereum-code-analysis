# go-ethereum code analysis

**I hope to analyze the code of Ethereum to learn the use of blockchain technology and GO language.**

Analysis of [go-ethereum](https://github.com/ethereum/go-ethereum)  
The process, I hope to start from the low-level technical components that rely on less, and slowly go deep into the core logic.

## Table of contents

- [go ethereum code analysis (account, smart contract, logs, etc...)](/go-ethereum-code-analysis.md)
- [yellow book symbol index](symbol-index.md)
- [rlp, rlpx analysis](/rlp-analysis.md)
- [trie source analysis](/trie-analysis.md)
- [ethdb analysis](/ethdb-analysis.md)
- [rpc analysis](/rpc-analysis.md)
- [p2p analysis](/p2p-analysis.md)
- [eth protocol analysis](/eth-analysis.md)
- **core analysis**
  - [blockchain index, chain_indexer analysis](/core-chain_indexer-analysis.md)
  - [bloom filter index, bloombits-analysis](/core-bloombits-analysis.md)
  - [ethereum trie, tree management, rollback, state-analysis](/core-state-analysis.md)
  - [transaction processing](/core-state-process-analysis.md)
  - **vm analysis**
    - [stack & data structure](/core-vm-stack-memory-analysis.md)
    - [instruction, jump table, interpreter analysis](/core-vm-jumptable-instruction.md)
    - [vm analysis](/core-vm-analysis.md)
  - **transaction pool management**
    - [transaction execution](/core-txlist-data-structure-analysis.md)
    - [transaction pool management](/core-txpool-analysis.md)
  - [creation block](/core-genesis-analysis.md)
  - [blockchain-analysis](/core-blockchain-analysis.md)
- [miner analysis & CPU mining](/miner-analysis-CPU-mining.md)
- [pow, poa, pos algorithms](/pow-analysis.md)
- [ethereum test network Clique_PoA introduciton](/ethereum-Clique_PoA-introduction.md)
- [swarm, raw & file upload, pss and feed](/ethereum-swarm-introduction.md)
- 

# The Right Triangle

## Base Geometry

![at](img/triangle.png)

Let the right triangle hypothenuse be aligned with the coordinate system *x-axis*. 
The vector loop closure equation running counter-clockwise then reads

$$a{\bold e}_\alpha + b\tilde{\bold e}_\alpha + c{\bold e}_x = \bold 0$$

with

$${\bold e}_\alpha = \begin{pmatrix}\cos\alpha\\ \sin\alpha\end{pmatrix} \quad and \quad {\tilde\bold e}_\alpha = \begin{pmatrix}-\sin\alpha\\ \cos\alpha\end{pmatrix}$$

Resolving for the hypothenuse part $c{\bold e}_x$ in the loop closure equation (1) 

$$-c{\bold e}_x = a{\bold e}_\alpha + b\tilde{\bold e}_\alpha$$

and squaring 

> finally results in the Pythagorean theorem (2)
>
> $$c^2 = a^2 + b^2$$ (2)

## More Triangle Stuff

Introducing the hypothenuse segments $p={\bold a}\cdot{\bold e}_x$ and  $q={\bold b}\cdot{\bold e}_x$, we can further obtain the following useful formulas.


| segment *p* | segment *q* | height *h* | area |
|:---:|:---:|:---:|:---:|
|$cp = a^2$|$cq = b^2$|$pq = h^2$|$ab = ch$|
