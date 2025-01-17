# Aavegotchi Autopet

This service will pet your [Aavegotchi](https://aavegotchi.com) twice daily. Get started:

- If you can, send 1 MATIC donation to the [AutoPetAddress](https://polygonscan.com/address/0x183f37551d5986d5c2b324db351a21687c4dc307) (this should cover >100 days gas costs)
- Set the AutoPetAddress as a PetOperator for your gotchi (see below)
- Make a commit to index.ts (or raise an issue) with your gotchi id

AutoPetAddress: 0x183f37551d5986d5c2b324db351a21687c4dc307

> This is a beta service and it might break. Limited to 10 gotchis for now.

### PetOperator

You must approve the autopet as a PetOperator for your gotchi. You can approve a new PetOperator for your gotchi via the [AavegotchiFacet](https://louper.dev/?address=0x86935F11C86623deC8a25696E1C19a8659CbF95d&network=polygon) (you'll need to call `setPetOperatorForAll` directly on the diamond contract `0x86935f11c86623dec8a25696e1c19a8659cbf95d` which can be done via [louper.dev](https://louper.dev/?address=0x86935F11C86623deC8a25696E1C19a8659CbF95d&network=polygon)).

The PetOperator can't do anything else other than pet your gotchi. You can still continue to pet your gotchi manually if you wish. Take care when making transactions, dyor, not financial advice etc.

### Forking

If you want to run this script yourself you could fork the repo and run the action on Github. You could also run this script from the terminal or run it on a schedule (e.g. AWS lambda).

### Running via Github action

- Fork the repo
- Update the `TOKEN_IDS` variable in `index.js/ts` to include your gotchis
- Set a new secret on the repo called `PrivateKey` which is the private key of the PetOperator with funds to cover gas costs

### Running locally

- Set the following environment variables:

```bash
PRIVATE_KEY=0x46453... # private key of the pet operator with funds to cover gas costs
```

### Compilation

Use TSC to compile `index.ts` to javascript:

```
yarn tsc index.ts
```

### Run

Run the script with node:

```
node index.js
```
