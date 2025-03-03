NEAR Staking Pool Details
=================================

Contract migrated from `name.near` to `pool-details.near`

----

[![Open in Gitpod!](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/zavodil/near-pool-details)

<!-- MAGIC COMMENT: DO NOT DELETE! Everything above this line is hidden on NEAR Examples page -->

## Description

Add details about your whitelisted staking pool on NEAR blockchain.

Current contract address in NEAR Mainnet: [`pool-details.near`](https://explorer.near.org/accounts/pool-details.near) 

Check output: [zavodil.near.page/?pools](https://zavodil.near.page/?pools)

## Available methods

- update_field '{"pool_id": "`<<YOUR_POOL>>`", "name": "`<<FIELD_NAME>>`", "value": "`<<VALUE>>`"}' --accountId=`<<YOUR_POOL_OWNER_ACCOUNT_ID>>` --gas=200000000000000

Please find list of suggested field names in [FIELDS.md](https://github.com/zavodil/near-pool-details/blob/master/FIELDS.md) 
- get_all_fields '{"from_index": 0, "limit": 100}'
- get_fields_by_pool '{"pool_id": "`<<YOUR_POOL>>`"}' 
- get_num_pools

## Examples

```
near call name.near update_field '{"pool_id": "zavodil.poolv1.near", "name": "url", "value": "https://zavodil.ru"}' --accountId=zavodil.near  --gas=200000000000000

near call name.near update_field '{"pool_id": "zavodil.poolv1.near", "name": "twitter", "value": "zavodil_ru"}' --accountId=zavodil.near  --gas=200000000000000

near view  name.near get_all_fields '{"from_index": 0, "limit": 3}'

near view  name.near get_fields_by_pool '{"pool_id": "zavodil.poolv1.near"}' 

```

## To Run
Open in the Gitpod link above or clone the repository.

```
git clone https://github.com/zavodil/near-pool-details
```


## Setup [Or skip to Login if in Gitpod](#login)
Install dependencies:

```
yarn
```

If you don't have `Rust` installed, complete the following 3 steps:

1) Install Rustup by running:

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

([Taken from official installation guide](https://www.rust-lang.org/tools/install))

2) Configure your current shell by running:

```
source $HOME/.cargo/env
```

3) Add wasm target to your toolchain by running:

```
rustup target add wasm32-unknown-unknown
```

Next, make sure you have `near-cli` by running:

```
near --version
```

If you need to install `near-cli`:

```
npm install near-cli -g
```

## Login
If you do not have a NEAR account, please create one with [NEAR Wallet](https://wallet.near.org).

In the project root, login with `near-cli` by following the instructions after this command:

```
near login
```

Modify the top of `src/config.js`, changing the `CONTRACT_NAME` to be the NEAR account that was just used to log in.

```javascript
…
const CONTRACT_NAME = 'YOUR_ACCOUNT_NAME_HERE'; /* TODO: fill this in! */
…
```

Build

```
yarn build
```

Deploy

```
yarn deploy
```

## To Explore

- `contract/src/lib.rs` for the contract code
