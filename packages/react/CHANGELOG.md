# @fuels/react

## 0.28.1

### Patch Changes

- [#257](https://github.com/FuelLabs/fuel-connectors/pull/257) [`b789ad0`](https://github.com/FuelLabs/fuel-connectors/commit/b789ad04054d4c7a57b0e6c14e33dd83cb479013) Thanks [@helciofranco](https://github.com/helciofranco)! - Sort connectors by `connected` and then `installed` status.

- [#257](https://github.com/FuelLabs/fuel-connectors/pull/257) [`b789ad0`](https://github.com/FuelLabs/fuel-connectors/commit/b789ad04054d4c7a57b0e6c14e33dd83cb479013) Thanks [@helciofranco](https://github.com/helciofranco)! - Add a `Installed` and `Connected` badge in the Connectors List.

## 0.28.0

### Minor Changes

- [#252](https://github.com/FuelLabs/fuel-connectors/pull/252) [`eea98c9`](https://github.com/FuelLabs/fuel-connectors/commit/eea98c991ed9aca318f65743f2734d5aa32e2e0e) Thanks [@helciofranco](https://github.com/helciofranco)! - Update SDK to `0.94.6` version. https://github.com/FuelLabs/fuels-ts/releases/tag/v0.94.6

- [#224](https://github.com/FuelLabs/fuel-connectors/pull/224) [`1f6ee86`](https://github.com/FuelLabs/fuel-connectors/commit/1f6ee8679994528ae36faec51535a183d582a58b) Thanks [@helciofranco](https://github.com/helciofranco)! - Bump pnpm version to v9.5.0

- [#251](https://github.com/FuelLabs/fuel-connectors/pull/251) [`d10db6d`](https://github.com/FuelLabs/fuel-connectors/commit/d10db6d28e74d958addbb113ec07bd75c0821e74) Thanks [@helciofranco](https://github.com/helciofranco)! - Add `useSelectNetwork` to select a network in the connected app.

- [#251](https://github.com/FuelLabs/fuel-connectors/pull/251) [`d10db6d`](https://github.com/FuelLabs/fuel-connectors/commit/d10db6d28e74d958addbb113ec07bd75c0821e74) Thanks [@helciofranco](https://github.com/helciofranco)! - Add `useNetworks` to get the list of networks available in the connected app.

- [#251](https://github.com/FuelLabs/fuel-connectors/pull/251) [`d10db6d`](https://github.com/FuelLabs/fuel-connectors/commit/d10db6d28e74d958addbb113ec07bd75c0821e74) Thanks [@helciofranco](https://github.com/helciofranco)! - Deprecate `useAddNetwork` hook. Use `useSelectNetwork` instead.

### Patch Changes

- [#246](https://github.com/FuelLabs/fuel-connectors/pull/246) [`b662c8d`](https://github.com/FuelLabs/fuel-connectors/commit/b662c8d36f078764a4f6a146ad9758db3882e5ac) Thanks [@helciofranco](https://github.com/helciofranco)! - Add optional query parameters to `useConnectors`, allowing developers to customize the `select` query.

- [#246](https://github.com/FuelLabs/fuel-connectors/pull/246) [`b662c8d`](https://github.com/FuelLabs/fuel-connectors/commit/b662c8d36f078764a4f6a146ad9758db3882e5ac) Thanks [@helciofranco](https://github.com/helciofranco)! - Sort connectors by name in the `Connect Wallet` modal.

## 0.27.1

## 0.27.0

### Minor Changes

- [#231](https://github.com/FuelLabs/fuel-connectors/pull/231) [`083bf92`](https://github.com/FuelLabs/fuel-connectors/commit/083bf92b594c7d1eee9e7225f909e1e140aef809) Thanks [@helciofranco](https://github.com/helciofranco)! - Update to `fuel-core@0.35.0`, `forc@0.63.3` and `fuels@0.94.4`

## 0.26.0

## 0.25.0

## 0.24.0

### Minor Changes

- [#167](https://github.com/FuelLabs/fuel-connectors/pull/167) [`ed5fb44`](https://github.com/FuelLabs/fuel-connectors/commit/ed5fb440b1b0739fbeb616156864d9ba6da3ac07) Thanks [@LeoCourbassier](https://github.com/LeoCourbassier)! - - Bumped packages version from `0.9.0` to `0.23.0` following react package's version
  - Updated react-next example to use `defaultConnectors` from @fuels/connectors package

## 0.23.0

### Minor Changes

- 🐞 Fixing infinite loading of wallet connector when fuelConfig connectors are defined asynchronously, by [@rodrigobranas](https://github.com/rodrigobranas) (See [#108](https://github.com/FuelLabs/fuels-npm-packs/pull/108))

### Patch Changes

- Updated UI connector's style to match provider's modal style, increasing user experience, by [@LeoCourbassier](https://github.com/LeoCourbassier) (See [#110](https://github.com/FuelLabs/fuels-npm-packs/pull/110))

## 0.22.0

### Minor Changes

- Add a loading state to display when the connector has installed status set to false, by [@helciofranco](https://github.com/helciofranco) (See [#104](https://github.com/FuelLabs/fuels-npm-packs/pull/104))

## 0.21.0

### Minor Changes

- Created useContractRead hook to read contract data from a contract instance or from a contract id.
  If provided Abi is declared with `as const`, hook will dynamically infer possible method names, as well as the arguments quantity and types for a selected method, by [@arthurgeron](https://github.com/arthurgeron) (See [#91](https://github.com/FuelLabs/fuels-npm-packs/pull/91))
- - Add `useTransactionResult` hook to get a transaction that has been executed
  - Create a type `UseNamedQueryParams` to allow overriding `select` function of TanStack Query and our custom `name` property.
  ### Basic usage with `select` function
  ````tsx
  const { receipts } = useTransactionResult({
  txId: '0xd7ad974cdccac8b41132dfe1d2a4219a681af1865f0775f141c4d6201ee428d1',
  query: {
  name: 'receipts', // Or anything else (optional, default: 'transactionResult')
  select: (data) => data?.receipts || null,
  },
  });
  ```, by [@helciofranco](https://github.com/helciofranco) (See [#94](https://github.com/FuelLabs/fuels-npm-packs/pull/94))
  ````
- Adds mutation callbacks, such as `onError` and `onSuccess`, by [@helciofranco](https://github.com/helciofranco) (See [#97](https://github.com/FuelLabs/fuels-npm-packs/pull/97))
- Provide consistent return types across Fuel hooks, for an easier typed experience.
  Every query hook will now return a `null` value if the query is not available, instead of `undefined`.
  ### Examples
  ````tsx
  const { wallet } = useWallet(); // wallet is Wallet | null
  const { network } = useNetwork(); // network is Network | null
  // and so on... Every query hook will return T | null
  ```, by [@helciofranco](https://github.com/helciofranco) (See [#85](https://github.com/FuelLabs/fuels-npm-packs/pull/85))
  ````
- Add `useSendTransaction` hook that allows developers to easily send a transaction.
  ````tsx
  const { sendTransaction } = useSendTransaction();
  // [...]
  const transactionRequest = new ScriptTransactionRequest({}); // Or any other tx request
  sendTransaction({
  address: 'fuel1zs7l8ajg0qgrak3jhhmq3xf3thd8stu535gj7p5fye2578yccjyqcgja3z',
  transaction,
  });
  ```, by [@helciofranco](https://github.com/helciofranco) (See [#92](https://github.com/FuelLabs/fuels-npm-packs/pull/92))
  ````

## 0.20.0

### Minor Changes

- Update fuels dependency to 0.86.0, by [@LuizAsFight](https://github.com/LuizAsFight) (See [#80](https://github.com/FuelLabs/fuels-npm-packs/pull/80))

## 0.19.0

### Minor Changes

- Upgrade to testnet (fuel-core 0.26.0 + fuels-ts 0.84.0), by [@arthurgeron](https://github.com/arthurgeron) (See [#72](https://github.com/FuelLabs/fuels-npm-packs/pull/72))
- Upgraded fuels-ts to new minor 0.83.0, by [@arthurgeron](https://github.com/arthurgeron) (See [#72](https://github.com/FuelLabs/fuels-npm-packs/pull/72))

## 0.18.1

### Patch Changes

- 🐞 fix: UI connectors loader, by [@luizstacio](https://github.com/luizstacio) (See [#68](https://github.com/FuelLabs/fuels-npm-packs/pull/68))

## 0.18.0

### Minor Changes

- 🐞 fix: only set theme colors style when its on client, by [@LuizAsFight](https://github.com/LuizAsFight) (See [#63](https://github.com/FuelLabs/fuels-npm-packs/pull/63))

## 0.17.0

### Minor Changes

- ✨ feat: make react-query package a peerDependency, by [@LuizAsFight](https://github.com/LuizAsFight) (See [#60](https://github.com/FuelLabs/fuels-npm-packs/pull/60))

### Patch Changes

- 🐞 fix: listen to prop data also using Reflect, by [@LuizAsFight](https://github.com/LuizAsFight) (See [#58](https://github.com/FuelLabs/fuels-npm-packs/pull/58))

## 0.16.0

### Minor Changes

- 🐞 fix: fuel hooks will only re-render tracked properties, instead of listening to every useQuery property, by [@helciofranco](https://github.com/helciofranco) (See [#55](https://github.com/FuelLabs/fuels-npm-packs/pull/55))

## 0.15.3

## 0.15.2

### Patch Changes

- chore: update fuels deps, by [@luizstacio](https://github.com/luizstacio) (See [#50](https://github.com/FuelLabs/fuels-npm-packs/pull/50))

## 0.15.1

### Patch Changes

- Migrate packages from fuels wallet to this repo, by [@matt-user](https://github.com/matt-user) (See [#40](https://github.com/FuelLabs/fuels-npm-packs/pull/40))

## 0.15.1

### Patch Changes

- Migrate packages from fuels wallet to this repo, by [@matt-user](https://github.com/matt-user) (See [#40](https://github.com/FuelLabs/fuels-npm-packs/pull/40))
