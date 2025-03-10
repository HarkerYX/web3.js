# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<!-- EXAMPLE

## [1.0.0]

### Added

- I've added feature XY (#1000)

### Changed

- I've cleaned up XY (#1000)

### Deprecated

- I've deprecated XY (#1000)

### Removed

- I've removed XY (#1000)

### Fixed

- I've fixed XY (#1000)

### Security

- I've improved the security in XY (#1000)

-->

## [4.0.0-alpha.1]

### Breaking Changes

#### Connection close is not supported

In `1.x` user had access to raw connection object and can interact with it. e.g.

```ts
web3.currentProvider.connection.close();
```

But this internal behavior is not exposed any further. Though you can achieve same with this approach.

```ts
web3.currentProvider.disconnect();
```

## [4.0.1-alpha.2]

### Changed

-   `tsc` compiled files moved to `lib/` directory from `dist/` (#5739)

## [4.0.1-alpha.5]

### Removed

-   `build` entry from `package.json` (#5755)

## [4.0.1-rc.0]

### Added

-   `registeredSubscriptions` was added by default in web3 constructor (#5792)
-   Add named exports for all objects which are the default-exported-object in their packages (#5771)
-   Export all packages' objects organized by namespaces (#5771)
-   Add Additional flat exports for all types and constants from `web3-types`, `web3-errors` and `web3`. (#5771)
-   Fix few issues with `new Web3().eth.contract` (#5824)

### Changed

-   `require('web3')` will now return all web3 exported-objects organized in namespaces . (#5771)

### Removed

-   Private static `_contracts:Contract[]` and static `setProvider` function was removed (#5792)

## [4.0.1-rc.1]

### Added

-   Added source files (#5956)
-   Added hybrid build (ESM and CJS) of library (#5904)

### Changed

-   No need for polyfilling nodejs `net` and `fs` modules (#5978)
-   Removed IPC provider dependency, IPC path is no longer viable provider. If you wanna use IPC, please install `web3-providers-ipc` and instantiate provider yourself (#5978)

## [4.0.1-rc.2]

### Changed

-   Dependencies updated

## [4.0.1]

Release Notes:

Detailed List of change logs are mentioned under previous 4.x alpha and RC releases.

Documentation:
[Web3.js documentation](https://docs.web3js.org/)
[Web3 API](https://docs.web3js.org/api)
[Migration Guide from 1.x](https://docs.web3js.org/guides/web3_upgrade_guide/x/)

## [4.0.2]

### Added

-   Exported `Web3Context`, `Web3PluginBase`, `Web3EthPluginBase` from `'web3-core'`, and `Web3Validator` from `'web3-validator'` (#6165)

### Fixed

-   Fixed bug #6185, now web3.js compiles on typescript v5 (#6195)
-   Fixed #6162 @types/ws issue (#6205)

## [4.0.3]

## Added

-   Web3 constructor accepts `Web3ContextInitOptions<EthExecutionAPI, CustomRegisteredSubscription>` as alternative to the still supported `undefined`, `string`, and `SupportedProviders<EthExecutionAPI>` (#6262).

### Fixed

-   Fixed bug #6236 by adding personal type in web3.eth (#6245)

## [4.1.0]

### Added

-   Added minimum support of web3.extend function

## [4.1.1]

### Added

-   To fix issue #6190, added the functionality to introduce different timeout value for Web3. (#6336)

## [4.1.2]

### Fixed

-   Fix of incorrect provider warning behavior

## [4.2.0]

### Changed

-   Dependencies updated

### Added

-   Various web3 sub packages has new functions details are in root changelog

## [4.2.1]

### Changed

-   Dependencies updated

## [4.2.2]

### Changed

-   Dependencies updated ( details are in root changelog )

## [4.3.0]

### Added

- Added methods (privateKeyToAddress, parseAndValidatePrivateKey, and privateKeyToPublicKey) to web3.eth.accounts (#6620)

### Changed

-   Dependencies updated

## [4.4.0]

-   Dependencies updated ( details are in root changelog )

## [4.5.0]

-   Dependencies updated ( details are in root changelog )

## [4.6.0]

### Added

-   Added EIP-6963 utility function `requestEIP6963Providers` for multi provider discovery ( other details are in root changelog )


## [4.7.0]

### added

#### web3-eth-contract

-   Types `ContractDeploySend`, `ContractMethodSend`, `Web3PromiEvent` was exported (#6883)

#### web3-eth-ens

- Added function getText and getName in ENS and resolver classes (#6914)

### fixed

#### web3-validator

- Multi-dimensional arrays(with a fix length) are now handled properly when parsing ABIs (#6798)

#### web3-utils

- fixed erroneous parsing of big numbers in the `toNumber(...)` function (#6880)

## [4.8.0]

### Changed

#### web3-eth-abi

-   Dependencies updated

#### web3-eth-accounts

-   Dependencies updated

### Fixed

#### web3-eth-contract

-	Fix an issue with smart contract function overloading (#6922)

#### web3-utils

- fixed toHex incorrectly hexing Uint8Arrays and Buffer (#6957)
- fixed isUint8Array not returning true for Buffer (#6957)


### Added

#### web3-eth-contract

-	Added a console warning in case of an ambiguous call to a solidity method with parameter overloading (#6942)
-	Added contract.deploy(...).decodeData(...) and contract.decodeMethodData(...) that decode data based on the ABI (#6950)

#### web3-eth

-   method `getBlock` now includes properties of eip 4844, 4895, 4788 when returning block (#6933) 
-   update type `withdrawalsSchema`, `blockSchema` and `blockHeaderSchema` schemas to include properties of eip 4844, 4895, 4788 (#6933)


#### web3-types

-   Added `signature` to type `AbiFunctionFragment` (#6922)
-   update type `Withdrawals`, `block` and `BlockHeaderOutput` to include properties of eip 4844, 4895, 4788 (#6933)

## [Unreleased]

### Added

-   Updated type `Web3EthInterface.accounts` to includes `privateKeyToAccount`,`privateKeyToAddress`,and `privateKeyToPublicKey` (#6762)
