# 📰 White Paper

### Introduction:

The users of today's centralized social media apps do not truly own the data and value (social relationships, social data, etc.) that they create.

When centralized apps change rules, algorithms, or stop their services, users will lose all their social relationships and data, and the commercial value of social data used by the app is unrelated to users.&#x20;

The <mark style="color:green;">UXUY protocol</mark> will solve this problem, helping users to own their social data through blockchain technology, and make it an asset.

UXUY is committed to becoming the infrastructure of the next generation of large-scale <mark style="color:green;">Web3 social applications</mark>, UXUY is a decentralized social graph protocol with network effects.&#x20;

The UXUY protocol uses "UXUY Token" to record users' contributions to the network constructed by the UXUY protocol.&#x20;

UXUY Token adopts the <mark style="color:green;">POL (Proof of Link)</mark> mechanism, and users can obtain token rewards by building social networks on UXUY, and they can also use tokens to purchase services or applications in other scenarios.

### Features of the UXUY protocol:

1. Supports mainstream Web2 social account login into the Web3 world. Users can create a Web3 account through Google, Twitter, or WeChat accounts, without the need for complex public/private keys, to use and experience Web3 applications, greatly improving user experience.
2. Owns its own relationship network on the blockchain. Create your on-chain identity, <mark style="color:green;">UXUY Profile</mark>, through the UXUY protocol, as an anchor for your self-sovereign decentralized identity, and seamlessly propagate it on the internet. UXUY Profile is a Web3-native way to represent status, affiliation, and social verification.
3. Composable. The true power of the UXUY protocol lies in its robust social network standards, which serve as the foundation for social networks in Web3 and can be combined into any Web3 application.
4. Multi-chain support. The UXUY protocol is already deployed on <mark style="color:green;">Arbitrum</mark> and will soon support more ecosystems.

### I. The UXUY protocol is a plug-in identity verification infrastructure for Web3 applications.

<figure><img src="../.gitbook/assets/whitepaper_01.jpg" alt=""><figcaption><p>I</p></figcaption></figure>

### II. The token reward mechanism of UXUY Token.

UXUY Token adopts the <mark style="color:green;">POL (Proof of Link)</mark> mechanism, which rewards contributors to the construction of the Web3 social network. Anyone can mint their own UXUY Token through their social network, and UXUY Token can be stored in an Ethereum-compatible crypto wallet. Users can earn a certain amount of UXUY Token rewards for successfully connecting to a social node. The amount of UXUY Token rewards is affected by some variables, and the formula is as follows:

{% code overflow="wrap" %}
```vue
 Rewards = OG * [ TAM(ts) * (1 + EAR（cLg）)* cLu / log2(cLg) ]
```
{% endcode %}

#### Explanation:

* TAM(ts0) = <mark style="color:green;">max(3000 - \[(ts0 - tsG)/3600\*24], 1)</mark>
* EAR(cLg) = <mark style="color:green;">max((k/100) - 0.001 \* \[cLg / 100000], 0)</mark>
* OG - Users holding <mark style="background-color:green;">SEAMAN NFTs</mark> are OG users, and their incentive weighting coefficient is <mark style="color:green;">120%</mark>.
* TAM - Time amplifier, early participants' incentives.
* EAR - Early Adopter Reward, early contributors' incentives.
  * For networks with <mark style="color:green;">0-100,000</mark> people, the EAR incentive coefficient starts at 90%.&#x20;
  * For networks with <mark style="color:green;">100,000-1 million</mark> people, the EAR incentive coefficient starts at 30%.&#x20;
  * After <mark style="color:green;">1 million</mark> people, the EAR incentive coefficient drops to 10%.&#x20;
  * And linearly decreases by <mark style="color:green;">0.1%</mark> every <mark style="color:green;">100,000</mark> people.
  * k - EAR incentive coefficient:
    * _<mark style="color:green;">`[cLg < 100,000, k=40].`</mark>_
    * _<mark style="color:green;">`[10 < cLg < 1 million, k=20].`</mark>_
    * _<mark style="color:green;">`[cLg > 1 million, k=10].`</mark>_\

* ts0 - the current node's establishment time.
* tsG - the project's genesis release start time.
* cLu - the number of people who established the node.
* cLg - the total number of people in the UXUY network.
* When <mark style="color:green;">cLg >= 30 million</mark>, Rewards = 0, i.e., no new UXUY Tokens are generated when the network is built to 3<mark style="color:green;">0 million</mark>.

### III. The token burn mechanism of UXUY Token.

UXUY Token is the application token of the UXUY network, which can be used for on-chain payments, transfers, social network reading, and other behaviors' on-chain fees. <mark style="color:green;">15%</mark> of on-chain revenue will be burned.

### Summary:

UXUY is a blockchain-based social protocol that aims to achieve a more fair, transparent, and decentralized social experience. The protocol adopts a token called "UXUY Token," which users can earn token rewards by building social network nodes under the UXUY protocol, and can also use tokens to purchase services or goods. UXUY's token reward mechanism is fair, transparent, and decentralized, and we call it the <mark style="color:green;">POL (Proof of Link)</mark> mechanism.



