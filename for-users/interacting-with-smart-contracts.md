---
description: Use Blockscout to Read and Write to Smart Contracts
---

# Interacting with Smart Contracts

Once a contract is verified, contract methods are exposed and contract interaction is possible directly from Blockscout.

{% hint style="info" %}
In the following examples we use Blockscout on Gnosis Chain. You can interact with verified contracts on any supported chain. Make sure your web3 wallet (like MetaMask) is also connected to that chain when reading / writing to a contract.
{% endhint %}

## Read Contract

Read actions let you check various contract attributes. You will need to connect a web3 wallet to make a query, though a query does not require a transaction or any gas costs.

1\) Find the contract address you want to interact with and enter into the search bar. In this example we search for USDC on Gnosis Chain.

<figure><img src="../.gitbook/assets/USDC-1.png" alt=""><figcaption><p>Search bar results</p></figcaption></figure>

2\) We select the first option in search and are taken to the token page. We can interact from here, but would prefer to see more information about the contract, so we click through to the contract page.

<figure><img src="../.gitbook/assets/USDC-contract-details.png" alt=""><figcaption><p>Read and Write methods are available, but we click on the Contract to see more.</p></figcaption></figure>

3\) Scrolling down past the contract details we see the code is verified by the checkmark:white\_check\_mark:. If the code is not verified, it is not possible to read or write to a contract (unless a verified contract with the same bytecode is located in the Blockscout database. In this case read/write will also be available).

<figure><img src="../.gitbook/assets/code-verified.png" alt=""><figcaption><p>Code is verified</p></figcaption></figure>

4\) We know this is a proxy implementation by the fact that there are options to either read/write to the contract or to the proxy. Proxy means that the contract is upgradeable, and the admin can set a new proxy address for the primary contract if upgrades are required.&#x20;

We will choose to **Read Proxy**, since it contains all the relevant methods for the current contract implementation.

<figure><img src="../.gitbook/assets/read-proxy.png" alt=""><figcaption><p>Read proxy to find relevant methods. Read contract will only show implementation address.</p></figcaption></figure>

5\) We can see the various methods within the proxy contract. Some show current values and others are queryable. An easy example to query is 8) `balanceOf` method.&#x20;

<figure><img src="../.gitbook/assets/balanceOf-1.png" alt=""><figcaption><p>Scroll down to find balanceOf method</p></figcaption></figure>

6\) This method expects an address and will output an integer. Simply paste in an 0x address and press **Query** to see the balance in USDC held by that particular address. If your web3 wallet is not connected at this point, you will be prompted to connect.

<figure><img src="../.gitbook/assets/query-balance.png" alt=""><figcaption><p>Query directly from Blockscout</p></figcaption></figure>

The result shows this address holds 1,000,000 of the token, which converts to 1 USDC. _(Note ERC20 tokens allow for custom decimal point precision. USDC uses 6 decimal precision. Many others use 18 (to denote wei) so be sure to check the token implementation for conversion info)._

## Write Contract

{% hint style="info" %}
Coming Soon :construction\_worker:
{% endhint %}

{% hint style="warning" %}
Many write functions can only be performed by an approved owner. Connect the owner wallet when performing gated functions.&#x20;
{% endhint %}