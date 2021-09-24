## Hardhat Console

```sh
yarn hardhat console --network localhost
```

### Get "FundingRound" Contract in hardhat console

```ts
const stateStr = fs.readFileSync('state.json').toString();
const state = JSON.parse(stateStr);
let fundingRoundAddress = state.fundingRound
let coordinatorPrivKey = state.coordinatorPrivKey
const coordinatorEthPrivKey = '0x59c6995e998f97a5a0044966f0945389dc9e86dae88c7a8412f4603b6b78690d'
const { Wallet } = require('ethers')
const coordinator = new Wallet(coordinatorEthPrivKey, ethers.provider)
const fundingRound = await ethers.getContractAt('FundingRound',fundingRoundAddress,coordinator)
await fundingRound.maci() // get maci address
```