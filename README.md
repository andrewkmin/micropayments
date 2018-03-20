# Micropayments
## Issue
The pay-for-content business model has been a tough problem to crack for many content providers. Such content providers, usually for-profit publications such as the New York Times, Financial Times, Wall Street Journal, and many others, want to get as many eyeballs as possible, and convert them into subscribers that'll pay a monthly rate to enjoy their exclusive content. On the other hand, while there is a substantial number of consumers who do pay via subscription-based model, there are others like myself who don't find it quite worthwhile to pay, say $10/month, for a site that I'd only ever visit a few times. At the same time, I've been sent articles many times, only to have my excitement to read them curtailed by a paywall that'd be sitting right after the first paragraph or so. I am aware of the cost of producing such content and am more than willing to pay for it. However, I don't think I'd pay $10/month only to see a few articles in that period. Enter our solution.

## Solution
Our solution to the problem above is as simple as this: you give a quick micropayment to the content provider every time you want to see a piece of content. Obviously, the price that's set for a given piece of content will depend on simple economics; we wouldn't want content providers to receive less revenue as a result of this service. For those that constantly live on the Economist app and read multiple articles a day, it would probably be worthwhile to pay that subscription fee. However, for others who want to enjoy content only on occassion but are turned away by a subscription requirement, an option to send a micropayment per piece of content might result in a more efficient scenario. 

#### User-flow
1. Have Metamask or other client-side plug-in to interact with the blockchain, with a sufficient balance of Ether
2. Navigate to a certain content site with a paywall
3. Approve a transaction to send [XXX] GWEI to a [XXX] content-provider
4. Gain access to content for a finite amount of time

*Why blockchain?*
* Drive adoption of cryptocurrencies
* Relatively easy facilitation of micropayments
* Verifiable, trustless transactions

## Tech stack
#### Front-end
* React + Redux
* Metamask: for users to have an interface to interact with Ethereum

#### Back-end
* Solidity: Ethereum-compatible smart contracts
* Truffle + Ganache: Solidity dev environment + testing
* Node: running a server
* Express: routing endpoints and managing cookies
* Heroku: hosting the site

## Timeline
* Develop smart contracts + test them
* Create website for MVP (e.g. with dummy data, and use Express cookie-session to control users' access to certain sites; cookies will be added to a user's session if they make the payment via Metamask and an appropriate "success" event is emitted from the smart contract)
* Consider working with real, third-parties and figure out ways to integrate (as mentioned below: Chrome extension or remote site as a proxy for allowing access)

## Other considerations
* Number of block confirmations required to allow someone to pass through (if payments take too long to confirm, this will probably slow things down to the point that the user no longer wants to view the content) -- high priority
* Chrome extension or remote site to permit users to bypass a paywall
* Challenge: ensuring that this system can't be exploited -- specifically, if a person gets a cookie-session and can access all articles on a site for, say, $0.10, then we (the providers) have a problem. Cookies must expire and must not be duplicable
* Benefit: paying $0.10 to read an article is better than having to scour the Internet for a copy of that same article, or making a dozen fake emails to get free trials for a given site (not advocating for this, but people actually do this haha)
* Pay to replace ads. In other words, pay the site instead of turning off your adblocker/whitelisting the site, which you probably do.

## Team
We are a team of computer science students at Penn that chose to develop this idea as part of a development course in Solidity.

## Contributing
We'll try to follow the general Git workflow, which goes something like the following:
* Create an issue
* Create a corresponding branch to address that issue
* Commit code
* Have someone review the code
* Merge with master branch