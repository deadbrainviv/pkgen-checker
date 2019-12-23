# Provate Keys Generator Checker
Generate Bitcoin Private Keys and check them against blockchain.com API
This is a fork and update of the original [PKGenerator_Checker](https://github.com/Frankenmint/PKGenerator_Checker)

Stupid Python Script that Generates random private keys and checks them in realtime...call this poor mans Mining for BTC - same chances as solo but you could find an address w/ money in it 🤑  This is for entertainment only and is designed to demonstrate how IMPOSSIBLE it is to realistically get a collision and take control of someone else's coin...Credits to @Shlomi for the inspiration...

# Fork updates
This fork updates includes:
- Use blockchain.com API to check wallets balance instead of using blockcypher which limits the number of request can you can make per hours/minute.
- If the script has ever to find a wallet with any balance will save the address and provate key along with the balance in a .txt file.

# Instructions

1. Clone this script - download it or in the terminal use `git clone https://github.com/monzanifabio/pkgen-checker.git`
2. Let's install some dependencies!  `pip install ecdsa hashlib base58 requests cfscrape`
3. Navigate to the directory: `cd pkgen-checker`
5. Run it! `python pkgen.py`

# Troubleshooting

If launching the script returns an error regarding some missing dependencies you might want to use `pip install --upgrade <dependencyName>` to fix those.

# Notes


* What's Going on?:  A random 32 byte Number is generated and encoded into Hex - Basially a number between 1 and 2^256 OR if counting in decimal form: [115792089237316195423570985008687907853269984665640564039457584007913129639936](http://www.calculatorsoup.com/calculators/algebra/exponent.php).  Then, that key is hashed a few times into a public address [according to these standard rules](https://en.bitcoin.it/w/images/en/9/9b/PubKeyToAddr.png) and is fired off to blockexplorer.com using their API. The script then prints the balance to the console window.
* I threw this together while following along [this video series](https://www.youtube.com/playlist?list=PLH4m2oS2ratfeNpZAoVwPlQqEr3HgNu7S) and reccomend YOU instead watch through the tutorials for your own benefit and to better grasp what happens at the protocol level for [Bitcoin](https://bitcoin.org)
* I had to use cfscraper to get around the issue of cloudflare on the v2 version of the script which uses bitcoinlist.io this version will scan an entire page at a time of keys..though idk if the underlying site is to be trusted (ie they just tell you the funds are zero and sweep the funds into their own wallet first)

Here's a demonstration of it in action

![demo working](http://g.recordit.co/z6QqeZyEM1.gif "We're Generating Private Keys and Checking Them on the Fly!")
