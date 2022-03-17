## Sentry setup

### Run script bellow to prepare your RPC server
```
wget -O archway_devnet.sh https://raw.githubusercontent.com/kj89/testnet_manuals/main/archway/archway_devnet.sh && chmod +x archway_devnet.sh && ./archway_devnet.sh
```

## Create wallet
save mnemonic from output!
```
archwayd keys add $ARCHWAY_WALLET
```

Save wallet information to variables (optional)
```
ARCHWAY_ADDR=$(archwayd keys show $ARCHWAY_WALLET -a)
ARCHWAY_VALOPER=$(archwayd keys show $ARCHWAY_WALLET --bech val -a)
echo 'export ARCHWAY_ADDR='${ARCHWAY_ADDR} >> $HOME/.bash_profile
echo 'export ARCHWAY_VALOPER='${ARCHWAY_VALOPER} >> $HOME/.bash_profile
source $HOME/.bash_profile
```

## Usefull commands

To check sync status
```
curl -s localhost:26657/status | jq .result | jq .sync_info
```

To view logs
```
docker logs -f archway --tail 100
```

To stop
```
docker stop archway
```

To start
```
docker start archway
```

To restart
```
docker restart archway
```