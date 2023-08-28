# contract-demo-poll

## Install

```bash
./install.sh
./build.sh
```

Optionally install Docker Desktop or Docker Engine to use `hh klaytn-node` and `hh explorer`

## Deploy on local network

### Start a local node

```
hh node
# or
hh klaytn-node
```

### Start a local explorer

```
hh explorer --network localhost
```

### Deploy and interact

```
export HARDHAT_NETWORK=localhost
hh deploy
hh call Poll catVotes
hh send Poll voteCat
hh call Poll catVotes
```

### Run a webapp

```
cd app && npm run dev:localhost
```

then go to <http://127.0.0.1:5173/>

## Deploy on Cypress network

### Prepare a wallet with some KLAY

```
export PRIVATE_KEY=0xabcd..
hh accounts --network cypress
```

### Deploy and interact

```
export HARDHAT_NETWORK=cypress
hh deploy
hh call Poll catVotes
hh send Poll voteCat
hh call Poll catVotes
```

### Run a webapp

```
cd app
vi .env.cypress  # Edit VITE_POLL_CONTRACT
npm run dev:cypress
```

then go to <http://127.0.0.1:5173/>

### Submit source code (verify contract)

```
hh smart-flatten Poll
```

then submit to KlaytnFinder or KlaytnScope

