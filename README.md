# Smart Contract Application

#### Features

- Create new wallets completely client side.
- Access your wallet via unencrypted private key, encrypted private key, keystore files, mnemonics, or Digital Bitbox, Ledger Nano S or TREZOR hardware wallet.
- Easily send ETH and *any* ERC-20 Standard Token. [Many tokens included as default.](https://myetherwallet.groovehq.com/knowledge_base/topics/can-i-send-my-steem-slash-btc-slash-ltc-slash-nem-slash-to-myetherwallet)
- Generate, sign & send transactions offline, ensuring your private keys never touch an internet-connected device.
- Securely access your ETH & Tokens on your [Digital Bitbox, Ledger or TREZOR Hardware Wallet](https://myetherwallet.groovehq.com/knowledge_base/topics/hardware-wallet-recommends) via the MyEtherWallet interface (Chrome & Opera natively, Firefox w/ [add-on](https://addons.mozilla.org/en-US/firefox/addon/u2f-support-add-on/))
- Now in 18 languages thanks 100% to the amazing Ethereum community.
- Supports URI Strings on Send Transaction Page.
    - to=[address]
    - value=[number]
    - sendMode=[ether | token]
    - tokenSymbol=[ARC | ICN | MKR | ....]
    - gasLimit=[number] OR gas=[number]
    - data=[hex data]
    - Example 1: https://www.myetherwallet.com/?to=0x7cB57B5A97eAbe94205C07890BE4c1aD31E486A8&value=1&tokenSymbol=REP&gaslimit=50000#send-transaction
    - Example 2: https://www.myetherwallet.com/?to=0x7cB57B5A97eAbe94205C07890BE4c1aD31E486A8&value=1&gaslimit=23000&data=0x5468616e6b20796f752c204d455720322e30#send-transaction

**Folder Structure**
- `fonts` and `images` get moved into their respective folders. This isn't watched via gulp so if you add an image or font, you need to run `gulp` again.
- `includes` are the pieces of the pages / the pages themselves. These are pretty self-explanatory and where you will make most frontend changes.
- `layouts` are the pages themselves. These basically take all the pieces of the pages and compile into one massive page. The navigation is also found here...sort of.
    * `index.html` is for MyEtherWallet.com.
    * `cx-wallet.html` is the main page for the Chrome Extension.
    * `embedded.html` is for https://www.myetherwallet.com/embedded.html.

- You can control what shows up on MyEtherWallet.com vs the Chrome Extension by using: `@@if (site === 'cx' )  {  ...  }` and `@@if (site === 'mew' ) { ... }`. Check out `sendTransaction.tpl` to see it in action. The former will only compile for the Chrome Extension. The latter only to MyEtherWallet.com.
- `embedded.html` is for embedding the wallet generation into third-party sites. [Read more about it and how to listen for the address generated here.](https://www.reddit.com/r/ethereum/comments/4gn37o/embeddable_myetherwallet_super_simple_wallet/)
- The wallet decrypt directives are at `scripts/directives/walletDecryptDrtv.js`. These show up on a lot of pages.
- The navigation is in `scripts/services/globalServices.js`. Again, we control which navigation items show up in which version of the site in this single file.