# Substrate funding service

## Installing and running

create `.env` file with following content:

```
URL=wss://substrate01.threefold.io
MNEMONIC=substrate ed25519 private words
KYC_PUBLIC_KEY=kyc service 25119 public key
ACTIVATION_AMOUNT=1
```

Run backend

```
yarn
yarn start
```

## Endpoints

### Activate

`/activation/activate`

Activates a Substrate account and puts 500 tokens on it.

Example: Post to `localhost:3000/activation/activate`

```sh
curl --header "Content-Type: application/json" \
  --request POST \
  --data '{"substrateAccountID": "some_id"}' \
  http://localhost:3000/activation/activate
```

### Create Entity

`/activation/create-entity`

Creates an entity object in the griddb.

## KYC

The KYC signature is currently not validated 


## Deployment

Build the docker image and configure following environment variables:

```
MNEMONIC=mnemonic words for account that activates
URL=substrate websocket url
```