# Info

My tests to set up and use cross chain transfers using Celer Network infrastructure.
Consists of two branches: `main` and `dev`, and sounds like `dev` is newer than `main`.

Last commit to `main` was made on March 17, 2023.

Last commit to `dev` was made on April 26, 2023.

## The latest app state I remember

Well, it was definitely possible to transfer tokens across netwroks set up. To make it running, if I remember correct, I had to deploy bridges on different networks, set up them, plus set up an app from Celer (files in `executor` config, 2 configurations are included). This Celer's app should have been running, and then, when one bridge emits "transfer" event (or so), Celer's app runs and proceeds the request.

## Strategy used for transfers

`CC transfer to be used - "burn and mint", with neither "source" nor "pegged" contract, and each chain will have its own range of ids. (later)` as it's mentioned in `ERC721CelerCrossChain.sol` file.

## Overall understanding

Well, everything's quite sipmle:
- first, you emit specific events on source chain;
- then your background service (some node.js or python script) takes your event, parses, validates, and proceeds;
- in the end, the destination bridge receives a transaction, verifies it, and if ok, then does the job (mints tokens).

Probably, Celer Network is used somehow to ... (what reason?) verify the data? Submit transactions? Idk. Do some majic.

### P.s

Some contract addresses are left, so you may search by them through the repo to better understand, which entity and how is used and set up somewhere.

Keys and passwords, that I've used, are replaced with some dummy values.

<hr />

# COPYING AND RUNNIG THE CODE IS AT YOUR OWN RISK!

and don't forget to add a `star` to this repo :)