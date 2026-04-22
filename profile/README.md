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
      <sub>Connect any Stellar wallet, create a plan, manage subscriptions.</sub>
    </td>
    <td width="33%" valign="top">
      <h4>Read the docs</h4>
      <p><a href="https://docs.vowena.xyz">docs.vowena.xyz</a></p>
      <sub>Contract reference, SDK guides, integration recipes.</sub>
    </td>
  </tr>
</table>

<div align="center">
  <img src="./profile/divider.svg" alt="" width="100%" />
</div>

## How it works

<div align="center">
  <img src="./profile/flow.svg" alt="Vowena subscription lifecycle: plan, subscribe, allowance, charge, settle" width="100%" />
</div>

<table width="100%">
  <tr>
    <td valign="top">
      <strong>1. Plan.</strong> A merchant defines the token, amount, period, trial, max periods, grace window, and price band. The plan lives on chain and is immutable.
    </td>
    <td valign="top">
      <strong>2. Subscribe.</strong> A subscriber authorizes the Vowena contract to spend up to a fixed amount of their token, with an expiration ledger. They sign once, in their wallet.
    </td>
  </tr>
  <tr>
    <td valign="top">
      <strong>3. Allowance.</strong> The token's SAC stores the pre-approval. The Vowena contract holds permission to pull, never the funds themselves.
    </td>
    <td valign="top">
      <strong>4. Charge.</strong> Anyone can call <code>charge</code> for a due subscription. The contract validates timing and allowance, then pulls the next period from subscriber to merchant.
    </td>
  </tr>
  <tr>
    <td colspan="2" valign="top">
      <strong>5. Settle.</strong> Every billing event, refund, pause, and cancellation is emitted as a Soroban event. The contract is the source of truth; the dashboard and SDK are convenience layers. Cancellation is one call, public, and works without any frontend.
    </td>
  </tr>
</table>

<div align="center">
  <img src="./profile/divider.svg" alt="" width="100%" />
</div>

## The stack

<div align="center">
  <img src="./profile/stack.svg" alt="Vowena architecture stack: applications, protocol, foundation" width="100%" />
</div>

<div align="center">
  <img src="./profile/divider.svg" alt="" width="100%" />
</div>

## Repositories

<table width="100%">
  <tr>
    <td width="60" valign="top" align="center">
      <img src="./profile/icons/protocol.svg" width="56" height="56" alt="" />
    </td>
    <td valign="top">
      <h3 style="margin:0"><a href="https://github.com/vowena/protocol">vowena/protocol</a></h3>
      <p>Soroban smart contract written in Rust. The billing engine. Plans, subscriptions, charge, refund, migrations, grace periods, auto-expiry.</p>
      <sub>Rust  ·  Soroban  ·  Stellar testnet  ·  Apache 2.0</sub>
    </td>
  </tr>
  <tr>
    <td valign="top" align="center">
      <img src="./profile/icons/sdk.svg" width="56" height="56" alt="" />
    </td>
    <td valign="top">
      <h3 style="margin:0"><a href="https://github.com/vowena/sdk">vowena/sdk</a></h3>
      <p>TypeScript SDK published to npm as <code>@vowena/sdk</code>. Wraps every contract function with typed inputs, simulation, and event helpers.</p>
      <sub>TypeScript strict  ·  ESM + CJS  ·  works with Freighter, Lobstr, xBull, Albedo</sub>
    </td>
  </tr>
  <tr>
    <td valign="top" align="center">
      <img src="./profile/icons/dashboard.svg" width="56" height="56" alt="" />
    </td>
    <td valign="top">
      <h3 style="margin:0"><a href="https://github.com/vowena/dashboard">vowena/dashboard</a></h3>
      <p>Next.js app for merchants and subscribers. Plan creation, billing analytics, the universal subscription manager, and a managed keeper that runs as a Vercel cron.</p>
      <sub>Next.js 16  ·  React 19  ·  <a href="https://dashboard.vowena.xyz">dashboard.vowena.xyz</a></sub>
    </td>
  </tr>
  <tr>
    <td valign="top" align="center">
      <img src="./profile/icons/site.svg" width="56" height="56" alt="" />
    </td>
    <td valign="top">
      <h3 style="margin:0"><a href="https://github.com/vowena/site">vowena/site</a></h3>
      <p>Marketing site at <a href="https://vowena.xyz">vowena.xyz</a>. Landing, pricing, MDX blog with syntax highlighting and dynamic OG images.</p>
      <sub>Next.js 16  ·  Tailwind v4  ·  MDX</sub>
    </td>
  </tr>
  <tr>
    <td valign="top" align="center">
      <img src="./profile/icons/docs.svg" width="56" height="56" alt="" />
    </td>
    <td valign="top">
      <h3 style="margin:0"><a href="https://github.com/vowena/docs">vowena/docs</a></h3>
      <p>Developer documentation at <a href="https://docs.vowena.xyz">docs.vowena.xyz</a>. Concepts, contract reference, SDK guides, dashboard guides.</p>
      <sub>Mintlify  ·  MDX  ·  CC BY 4.0</sub>
    </td>
  </tr>
</table>

<div align="center">
  <img src="./profile/divider.svg" alt="" width="100%" />
</div>

## Network

<table width="100%">
  <tr>
    <td width="50%" valign="top">
      <h4>Stellar testnet  <sub><kbd>live</kbd></sub></h4>
      <pre><code>CCNDNEGYFYKTVBM7T2BEF5YVSKKICE44JOVHT7SAN5YTKHHBFIIEL72T</code></pre>
      <p><a href="https://stellar.expert/explorer/testnet/contract/CCNDNEGYFYKTVBM7T2BEF5YVSKKICE44JOVHT7SAN5YTKHHBFIIEL72T">View on Stellar Expert &rarr;</a></p>
    </td>
    <td width="50%" valign="top">
      <h4>Stellar mainnet  <sub>coming soon</sub></h4>
      <p>Mainnet deployment ships after pilot merchants on testnet validate the billing loop end to end.</p>
      <p><sub>Want to be one of the first merchants? <a href="mailto:hello@vowena.xyz">hello@vowena.xyz</a></sub></p>
    </td>
  </tr>
</table>

<div align="center">
  <img src="./profile/divider.svg" alt="" width="100%" />
</div>

## Community

<table width="100%">
  <tr>
    <td valign="top">
      <h4>Web</h4>
      <p><a href="https://vowena.xyz">vowena.xyz</a><br/><a href="https://docs.vowena.xyz">docs.vowena.xyz</a><br/><a href="https://dashboard.vowena.xyz">dashboard.vowena.xyz</a></p>
    </td>
    <td valign="top">
      <h4>Talk to us</h4>
      <p><a href="https://x.com/vowena">@vowena on X</a><br/><a href="https://github.com/orgs/vowena/discussions">GitHub discussions</a><br/><a href="mailto:hello@vowena.xyz">hello@vowena.xyz</a></p>
    </td>
    <td valign="top">
      <h4>Build with us</h4>
      <p>Every repository accepts issues and PRs.<br/>Pick one and start with <code>good first issue</code>.</p>
    </td>
  </tr>
</table>

<br />

<div align="center">
  <img src="./profile/footer.svg" alt="vowena" width="320" />
</div>

<p align="center">
  Built on <a href="https://stellar.org">Stellar</a>. Powered by <a href="https://stellar.org/soroban">Soroban</a>.<br/>
  <sub>Apache-2.0 licensed. Read the source. Run the keeper. Own your billing.</sub>
</p>
