# NFTAirdropDemo

This repo is a demo for deploying ERC721 tokens utilising Merkle trees. This method is compared with other deployment strategies.
The Merkle-airdrop would allow for the deployer to have comparitively cheaper deployment, and would allow an airdrop startegy in which the minting of a token is paid for by the token recipient; further reducing deployer's cost.

Merkle-proofs would also provide an additional element of verifcation as to who exactly can receive the airdrop and guarantee no new tokens could be minted after this airdrop.

Docs are created using hardhat-docgen.

## Cost examples
·-------------------------------------------------------|---------------------------|-------------|-----------------------------·
|                  Solc version: 0.8.4                  ·  Optimizer enabled: true  ·  Runs: 200  ·  Block limit: 30000000 gas  │
························································|···························|·············|······························
|  Methods                                                                                                                      │
··········································|·············|·············|·············|·············|···············|··············
|  Contract                               ·  Method     ·  Min        ·  Max        ·  Avg        ·  # calls      ·  eur (avg)  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721Basic                            ·  grantRole  ·          -  ·          -  ·      51441  ·            1  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721Basic                            ·  mint       ·      74217  ·      74229  ·      74227  ·           40  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721LazyMint                         ·  grantRole  ·          -  ·          -  ·      51463  ·            3  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721LazyMint                         ·  redeem     ·      80249  ·      80281  ·      80265  ·           42  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721LazyMintWith712                  ·  grantRole  ·          -  ·          -  ·      51463  ·            3  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721LazyMintWith712                  ·  redeem     ·      80432  ·      80476  ·      80458  ·           42  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721LazyMintWith712SignatureChecker  ·  grantRole  ·          -  ·          -  ·      51441  ·            3  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721LazyMintWith712SignatureChecker  ·  redeem     ·      92056  ·      92108  ·      92084  ·           42  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  ERC721MerkleDrop                       ·  redeem     ·      75277  ·      76877  ·      76563  ·           42  ·          -  │
··········································|·············|·············|·············|·············|···············|··············
|  Deployments                                          ·                                         ·  % of limit   ·             │
························································|·············|·············|·············|···············|··············
|  ERC721Basic                                          ·          -  ·          -  ·    1592663  ·        5.3 %  ·          -  │
························································|·············|·············|·············|···············|··············
|  ERC721LazyMint                                       ·          -  ·          -  ·    1889217  ·        6.3 %  ·          -  │
························································|·············|·············|·············|···············|··············
|  ERC721LazyMintWith712                                ·          -  ·          -  ·    1961984  ·        6.5 %  ·          -  │
························································|·············|·············|·············|···············|··············
|  ERC721LazyMintWith712SignatureChecker                ·          -  ·          -  ·    1938755  ·        6.5 %  ·          -  │
························································|·············|·············|·············|···············|··············
|  ERC721MerkleDrop                                     ·          -  ·          -  ·    1349399  ·        4.5 %  ·          -  │
························································|·············|·············|·············|···············|··············
|  SmartWallet                                          ·          -  ·          -  ·     595098  ·          2 %  ·          -  │
·-------------------------------------------------------|-------------|-------------|-------------|---------------|-------------·

Made with hardhat-gas-reporter

## Made with
- Solidity
- Hardat

### This repo is inspired by;
- Openzeppelin's workshop; [nft-merkle-drop](https://github.com/OpenZeppelin/workshops/tree/master/06-nft-merkle-drop)
