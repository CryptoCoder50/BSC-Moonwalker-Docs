# IFO-Inital Farm Offering

## Contract Details

Each IFO will have a different smart contract for the particular IFO event. You can find the IFO's smart contract link on the[ MoonwalkerSwap IFO page](https://bsc-home.moonwalker.network/ifo). The link will take you to IFO's contract page on BscScan.

## How to Participate in an IFO with BscScan

Joining IFOs can be exciting and very rewarding. The [MoonwalkerSwap website’s IFO](https://bsc-home.moonwalker.network/ifo) page is an easy way to join an IFO. But some users may prefer to interact directly with smart contracts on the BscScan website. Using BscScan will let you see a contract's code, review its analytics and events in real-time, and find other useful information.

Currently, only MetaMask or WalletConnect wallets can interact directly with BscScan. WalletConnect is still in beta, so for now we recommend using MetaMask.

{% hint style="warning" %}
Interacting directly with smart contracts is not something we’d recommend to beginners. If you’d like to join an IFO without the complicated steps, we have a [How to Participate in an IFO guide](ifo-inital-farm-offering.md#how-to-participate-in-an-ifo) to help you through the process using the MoonwalkerSwap website.
{% endhint %}

### Before the IFO

Before you can join an IFO there are a few things you will need to do to get ready. Follow the steps below to make sure you're ready to buy when the IFO event goes live.

#### Get DUST-BNB Liquidity Tokens

### Once the IFO is live

While an IFO is live, you will have 1 hour to participate. If you have prepared your DUST-BNB LP Tokens it doesn’t take long at all to buy the new token.

#### Getting the IFO’s smart contract address

You’re going to need the IFO’s smart contract address to join the IFO. You can find a link to the contract’s BscScan page on the IFO page of the [MoonwalkerSwap website](https://bsc-home.moonwalker.network/ifo) underneath the Unlimited Sale section.

On the contract page, in the top-left area you’ll find the contract address. Copy the address to clipboard.

#### Approving the IFO contract

Before you’re able to spend into the IFO, you’ll need to approve the contract spending your LP Tokens.

1. Open a new tab and visit the [MoonwalkerSwap LP BscScan contract page](https://bscscan.com/address/0x0ed7e52944161450477ee417de9cd3a859b14fd0#writeContract) and make sure you’re on **Contract**, **Write Contract**.
2. Click **Connect to Web3** to connect MetaMask.

Confirm the connection.

1. Under function 1, “approve”, you’ll see “spender:address”. Paste the IFO’s contract address you copied to clipboard earlier.
2. You’re also going to need to approve the amount of LP Tokens the contract can spend. In the value field, you’ll need to enter the amount in Wei. You can use the [BscScan Unit Converter](https://www.bscscan.com/unitconverter) to easily change your amount into Wei.
3. Click **Write** and accept the action in your MetaMask wallet. You’re now able to buy into the IFO up to the amount you’ve approved.

#### Buying into the IFO’s Basic Sale

Now that you’ve approved the IFO to spend your Moonwalker LP Tokens, you’re ready to buy into the IFO.

1. Go back to the tab you have open with the IFO contract. Click onto **Contract**, and then onto **Write Contract**.
2. Under function 1, depositPool, you’ll see “\_amount”. Type or paste your Wei value from before into the field.
3. Under the \_amount field you’ll see “\_pid”. This will tell the contract which sale you want to buy into between the Basic Sale and Unlimited Sale. If you’re not sure which sale to choose, you can read about them in [How to Participate in an IFO guide](https://docs.pancakeswap.finance/get-started/ifo-guide#which-type-of-sale-should-i-choose-basic-or-unlimited).

To buy into the Basic Sale, type 0 into the \_pid field.

1. Check you typed the right information then click the **Write** button. Confirm your action in MetaMask.
2. A **View your transaction** button will appear. You can click the button to view your transaction on the BscScan explorer to confirm it worked.

You can also check the IFO page on MoonwalkerSwap’s website to see your deposit.

#### Buying into the IFO’s Unlimited Sale

1. To buy into the Unlimited Sale, follow the same steps as in the Basic Sale until you are entering an amount into the “\_pid” field of the IFO contract.
2. Here, instead of typing 0, type 1. This will deposit your funds into the Unlimited Sale. From here click **Write** and confirm your action in MetaMask.
3. You can click **View your transaction**, or visit the MoonwalkerSwap IFO page to confirm your transaction.

### After the IFO has ended

When the IFO has ended, you will be able to collect your new tokens. How many you will get depends on how many people participated in the IFO. Any extra LP Tokens you have committed to the IFO that aren't used to buy new tokens will be returned to you.‌

#### Collecting your new tokens

1. To collect your new tokens, you’ll need to visit the IFO contract page on BscScan, and click **Contract**, then **Write Contract**.
2. You’ll have to connect MetaMask to WEB3 by clicking on **Connect to Web3**. Confirm the action with MetaMask.
3. Scroll down to function 3, harvestPool. Here you’ll find “\_pid” and a field to type into. Just like earlier, you can type 0 to collect your tokens from the Basic Sale, and 1 to collect your tokens from the Unlimited Sale.

Type 0 or 1 and click **Write**. Confirm your action in MetaMask.

1. You can click **View your transaction** or visit the PancakeSwap IFO page to confirm your tokens have been collected.

All done! Your new IFO tokens will be in your wallet, and any unspent LP Tokens will be returned to you.

## How to Participate in an IFO

An IFO on MoonwalkerSwap is an Initial Farm Offering. IFOs let you get early access to MoonwalkerSwap’s new tokens as soon as they are added. By being one of the first to have a new token, you can benefit from higher rewards!

IFOs are available for a very limited time. Get ready ahead of the event to make sure you can participate!

### **Before the IFO**

Before you can join an IFO there are a few things you will need to do to get ready. Follow the steps below to make sure you're ready to buy when the IFO event goes live.

#### Create your MoonwalkerSwap profile

To take part in an IFO, you'll need a MoonwalkerSwap profile. Having a profile protects the security of the IFO and makes it fair for everyone. The small cost of a profile also helps keep the total DUST supply down by burning a little DUST from each profile created.

#### Get DUST-BNB Liquidity Tokens

Once you have a profile, you will also need to provide liquidity to get some DUST-BNB LP Tokens. These will be used to buy the tokens being offered in the IFO.

To provide liquidity and get some DUST-BNB LP Tokens, you can follow our How to Add/Remove Liquidity guide [here](moonwalkerswap-exchanges.md#how-to-add-remove-liquidity).

#### Check on your progress

Once you’ve followed the steps above, go back to the IFO page [here](https://home.moonwalker.network/ifo). Scroll down to the coloured ‘How to Take Part’ section.

_\*\*_![](https://lh5.googleusercontent.com/7Bh78UrDgqLpgsIjtAuX8UFkd8aG7-J3gsp36xGsCG0kPrkYckmy6UgTKQZfUJEkIMccixBdrhVUVmv2kJfnVGq9Vljb\_AXetLk89YzBIiSBPSGaIA-v2vRImzvNrFOnJWQWle-S)

_\*\*_You should see your progress at step 3, Commit LP Tokens, like in the picture above. If for some reason you aren’t at step 3, go back through the guides linked up higher in this page.

And that’s it; you’re now ready to participate in an IFO when it goes live!

#### **Knowing when an IFO will start**

The IFO is a limited time event, only lasting one hour. You'll want to check the time to make sure you don’t miss out!

**Check the IFO page**

IFOs will have a countdown at the top of the IFO page.

The **(blocks)** link will open the BscScan explorer in a new window at the starting block.

**Use social media**

There isn’t a set time before an IFO goes live for the countdown to start, so check PancakeSwap’s official social media accounts for news about upcoming IFO times.

The countdown and announcements will give you plenty of time to prepare.

### **Once the IFO is live**

While an IFO is live, you will have 1 hour to participate. If you have prepared your CAKE-BNB LP Tokens it doesn’t take long at all to buy the new token.

#### Checking the IFO is live

On the IFO page, look where the event start countdown was. You will now see a countdown until the IFO sale ends instead. This will let you know how much time you have to buy the offered tokens.

#### **Which type of sale should I choose: Basic or Unlimited?**

There are two sales available: Basic Sale and Unlimited Sale. It's possible to participate in both sales if you want to, but each has conditions. You will need to choose which sale you would like to participate in.

**Basic Sale**

The Basic Sale has a limited buy amount per user (about $100 USD in CAKE-BNB LP Tokens). Anyone can participate in the Basic Sale, and there are no fees to buy tokens this way.

**Unlimited Sale**

The Unlimited Sale has no limit on the amount of tokens a user can buy. If you buy tokens with the Unlimited Sale you will have to pay a small fee.

You can buy tokens from both sales, but the Basic Sale is limited. If you only want a small amount of tokens we recommend using the Basic Sale.

#### **Committing tokens to the Basic Sale**

1. Let's commit some LP Tokens to the Basic Sale. Click **Commit LP Tokens** button under Basic Sale. A window will appear.
2. In the new window, type your amount of LP Tokens into the field.

Remember, the Basic Sale has a limit of about $100 USD. Any LP Tokens you cannot spend on new tokens will be returned to you, so you don’t need to worry about losing any tokens.

1. Click the **Confirm** button and confirm the action with your wallet. Once your LP Tokens are committed, the Basic Sale section will show your committed amount under “Your LP Tokens Committed”.

You can add more LP Tokens at any time during the IFO event as long as you haven’t reached the maximum. If you have, you will see "Max Committed" on the faded button.

If you don’t want to commit more LP Tokens to the IFO, you can skip ahead to the next section, Collecting your new tokens.

#### **Committing LP Tokens to the Unlimited Sale**

1. To use your LP Tokens in the Unlimited Sale, click the **Commit LP Tokens** button under Unlimited Sale. A window will appear.
2. In the new window, type your amount of LP Tokens into the field.

There is no limit to the LP Tokens you can commit to the Unlimited Sale. Even so, if you add more than you are able to spend on new tokens, your extra LP Tokens will be returned to you. You don’t need to worry about losing any tokens.

1. Click the **Confirm** button and confirm the action with your wallet. Once your LP Tokens are committed, the Unlimited Sale section will show your committed amount under “Your LP Tokens Committed”.

You can add more LP Tokens at any time during the IFO event as long as you have the funds. Keep in mind there is a fee for the Unlimited Sale, listed next to “Additional fee”.

### After the IFO has ended

When the IFO has ended, you will be able to collect your new tokens. How many you will get depends on how many people participated in the IFO. Any extra LP Tokens you have committed to the IFO that aren't used to buy new tokens will be returned to you.‌

#### **Collecting your new tokens**

Collecting your new tokens is incredibly easy. Just go back to the IFO page once the IFO event is finished and click the **Claim Tokens** button under Basic Sale, and if you’ve used it, Unlimited Sale too.

Confirm the action with your wallet. You'll now have your new tokens. Congratulations!

#### Using your new tokens in farms

Now that you've got your shiny new tokens, you can put them to work for you!

You can add liquidity for your token to receive LP Tokens. Your LP Tokens will let you collect trading fees for your pair. Read about adding liquidity [here](moonwalkerswap-exchanges.md#how-to-add-remove-liquidity).

If you've added liquidity for your new token, you can also use your new LP Tokens to yield farm and earn more rewards! Read about farming[ here](yield-finance.md#how-to-use-farms-with-bscscan).



Buy new tokens using DUST-BNB LP tokens.

The project gets the BNB, MoonwalkerSwap burns the DUST. **You get the tokens.**

1. **You will need DUST-BNB LP tokens** to participate.
2. **DUST tokens equating to half of the total funds raised will be burned forever**: For example, if the full $1,000,000 USD allocation is raised, then _\*\*_$500,000 of DUST tokens will be burned.

Learn how to find IFO smart contracts

### **How to participate in an IFO**

Visit [https://home.moonwalker.network/ifo](https://pancakeswap.finance/ifo) to find out more about IFOs.

Get [DUST-BNB LP](https://home.moonwalker.network/farms) tokens by adding DUST and BNB liquidity

During Sale:

1. While the sale is live, commit your DUST-BNB LP tokens to buy the IFO tokens at [https://home.moonwalker.network/ifo](https://home.moonwalker.network/ifo)

After Sale:

1. When the sale is complete, claim the IFO tokens you've bought. Your unspent funds will also be sent back to you.
2. Done! In the case of an overflow you can unstake your remaining DUST-BNB LP tokens.

{% hint style="info" %}
If you decide to acquire DUST-BNB LP tokens before the IFO starts, you can stake them in the [DUST-BNB Farm](https://pancakeswap.finance/farms) to earn DUST token rewards while waiting for the sale.
{% endhint %}

{% hint style="warning" %}
While you are holding DUST-BNB LP tokens you will be at risk of [Impermanent Loss](https://academy.binance.com/en/articles/impermanent-loss-explained).
{% endhint %}

### **What is the “Overflow” sale method?** <a href="#overflow" id="overflow"></a>

&#x20;Basically, the more you put in, the more you will get, and you’ll get back anything that doesn’t get spent.

In the “Overflow” method, users can subscribe as much or as little as they want to the IFO, and their final allocation will be based on the amount of funds they put in as a percentage of all funds put in by other users at the time the sale ends. Users will receive back any leftover funds when they claim their tokens after the sale.

{% hint style="warning" %}
It's possible to receive no tokens at all: If you commit a very small amount of LP tokens compared to the total amount committed by others, your contribution may be such a small part of the total that you may not qualify for even a small portion of the tokens sold.\
In such a case, you will still be able to reclaim all the DUST-BNB LP tokens you committed.
{% endhint %}

### What happens if the IFO doesn't raise all the funds targeted?

The sale will proceed as normal, and all funds contributed will be spent.

### Want to launch your own IFO?

Launch your project with MoonwalkerSwap, Binance Smart Chain’s most-used AMM project and liquidity provider, to bring your token directly to the most active and rapidly growing community on BSC.

[\*\*\*\*Apply to launch](https://form.jotform.com/212606130120031)
