# Orbital

This repository contains the core smart contracts for Orbital, an automated market maker for pools of 2, 3, or 10,000 stablecoins.

## Local deployment

In order to deploy this code to a local testnet, you should install the npm package `@zorbital/orbital-core` and import the factory bytecode located at `@zorbital/orbital-core/artifacts/contracts/OrbitalFactory.sol/OrbitalFactory.json`. For example:

```typescript
import {
  abi as FACTORY_ABI,
  bytecode as FACTORY_BYTECODE,
} from '@zorbital/orbital-core/artifacts/contracts/OrbitalFactory.sol/OrbitalFactory.json'

// deploy the bytecode
```

This will ensure that you are testing against the same bytecode that is deployed to mainnet and public testnets, and all Orbital code will correctly interoperate with your local deployment.

## Using solidity interfaces

The Orbital interfaces are available for import into solidity smart contracts via the npm artifact `@zorbital/orbital-core`, e.g.:

```solidity
import '@zorbital/orbital-core/contracts/interfaces/IOrbitalPool.sol';

contract MyContract {
  IOrbitalPool pool;

  function doSomethingWithPool() {
    // pool.swap(...);
  }
}
```

## Development

Requires [Foundry](https://book.getfoundry.sh/getting-started/installation).

```bash
forge install
forge build
```

## Testing

```bash
forge test
```
