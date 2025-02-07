Steps

``` bash
forge build
source .env
forge create --rpc-url $RPC_URL --private-key $PRIVATE_KEY ERC721Factory --broadcast
# address 0x84C3EDD4f57196BA428858622fba2F95ccdBc527


# TODO after preparing NFT image(s) & JSON metada for upload to Irys
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x84C3EDD4f57196BA428858622fba2F95ccdBc527 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "MyCollection" "MCOL" "Electronic" "Summer Festival" "Los Angeles" "2024-09-15" "18:00" "DJ Alex"

# ADDRESS goes here

cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY <ADDRESSGOESHERE> "mint(string)" "Woah my vibe is on-chain"


# for subgraph creation
forge inspect ERC721Factory abi > ERC721Factory.json
forge inspect NFTCollection abi > NFTCollection.json

```