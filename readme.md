# About the project
With every passing day, we are able to observe extensive use cases of ZKP in the web3 space. In the past few months, a lot of innovation has been observed in projects like ZKML, ZK-based DAO Voting, etc which would aid the community in the future. But currently, users are not able to use these ZK dapps because the verification part is computationally intensive resulting in the end users being forced to pay excessive gas fees. Also, naive users have more trust in L1 chains rather than L2 chains because of their credibility, thus moving the whole dapp onto L2 is not the best solution.

Here is where ZKP-Hype comes into the picture. In our approach, the dapp is deployed over in L1 but the ZKP computational part is moved to the L2 chain. By doing this, the user pays less gas fees and can still have their funds in the L1 chain.

# L2 contract addresses
## zkEVM
L2 Verifier:-
0xC0eB65078d6b7047e92a10807Bd4348765953190<br>
L2 Router:- 
0x51525dA9BC4bE3dc88CCdE33F7CB70d87500fdAB

## Scroll
L2 Verifier(Successfully verified):-
0x335A3359024b959df5C7e6a7D994236E604958bA<br>
L2 Router(Tried verifying got status "Ok" in the foundry but was not verified in Explorer):-<br>
(You can find the contract at ./Router/src/Router.sol)<br>
0xAfC3a4180F344724E1EE5D2B2124b6eF90A2d7Ac

# Architecture of the project
We have executed our planned architecture with these 4 verticals:-

Noir Interchain Development Kit:- We have created an interchain dev kit for Noir developers using which they can compile, test, deploy the verifier, and run the off-chain agent with just a single command. Also, we have brought convenience to developers by providing debugging scripts using which they can verify the circuit on-chain.

Hyperlane-based ZKP Router:- Proofs and public inputs are relayed from L1 to L2 and computation result is relayed back to L1 using Hyperlane. We have created custom routers for this particular use case by integrating Hyperlane's mailbox and interchain gas paymasters.

Cache + ZkISM:- Using the base ISM provided by Hyperlane, we have created our custom routing ISM which caches output for particular proofs and public inputs so that there is no need to reverify again. Also, using the off-chain agent, you have an additional option to verify the L2 result off-chain.

Offchain-agent(Secondary):- Along with Noir Interchain Dev Kit, you get a prebuilt off-chain agent which you can pair with the custom ISM to add an additional verification layer for your project. This agent will run an off-chain verifier for the same circuit and will generate outputs based on the proof and public input received on the L1 router.

# Team members
Arman Aurobindo<br>
Shreyas Padmakiran<be>
ayushsingh82
