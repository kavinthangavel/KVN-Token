SPL Token-22

> solana-keygen grind --starts-with KVN:1

> solana config set --keypair KVN__________.json

> solana config set --url https://api.devnet.solana.com  

> solana airdrop 2

> spl-token create-token -p TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb KVNmDjP8vhUTCk6toCtLu5gXDurV5CJfX6JGgbrBzsJ.json

(or)

> spl-token create-token -p TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb       #recommended 

After changing the address and json in mpl_token22.ts

Run ts file

> ts-node .\mpl_token22.ts

> spl-token create-account <tokenaddress>
 
> spl-token mint <tokenaddress> 10000000                                     #you can change the mint count ex.100,1000,999999....
 
Connect Paper Wallet to Phantom Wallet

> more KVN________________.json

Copy the O/P  #example [120,22,34,5,666,6,.....]

Create a new Accout in Phantom Wallet 

Select Import Private Key

Paste the key and name anything                                              #ignore the error while pasting key in Text-Box

Also Enable Testnet mode in Settings to see testnet tokens

