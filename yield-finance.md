# Yield Farming

## How to Use Farms with BscScan

Since it requires several steps, using Farms with MoonwalkerSwap can seem intimidating at first. This guide will walk you through using the Farms contract directly through BscScan.

{% hint style="warning" %}
Please understand that using BscScan to interact with contracts is not recommended for beginners. If you're not feeling confident, we suggest using the [How to Use Farms guide](https://docs.moonwalker.network/products/yield-farming/how-to-use-farms) instead.
{% endhint %}

### Finding Farm process identifier

To interact correctly with the farming smart contract, you’ll need the matching process identifier (PID) for your LP pair. For now, the easiest way to locate this is to check GitHub.

1. Open the MoonwalkerSwap website’s Farms code on[ GitHub](https://github.com/MoonwalkerSwap/).
2. **Control**/**command** + **F** and search for your pair by ticker (not project name). For example, 'DUST-BNB'.
3. Write down or copy the PID number — in this case 1 —somewhere you can access it easily. You'll need this later.

### Depositing LP Tokens through BscScan

There are a few things involved in depositing LP Tokens using BscScan. We've broken it down into steps to make it easier to follow along.

#### Getting the Main Staking Contract address

The address for the main staking contract is: **0x34c3deb04f6f30fdd8f2eaa52d41b08c2dcb9ae1**

But assuming you'd like to confirm that, visit the MoonwalkerSwap: [Main Staking Contract BscScan page](https://bscscan.com/address/0x34c3deb04f6f30fdd8f2eaa52d41b08c2dcb9ae1). You'll see the address in the top-left. Click the **pages icon** to copy this to clipboard. You'll need it soon.

#### Open the contract for your LP Token

You'll need to approve the smart contract for the LP Token you wish to commit to a farm before you can spend it.

#### From the source code

1. First, [open farms.ts on GitHub](https://github.com/MoonWalkerJim/MoonWalkerSwap-FrontEnd-Main/blob/main/src/config/constants/farms.ts).
2. **Control**/**command** + **F** and search for your pair by ticker (not project name). For example, 'DUST-BNB'
3. When you have the code for the LP pair you're looking for up, find the address after "56:". This will be your contract address.

#### From the UI

1. First, visit the [MoonwalkerSwap Farms page](https://bsc-home.moonwalker.network/farms) and search for your chosen pair using the "SEARCH" field in the top right. We're using DUST-BNB for this example.
2. Click **Details** to expand the row to show more information.
3. Click **View Contract** to open the smart contract on [BSC Scan](https://bscscan.com/).

#### Giving permission to the LP Token contract

Now that you have your LP Token's contract open on [BscScan](https://bscscan.com/), you're going to approve the spending of your LP Tokens into the Farm.

1. On the LP Token's contract page, go to **Contract**, and then **Write Contract**.
2. Click **Connect to Web3** to connect MetaMask.

Confirm the connection.

1. Under function 1, “approve”, you’ll see “spender:address”. Paste in the Main Staking Contract’s contract address you copied to clipboard earlier.
2. You’re also going to need to approve the amount of LP Tokens the contract can spend. In the value field, you’ll need to enter the amount in Wei. You can use the [BscScan Unit Converter](https://www.bscscan.com/unitconverter) to easily change your amount into Wei. Here we'll use 5 CAKE-BUSD LP Tokens.

{% hint style="warning" %}
You can also use `-1` as the value to give unlimited spend approval. This does not mean you will spend everything by default, but only that a transaction of any size using this contract will be allowed by your wallet.
{% endhint %}

1. Click **Write** and accept the action in your MetaMask wallet. You’re now able to commit LP Tokens to the Farm up to the amount you’ve approved.

#### Deposit LP Tokens with the Main Staking Contract smart contract

With the Main Staking Contract now approved to spend your LP Tokens, it's time to make a deposit.

1. Back on the MoonwalkerSwap: Main Staking Contract BscScan page, go to **Contract**, and then **Write Contract**.
2. Click **Connect to Web3** to connect MetaMask.
3. Scroll to function 2, "deposit", and type your PID into the "\_pid" field.

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

1. Underneath \_pid you'll see "\_amount". Enter the amount for the LP contract to spend that you approved earlier.
2. Check the information and click **Write**. Confirm your action in MetaMask.
3. You can confirm your deposit worked by clicking **View your transaction**.

### Withdrawing from a Pool

Withdrawing your LP Tokens from a Pool is very similar to making a deposit. The difference is which function you'll interact with.

1. Back on the MoonwalkerSwap:[ Main Staking Contract BscScan page](https://bscscan.com/address/0x34c3deb04f6f30fdd8f2eaa52d41b08c2dcb9ae1), go to **Contract**, and then **Write Contract**.
2. Click **Connect to Web3** to connect MetaMask.
3. Scroll all the way down to function 15, "withdraw", and type your PID into the "\_pid" field.

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

1. Underneath \_pid you'll see "\_amount". Enter the amount of LP you'd like to withdraw from the Pool.
2. Check the information and click **Write**. Confirm your action in MetaMask.
3. You can confirm your withdrawal worked by clicking **View your transaction**.

### **Making an emergency withdrawal**

‌Using the emergency withdraw function allows you to draw all your funds out of a pool when no other way is working.

{% hint style="danger" %}
**Using the emergency withdraw function will forfeit your DUST rewards!**

The MoonwalkerSwap team strongly suggests avoiding this function unless advised to do so officially by the MoonwalkerSwap team, or if you are very comfortable interacting with smart contracts and understand the underlying code.
{% endhint %}

‌1. On the MoonwalkerSwap: [Main Staking Contract BscScan page](https://bscscan.com/address/0x34c3deb04f6f30fdd8f2eaa52d41b08c2dcb9ae1), go to **Contract**, and then **Write Contract**.

1. Click **Connect to Web3** to connect MetaMask.

‌3. Scroll down to function 4, "emergencyWithdraw", and type your PID into the "\_pid" field.

If you didn't copy down your PID earlier, you can learn how to get it in the **Finding Farm process identifier** section higher up this page.

1. Check the information and click **Write**. Confirm your action in MetaMask.
2. You can confirm your withdrawal worked by clicking **View your transaction**.

## How to Use Farms

![](<.gitbook/assets/Screenshot 2021-09-18 at 20.15.20.png>)

Yield Farming in Farms is a great way to earn DUST rewards on MoonwalkerSwap.

Space Pools, Farms require you to stake **two tokens** to get LP Tokens, which you then stake in the Farm to earn rewards. This lets you earn **DUST** while still keeping a position in your other tokens!

{% hint style="warning" %}
Yield farming can give better rewards than Space Pools, but it comes with a risk of **Impermanent Loss**. It’s not as scary as it sounds, but it is worth learning about the concept before you get started.

Check out this great [article about Impermanent Loss ](https://academy.binance.com/en/articles/impermanent-loss-explained)from Binance Academy to learn more.
{% endhint %}

### Getting prepared

Yield farming takes a little work to get set up.

You’re going to need some "LP Tokens" to enter into a Farm with. Farms can only accept their own exact LP Token; for example, the DUST-BNB Farm will only accept DUST-BNB LP Tokens.

To get the exact LP Token, you'll need to provide liquidity for that trading pair. So to get DUST-BNB LP Tokens, you'll first have to provide liquidity for the DUST-BNB pair.

It may sound intimidating, but it's not too complicated. Let's go through step by step.

#### Finding your Farm

Before you proceed, you'll want to choose a Farm that's right for you. Visit the [Farms page](https://home.moonwalker.network/farms) and you’ll see a list of available Farms.

![](<.gitbook/assets/Screenshot 2021-09-18 at 20.15.20.png>)

DUST-BNB and BUSD-BNB are pinned to the top of the list with the default **Hot** sorting. After the pinned Farms, Hot will show other Farms in order of how new they are.

You can choose another sorting option if you like, such as by **APR** for the Farms with the highest reward rate currently.

When you find a Farm that you'd like to use, note down the trading pair, e.g.DUST-BNB in case you need it later.

#### Providing liquidity to get LP Tokens

Now that you've found a Farm to stake in, you will need to add liquidity to get your LP Tokens.

1. Click on the row of the Farm you've chosen from the list. It will open to show more details.
2. On the left, you'll see some links. Click the **Get (your pair) LP** link.

This will open the Add Liquidity page for your Farm's pair. We have a [guide to adding liquidity ](guides.md#how-to-yield-farm-on-moonwalkerswap)you can follow to get your LP Tokens.

### Putting your LP Tokens into a farm

Now that you have your LP Tokens, you’re ready to start staking them in a Farm and earning rewards!

#### Putting your LP Tokens into the Farm

1. Go back to the [Farms page](https://home.moonwalker.network/farms) and locate your Farm. Click anywhere on the row showing your pair. It will expand to show more details.

![](<.gitbook/assets/Screenshot 2021-09-18 at 20.15.20.png>)

When you’re ready, click the **Enable** button and confirm your action in your wallet.

1. After a short wait, the Enable button will change to **Stake LP**. Click it and a new window will appear.

![](https://lh4.googleusercontent.com/Mpwe28bYv8e3EcbtGRq8ni57u\_UlESPz\_nOqdTPXB-RjZ8ThcgWvUWI8nOGbOgo5d-Mvj7\_a6J\_POtIftVWCCXdDCf3RVhcpq7OYDQOuhFtSLNiupMQaaNQLmgSo1aJMWky-F9Jc)

Type the amount of LP Tokens you would like to farm with into the field, or just click **Max** to use all of your LP Tokens.

1. When you have the amount entered, the **Confirm** button will light up. Click it. Your wallet will ask you to confirm your action.

![](https://lh3.googleusercontent.com/s\_699JBPT7pxQXK1sO0tvkyEawbhEIZcd\_QFd8VGq9glynryO1YpNIjoa4s-nUOxiVuEU-DOTjs3NvSAn6\_jfp-ONULDJczNeubeYU8bqlWtpAhkunlG0L184CoxbaDZVZ8t16C3)

1. After a short wait, the window will close, and you will see your new staked LP Token balance in the details.

![](https://lh3.googleusercontent.com/LatVJszaNP2RwYTf-mNod7AmYa5-y1FafJTnY2I4Nk5tnfR\_7d2b44gwRJqMUGSQy8IKS0TAxmUL0LvUQ7urvBNrsPGc-UWay3WRVDeRCQf\_vIM15j\_FTdXfXb6u4b1S57jExq7F)

### Adding or removing LP Tokens from a Farm

You may decide you would like to add more LP Tokens to a Farm at a later date, or to take some out of a Farm. You can do this very easily whenever you'd like.

1. Return to the Yield [Farms page](https://home.moonwalker.network/farms). At the top of the page you'll see a **Staked only** toggle. Click the toggle.

![](<.gitbook/assets/Screenshot 2021-09-19 at 14.10.33.png>)

You should now only see the pairs you have LP Tokens in on the list, making it easier to find your Farm.

1. Find the Farm you have LP Tokens in, and click the row to view details. You will see a **-** and **+** button on the right-hand side. Click **-** to remove LP Tokens, or **+** to add more LP Tokens.
2. A window will open that looks like the one you used earlier to first stake your LP Tokens. Like last time, type the amount you would like to unstake/stake, or click **Max** to remove/add all available LP Tokens.
3. Make sure your information is correct. When you are ready, click the **Confirm** button and confirm the action in your wallet.
4. After a short wait, your new balance will show in the details section of your LP Token pair. If you've unstaked your LP Tokens, any unharvested rewards you had will automatically have been collected.

### Collecting your farming rewards

Farming will bring you DUST rewards over time. You can collect these rewards and use them to get more LP Tokens, stake them in Space Pools, or anything else you’d like.

#### Returning to your Farm to Harvest

You can harvest your Farm and Space Pool rewards together from the Home page. If you'd like to collect your farming rewards only, follow along.

To collect your rewards, you’ll need to visit your chosen Farm and collect the DUST waiting for you.

1. Return to the [Farms](https://home.moonwalker.network/farm) page here.
2. Find the Farm you staked your LP Tokens in, and click the row to view details. You should see an estimate of your rewards under “Cake earned”.
3. Click the **Harvest** button and confirm the action in your wallet. After a short wait, the DUST will be claimed to your wallet for you to use as you like.

#### How often should I harvest my rewards?

How often you harvest your rewards is up to you, but it does help to remember that there is a small fee involved in harvesting.

You can see this fee in your wallet when confirming after clicking **Harvest**.

This shows the fee for harvesting as it appears in the MetaMask wallet. Different wallets will show the information a little differently. Consider leaving your rewards to grow for a while so you pay fees less often.

And that's all there is to it! You may also want to look at [how to use MoonwalkerSwap Space Pools](https://docs.moonwalker.network/get-started/space-pool-guide) to earn rewards.

Happy farming!

## 🚜 Yield Farming

Yield Farms allow users to earn DUST while supporting MoonwalkerSwap by staking LP Tokens.

Check out our [How to Use Farms guide ](yield-finance.md#how-to-use-farms-with-bscscan)to get started with farming.

Learn [how to find Farm smart contracts](https://app.gitbook.com/s/-MjsHJz3bXkrpWm-4f79/)

{% hint style="warning" %}
Yield farming can give better rewards than Space Pools, but it comes with a risk of **Impermanent Loss**. It’s not as scary as it sounds, but it is worth learning about the concept before you get started.

Check out this great [article about Impermanent Loss ](https://academy.binance.com/en/articles/impermanent-loss-explained)from Binance Academy to learn more.
{% endhint %}

### Reward calculations

Yield Farm APR calculation includes both the rewards earned through providing liquidity and rewards earned staking LP Tokens in the Farm.

Previously, rewards earned by LP Token-holders generated from trading fees were not included in Farm APR calculations. APR calculations now include these rewards, and better reflect the expected APR for Farm pairs.

Below is a basic explanation of how APR is calculated.

In the image above of the WBNB/BUSD pair, we see these values:

**Liquidity:** $387.42M\
**Volume 24H:** $96.97M\
**Volume 7D:** 709.73M

To calculate the APR, first we take the 24hour volume, $96,970,000, and calculate the fee-share of LP-holders, 0.17% \[**$96,970,000\*0.17/100 = $164,849]**.

Next, we estimate the yearly fees based on the 24h volume \[**$164,849\*365 = $60,169,885**].

Now we can calculate the fee APR with yearly fees divided by liquidity \[(**$60,169,885/$387,420,000)\*100 = 15.53%**]

With the fee APR, we can add the fee APR (15.53%) and the Farm staking APR (20.08%) to get the new total APR \[**15.53%+20.08% = 35.61%**].
