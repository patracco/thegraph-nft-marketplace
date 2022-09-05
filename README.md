# ABI

When init with The Graph, the ABI is auto created if you verified your contract with Etherscan. Otherwise, you'll have to copy/paste or import manually.

# Schema

Create a schema for each entity that we want to query.

# codegen

- every time you update schema.graphql, run "graph codegen"

# mapping

Active Item is going to be the result of a function that involves ItemListed, ItemCanceled and ItemBought.

- src/mapping.ts is where we keep track of all the events. NOTE: renamed to mapping from auto-generated nft-marketplace name

# subgraph.yalm

- added "startBlock", otherwise the graph will start indexing events since the beginning of the Ethereum network. It will take a long time and we don't want that. Instead, we want it to start indexing from right before we deployed the NftMarketplace contract
- ti find the block, use Etherscan withe the contract address and copy/paste the block number - 1 (right before)
