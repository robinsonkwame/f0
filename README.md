# F0

> Factoria F0 contract

This repository contains the F0 smart contract for Factoria.

# Licensing

The primary license for Factoria F0 is the Business Source License 1.1 (BUSL-1.1), see [LICENSE](LICENSE).

# Structure

There are 2 main contracts that derive from F0.sol:

1. [contracts/Factory.sol](contracts/Factory.sol): The factory contract for creating F0 contract
2. [contracts/Royalty.sol](contracts/Royalty.sol): The programmable royalty contract used by the factory contract

These main contracts derive from the following *.sol:
3. [contracts/F0.sol](contracts/F0.sol): The NFT contract
4. [contracts/F0ERC721Upgradeable.sol](contracts/F0ERC721Upgradeable.sol)
    - F0 inherits from this file instead of [@openzeppelin/ERC721Upgradeable.sol](https://github.com/OpenZeppelin/openzeppelin-contracts-upgradeable/blob/master/contracts/token/ERC721/ERC721Upgradeable.sol).
    - Identical to @openzeppelin/ERC721Upgradeable except **one difference**
    - **difference:** the `_name` and `_symbol` attributes are declared ["internal"](https://github.com/factoria-org/f0/blob/main/contracts/F0ERC721Upgradeable.sol#L31-L35) instead of ["private"](https://github.com/OpenZeppelin/openzeppelin-contracts-upgradeable/blob/master/contracts/token/ERC721/ERC721Upgradeable.sol#L25-L28). Because it's "internal", F0 can inherit and [update the name and symbol](contracts/F0.sol#L77-L82) (which the defalut OpenZeppelin contract doesn't allow).
