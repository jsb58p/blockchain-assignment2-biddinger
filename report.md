### Part A - Deployment

<br>

- Contract address: 0x5fbdb2315678afecb367f032d93f642f64180aa3

- Symbol: CAMP

- Decimals: 18

- Initial supply:

  - Raw: 100000000000000000000

  - Human: 100 (Raw/10^18)

- Compiler version (0.8.28)
 
- Scripts used:

  - scripts/deploy.ts scripts/interact.ts, scripts/analyze.ts

![deploy.ts](https://github.com/jsb58p/blockchain-assignment2-biddinger/blob/main/screenshots/screenshot2(npx%20hardhat%20run%20deploy.ts%20--network%20localhost).png)

  - scripts/interact.ts

![interact.ts](https://github.com/jsb58p/blockchain-assignment2-biddinger/blob/main/screenshots/screenshot3(npx%20hardhat%20run%20interact.ts%20--network%20localhost).png)
 
  - scripts/analyze (shown below)

<br>

### Part B - Transaction Details (tx1/tx2/tx3)

<br>

- tx1

```bash

===0x5e983d095a7f44fc64a7fa3d26f48c95c7e56626eb5558b4eacea7f7cb422f5d ===
Status: Success
Block: 2n
Timestamp (UTC): 2025-09-17T13:54:40.000Z
From: 0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266
To: 0x5fbdb2315678afecb367f032d93f642f64180aa3
Nonce: 1
Gas limit: 29975n
Gas used: 26925n
Base fee per gas: 769569727n
Max fee per gas: 20000000000n
Max priority fee per gas: 1000000000n
Effective gas price: 1769569727n
Total fee (wei): 47645664899475n
Event: Transfer {
  from: '0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266',
  to: '0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266',
  value: 100000000000000000000n
}

```

![tx1](https://github.com/jsb58p/blockchain-assignment2-biddinger/blob/main/screenshots/screenshot4(npx%20hardhat%20run%20analyze.ts%20--network%20localhost%201).png)

Human Value: 100

---
<br>

- tx2

```bash
=== 0xee3ddd33e2a799fd032fc8469decfbb275e1dff220c9b8c543f35fcbbadb6624 ===
Status: Success
Block: 3n
Timestamp (UTC): 2025-09-17T13:54:41.000Z
From: 0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266
To: 0x5fbdb2315678afecb367f032d93f642f64180aa3
Nonce: 2
Gas limit: 29975n
Gas used: 26925n
Base fee per gas: 673546184n
Max fee per gas: 22000000000n
Max priority fee per gas: 3000000000n
Effective gas price: 3673546184n
Total fee (wei): 98910231004200n
Event: Transfer {
  from: '0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266',
  to: '0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266',
  value: 50000000000000000000n
}
```

![tx2](https://github.com/jsb58p/blockchain-assignment2-biddinger/blob/main/screenshots/screenshot4(npx%20hardhat%20run%20analyze.ts%20--network%20localhost%202).png)

Human Value: 50

---
<br>

- tx3

```bash
=== 0xdf05f0b8b30e2b490fa29aa84f3c0fea05ed2ac529978b27a111eaa1bf569214 ===
Status: Success
Block: 4n
Timestamp (UTC): 2025-09-17T13:54:42.000Z
From: 0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266
To: 0x5fbdb2315678afecb367f032d93f642f64180aa3
Nonce: 3
Gas limit: 46378n
Gas used: 46378n
Base fee per gas: 589504038n
Max fee per gas: 21000000000n
Max priority fee per gas: 2000000000n
Effective gas price: 2589504038n
Total fee (wei): 120096018274364n
Event: Approval {
  owner: '0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266',
  spender: '0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266',
  value: 25000000000000000000n
}
```
![tx3](https://github.com/jsb58p/blockchain-assignment2-biddinger/blob/main/screenshots/screenshot4(npx%20hardhat%20run%20analyze.ts%20--network%20localhost%203).png)

Human Value: 25

<br>

---
### Part C - Fee Comparison (tx1 vs tx2)

<br>

- Which landed first:
  - tx1: Timestamp (UTC): 2025-09-17T13:54:40.000Z
  - tx2: Timestamp (UTC): 2025-09-17T13:54:41.000Z
  - **tx1 (Block 2) landed before tx2 (Block 3)**
 
- Which had higher effective gas price and priority tip?
  - Higher effective gas price:
    - tx1: Effective gas price: 1769569727n
    - tx2: Effective gas price: 3673546184n
    - **tx2 has the higher effective gas price**

  <br>

  - Higher priority tip:
    - tx1: Max priority fee per gas: 1000000000n
    - tx2: Max priority fee per gas: 3000000000n
    -  **tx2 has the higher priority tip**

<br>

  - Brief EIP-1559 explanation:
    - EIP-1559 is a protocol upgrade that:
      -  dynamically adjusts the base fee each block based on network congestion (block fullness).

      - Burns the base fee to reduce supply.

      - Lets users set a priority tip to incentivize miners to prioritize their transactions.
    - This system improves fee predictability, helps reduce ETH supply, and stabilizes gas prices.

## Part D - Decimals & Conversions

<br>

- Example of raw vs human for tx1:
  - raw value: 100000000000000000000n
  - human value = raw value / 10^18
  - 100000000000000000000 / 10^18 = **100** human value
