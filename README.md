Steps

``` bash
forge build
source .env
forge create --rpc-url $RPC_URL --private-key $PRIVATE_KEY ERC721Factory --broadcast
# factory address goes here
# 0x14FB9F2466889F35292f0d32AF572ba6D5Ed7820


# for subgraph creation
#######################
forge inspect ERC721Factory abi > /Users/paka/code/vibesync-subgraph/abis/ERC721Factory.json
forge inspect NFTCollection abi > /Users/paka/code/vibesync-subgraph/abis/NFTCollection.json


# TODO after preparing NFT image(s) & JSON metada for upload to Irys
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x14FB9F2466889F35292f0d32AF572ba6D5Ed7820 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "FestivalNFT" "FEST" "Electronic" "Ultra Miami" "Miami, FL" "2024-03-15" "20:00" "DJ Snake"

cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x14FB9F2466889F35292f0d32AF572ba6D5Ed7820 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "Ultra Tokyo" "ULTTKY" "Electronic" "Ultra Music Festival" "Tokyo, Japan" "2024-07-20" "18:00" "DJ Kura" && \
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x14FB9F2466889F35292f0d32AF572ba6D5Ed7820 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "Tomorrowland" "TML" "EDM" "Tomorrowland 2024" "Boom, Belgium" "2024-07-28" "16:00" "Armin van Buuren" && \
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x14FB9F2466889F35292f0d32AF572ba6D5Ed7820 \
    "createCollection(string,string,string,string,string,string,string,string)" \
    "Ibiza Summer Party" "IBZ24" "House" "Sunset Sessions" "Ibiza, Spain" "2024-08-05" "19:30" "Carl Cox"



cast call 0x14FB9F2466889F35292f0d32AF572ba6D5Ed7820 --rpc-url $RPC_URL "getCollections()"


cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY 0x1A4CeB775616a53E6a1BB7F701E6a2dA9e02E6b1 \
    "mint(string,string)" "testing another link" "https://devnet.irys.xyz/tx/94TNg3UUKyZ96Dj8eSo9DVkBiivAz9jT39jjMFeTFvm3/data"



# Update subgraph with factory address
# rebuild and deploy





# TO FIX
#######
irys balance $PRIVATE_KEY -t base-eth -n testnet --provider-url https://sepolia.base.org


irys fund 1000000000000000 \
  -n base-sepolia \
  -t base-eth \
  -w $PRIVATE_KEY \
  --provider-url https://rpc.sepolia.dev










```