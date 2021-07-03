
# GPFS Network Litepaper
[简体中文](README_CN.md)

## Abstract
IPFS(InterPlanetary File System) is a distributed web, point-to-point hypermedia protocol. It can make our Internet faster, safer, and more open. In some respects, IPFS is similar to the web, but the web is centralized, and IPFS is a single Bittorrent cluster, distributed storage using git warehouses. In other words, IPFS provides a high-throughput content-addressable block storage model with content-addressable hyperlinks. This forms a generalized Merkle DAG data structure, which can be used to build version file systems, blockchains, and even permanent websites. IPFS combines distributed hash tables, block exchanges with incentive mechanisms, and self-certified namespaces. IPFS has no single point of failure, and nodes do not need to trust each other. GPFS is fully compatible with the IPFS protocol and is the incentive layer of IPFS. GPFS and IPFS are in the same P2P network, and the data of GPFS nodes and IPFS nodes can be seamlessly connected.

## Background
As an important infrastructure of Web3.0, IPFS has always attracted attention.。[go-ipfs](https://github.com/ipfs/go-ipfs) is its main implementation. Although it has been online for many years, it has been in a semi-available state. Mainly due to the lack of incentive layer, resulting in not many active nodes. With the launch of the much-anticipated [Filecoin](https://github.com/filecoin-project/lotus) mainnet, I thought it could be changed. However, due to the mechanism of Filecoin itself, it is determined that it can only store cold data. Even access to a small file of only a few K takes several hours, which is far from meeting the current web3.0 requirements. Back to go-ipfs itself, we found that its file access is very fast. At present, there are also many teams based on the above development, but they are fighting each other and have not formed a joint force. What GPFS has to do is to transform the IPFS network and provide incentive nodes so that all personal computers can become miners. By providing storage space and obtaining incentives, the throughput of the entire IPFS network can be improved to ensure the security and availability of data in the network. Truly become the cornerstone of web3.0.
## Network structure
The GPFS node is a special node in the IPFS network and seamlessly connects with the IPFS node. The data stored on the GPFS node can be read from the IPFS node, and vice versa. At the same time, the data saved through the GPFS node will be automatically broadcast to other GPFS nodes to form 3 to 5 copies. Even if the local data is deleted, it can be retrieved from any IPFS or GPFS node through the CID of the file. The network topology is as follows:
![](https://raw.githubusercontent.com/gpfs-group/gpfs-doc/main/image/gpfs.jpg)

## The difference between GPFS and Filecoin
- GPFS and IPFS are on the same network, Filecoin is an independent network.
- GPFS and IPFS data are seamlessly connected, and Filecoin needs to develop a data transfer function separately.
- GPFS has a fast data reading speed and is suitable for hot data, while Filecoin has a slow data reading speed and can only store cold data.
- GPFS has a low mining threshold, does not require pledges, and has no special requirements for hardware. Everyone can mine. Filecoin mining has a high threshold, requires pledges, high-performance graphics cards and professional operation and maintenance teams.

## Token economic model
The native token in the GPFS protocol is GPS, which is issued based on the Binance Smart Chain BSC, and miners participate in mining to obtain GPS. GPS can be used for later value-added services of GPFS. For example, when DAPP or commercial software needs to be connected to GPFS, you need to use GPS to pay.
The total amount of GPS tokens is 10,000,000,000 GPS, no external fundraising, and no reservations by the team. The token distribution rules are as follows:

- 0.1% airdrop to 100,000 BSC addresses.  
- 99.9% is generated by mining, and the output is halved every 4 years.

## 挖矿
The goal of the GPFS project is to provide a large number of stable active nodes for the IPFS network. We will reduce the mining threshold as much as possible, and each node only needs to provide 10G hard disk space and smaller network bandwidth. The GPFS network will randomly select a number of lucky nodes from all active nodes every 10 minutes (200 block height) to issue this reward. Each time, 50% of the total rewards will be distributed to the lucky nodes on average, and the other 50% will be distributed in proportion to the number of GPS held by the lucky nodes. In order to ensure fairness, the currency division logic is implemented through smart contracts, and the random algorithm used is publicly verifiable.
The rules for selecting the number of lucky nodes are as follows, assuming that the number of online nodes is N:
- If N <= 10, select all nodes.
- If 10 <N <= 100, select 10 nodes.
- If 100 <N <= 1000, select 30 nodes.
- If 1000 <N <= 10000, select 50 nodes.
- If N> 10000, select 100 nodes.

## Roadmap
- April 2021, the first version of the GPFS code was released to realize the improvement based on go-ipfs and the mining logic.
- May 2021, release the second version of the GPFS code, develop a smart contract for cents, and conduct internal testing.
- June 2021, it was officially released, and external mining began.
- September 2021, a gateway compatible with S3 interface will be released.

## Team 
We are a group of technical geeks from the IPFS community who came together with enthusiasm for IPFS technology and formed the GPFS team. We are a decentralized autonomous organization dedicated to the real implementation of IPFS technology in the world. We will continue to optimize the GPFS network protocol and actively promote ecological construction. The door of Web3.0 has been opened, and it is wonderful and worth looking forward to. We welcome more like-minded technical geeks to join.

