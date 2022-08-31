# @near-wallet-selector/next-wallet

This is the [Next Wallet](https://thenextwallet.com/) package for NEAR Wallet Selector.

## Installation and Usage

The easiest way to use this package is to install it from the NPM registry, this package requires `near-api-js` v0.44.2 or above:

```bash
# Using Yarn
yarn add near-api-js@^0.44.2

# Using NPM.
npm install near-api-js@^0.44.2
```
```bash
# Using Yarn
yarn add @thenextwallet/next-wallet-selector

# Using NPM.
npm install @thenextwallet/next-wallet-selector
```

Then use it in your dApp:

```ts
import { setupWalletSelector } from "@near-wallet-selector/core";
import { setupNextWallet } from "@thenextwallet/next-wallet-selector";

// Next Wallet for Wallet Selector can be setup without any params or it can take two optional params.
const nextWallet = setupNextWallet({
  walletUrl: "https://testnet.thenextwallet.com",
  iconUrl: "https://yourdomain.com/yourwallet-icon.png"
});

const selector = await setupWalletSelector({
  network: "testnet",
  modules: [nextWallet],
});
```

## Options

- `walletUrl` (`string?`): Wallet URL used to redirect when signing transactions. This parameter is required for custom network configuration.
- `iconUrl`: (`string?`): Image URL for the icon shown in the modal. This can also be a relative path or base64 encoded image. Defaults to `./assets/next-wallet-icon.png`.

## Assets

Assets such as icons can be found in the `/assets` directory of the package. Below is an example using Webpack:

```ts
import { setupNextWallet } from "@thenextwallet/next-wallet-selector";
import nextWalletIconUrl from "@thenextwallet/next-wallet-selector/assets/next-wallet-icon.png";

const nextWallet = setupNextWallet({
  iconUrl: nextWalletIconUrl
});
```

## License

This repository is distributed under the terms of both the MIT license and the Apache License (Version 2.0).
