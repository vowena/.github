<div align="center">
  <a href="https://vowena.xyz">
    <img src="./profile/banner.svg" alt="Vowena, trustless recurring payments built on Stellar" width="100%" />
  </a>
</div>

<p align="center">
  <strong>Trustless recurring payments, built on Stellar.</strong>
</p>

<p align="center">
  Vowena is a Soroban smart contract that lets merchants run subscriptions in USDC (or any SEP-41 token) without intermediaries. Subscribers authorize a spending allowance once; the contract enforces the billing rules autonomously, on chain.
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/@vowena/sdk"><img alt="npm" src="https://img.shields.io/npm/v/@vowena/sdk?style=flat-square&color=6B4EFF&label=%40vowena%2Fsdk&labelColor=0F0F16"></a>
  <a href="https://stellar.expert/explorer/testnet/contract/CCNDNEGYFYKTVBM7T2BEF5YVSKKICE44JOVHT7SAN5YTKHHBFIIEL72T"><img alt="Network" src="https://img.shields.io/badge/network-stellar%20testnet-6B4EFF?style=flat-square&labelColor=0F0F16"></a>
  <a href="https://github.com/vowena/protocol/blob/main/LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Apache--2.0-6B4EFF?style=flat-square&labelColor=0F0F16"></a>
  <a href="https://x.com/vowena"><img alt="X" src="https://img.shields.io/badge/follow-%40vowena-6B4EFF?style=flat-square&labelColor=0F0F16"></a>
</p>

<br />

## Get started

<table width="100%">
  <tr>
    <td width="33%" valign="top">
      <h4>Install the SDK</h4>
      <pre><code>npm install @vowena/sdk</code></pre>
      <sub>TypeScript, ESM and CJS, ships with full types.</sub>
    </td>
    <td width="33%" valign="top">
      <h4>Launch the dashboard</h4>
      <p><a href="https://dashboard.vowena.xyz">dashboard.vowena.xyz</a></p>
      <sub>Connect Freighter, create a plan, manage subscriptions.</sub>
    </td>
    <td width="33%" valign="top">
      <h4>Read the docs</h4>
      <p><a href="https://docs.vowena.xyz">docs.vowena.xyz</a></p>
      <sub>Contract reference, SDK guides, integration recipes.</sub>
    </td>
  </tr>
</table>

<br />

## Repositories

<table width="100%">
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/vowena/protocol">vowena/protocol</a></h3>
      <p>Soroban smart contract written in Rust. The billing engine. Plans, subscriptions, charge, refund, migrations, grace periods, auto-expiry.</p>
      <sub>Rust  ·  Soroban  ·  Stellar testnet</sub>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/vowena/sdk">vowena/sdk</a></h3>
      <p>TypeScript SDK published to npm as <code>@vowena/sdk</code>. Wraps every contract function with typed inputs, simulation, and event helpers.</p>
      <sub>TypeScript  ·  @stellar/stellar-sdk  ·  works with Freighter, xBull, Albedo, WalletConnect</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/vowena/dashboard">vowena/dashboard</a></h3>
      <p>Next.js app for merchants and subscribers. Plan creation, billing analytics, the Universal Subscription Manager, and a built-in keeper.</p>
      <sub>Next.js  ·  React  ·  <a href="https://dashboard.vowena.xyz">dashboard.vowena.xyz</a></sub>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/vowena/site">vowena/site</a></h3>
      <p>Marketing site at <a href="https://vowena.xyz">vowena.xyz</a>. Landing, pricing, blog, brand surface.</p>
      <sub>Next.js  ·  static  ·  edge cached</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/vowena/docs">vowena/docs</a></h3>
      <p>Developer documentation at <a href="https://docs.vowena.xyz">docs.vowena.xyz</a>. Contract reference, SDK guides, integration patterns.</p>
      <sub>Mintlify  ·  MDX</sub>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/vowena">More coming</a></h3>
      <p>Keeper bot, indexer, framework adapters, and reference integrations are on the roadmap.</p>
      <sub>open source by default</sub>
    </td>
  </tr>
</table>

<br />

## How Vowena works

1. **Create a plan.** A merchant defines the token, amount, period, trial, max periods, grace window, and price band. The plan lives on chain and is immutable.
2. **Subscribe with an allowance.** A subscriber authorizes the Vowena contract to spend up to a fixed amount of their token, with an expiration ledger. They sign once, in their wallet.
3. **Charge permissionlessly.** Anyone can call `charge` for a due subscription. The contract validates timing and allowance, then transfers tokens from the subscriber to the merchant.
4. **Settle on chain.** Every billing event, refund, pause, and cancellation is emitted as a Soroban event. The contract is the source of truth; the dashboard and SDK are convenience layers.

The subscriber's funds are never custodied by Vowena. The contract holds a permission to pull, not the funds themselves. Cancellation is one call, public, and works without any frontend.

<br />

## Network

Live today on **Stellar testnet** at contract `CCNDNEGYFYKTVBM7T2BEF5YVSKKICE44JOVHT7SAN5YTKHHBFIIEL72T`. Mainnet deployment ships after pilot merchants.

<br />

## Community

- Web: [vowena.xyz](https://vowena.xyz)
- Docs: [docs.vowena.xyz](https://docs.vowena.xyz)
- Dashboard: [dashboard.vowena.xyz](https://dashboard.vowena.xyz)
- X: [@vowena](https://x.com/vowena)
- Discussions: [github.com/orgs/vowena/discussions](https://github.com/orgs/vowena/discussions)
- Contact: [hello@vowena.xyz](mailto:hello@vowena.xyz)

<br />

<p align="center">
  Built on <a href="https://stellar.org">Stellar</a>. Powered by <a href="https://stellar.org/soroban">Soroban</a>.
</p>

<p align="center">
  <sub>Apache-2.0 licensed. Read the source. Run the keeper. Own your billing.</sub>
</p>
