Steps

``` bash
forge build
source .env
forge create --rpc-url $RPC_URL --private-key $PRIVATE_KEY ERC721Factory --broadcast
# address 0x84C3EDD4f57196BA428858622fba2F95ccdBc527


# TODO after preparing NFT image(s) & JSON metada for upload to Irys
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x84C3EDD4f57196BA428858622fba2F95ccdBc527 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "FestivalNFT" "FEST" "Electronic" "Ultra Miami" "Miami, FL" "2024-03-15" "20:00" "DJ Snake"

cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x84C3EDD4f57196BA428858622fba2F95ccdBc527 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "Ultra Tokyo" "ULTTKY" "Electronic" "Ultra Music Festival" "Tokyo, Japan" "2024-07-20" "18:00" "DJ Kura" && \
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x84C3EDD4f57196BA428858622fba2F95ccdBc527 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "Tomorrowland" "TML" "EDM" "Tomorrowland 2024" "Boom, Belgium" "2024-07-28" "16:00" "Armin van Buuren" && \
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x84C3EDD4f57196BA428858622fba2F95ccdBc527 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "Ibiza Summer Party" "IBZ24" "House" "Sunset Sessions" "Ibiza, Spain" "2024-08-05" "19:30" "Carl Cox"



cast call 0x84C3EDD4f57196BA428858622fba2F95ccdBc527 --rpc-url $RPC_URL "getCollections()"

# ADDRESS goes here

cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY <ADDRESSGOESHERE> "mint(string)" "Woah my vibe is on-chain"


# for subgraph creation
forge inspect ERC721Factory abi > ERC721Factory.json
forge inspect NFTCollection abi > NFTCollection.json

```