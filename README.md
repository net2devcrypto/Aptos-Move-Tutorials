# Aptos-Move-Tutorials
Net2Dev Official Aptos Blockchain development Tutorial Videos GitHub Repo

<img src="https://raw.githubusercontent.com/net2devcrypto/misc/main/anchorlogo.png" width="150" height="45"> 

> [!NOTE]  
> THE FILES ATTACHED TO THIS REPO ARE FOR EDUCATIONAL PURPOSES ONLY.
> NOT FINANCIAL ADVICE
> USE IT AT YOUR OWN RISK, I'M NOT RESPONSIBLE FOR ANY USE, ISSUES.

<h3>Video 1</h3>

<a href="https://youtu.be/7qXZIKrQKTE" target="_blank"><img src="https://github.com/net2devcrypto/misc/blob/main/ytlogo2.png" width="150" height="40"></a>

<h3>Video 2</h3>

<a href="" target="_blank"><img src="https://github.com/net2devcrypto/misc/blob/main/ytlogo2.png" width="150" height="40"></a>

<h3>Setup Aptos Development Environment Instructions</h3>

<h4>Step 1 Install Aptos CLI for your desired OS</h4>

```shell
https://aptos.dev/en/build/cli
```

<h4>Step 2 Create project folder and initialize project</h4>

```shell
mkdir aptostut
cd aptostut
aptos move init --name aptostut
```

confirm you obtained "Result: Success"

<h4>Create Dev wallet in project</h4>

Open aptostut project folder in VS Code.

Then open your VS code terminal and create wallet account:

```shell
aptos init --network devnet
```

A folder named ".aptos" with a config.yaml file inside should been generated with the account info.

<h4>Step 3 Associate your account with the project.</h4>

Navigate to the .aptos folder, then open config.yaml and copy the account value.

Open the "Move.toml" file located in the project folder root, and add under "[addresses]"

```shell
[addresses]
net2dev_addr = "PASTE_COPIED_ACCOUNT_VALUE_HERE"
```

CTRL + S to Save file !

<h4>Step 4 Deploy Sample MOVE contract.</h4>

Download the demoaptos.move file from this repo and save it inside the project "sources" folder.

Open the VS Code terminal and proceed to compile the contract:

```shell
aptos move compile
```

If compiled successfully, you should see a similar return:

```shell
root@devpc1:/home/net2dev/aptostut# aptos move compile
Compiling, may take a little while to download git dependencies...
UPDATING GIT DEPENDENCY https://github.com/aptos-labs/aptos-core.git
INCLUDING DEPENDENCY AptosFramework
INCLUDING DEPENDENCY AptosStdlib
INCLUDING DEPENDENCY MoveStdlib
BUILDING aptostut
{
  "Result": [
    "9bdbaee9431e26a2ccb0a26bd65179fc2302954bf302635281ac516becc0e5fc::demoaptos"
  ]
}
```

Proceed to deploy to the Aptos devnet: 

```shell
aptos move publish
```

When prompted to submit tx, type "yes" and Enter.

If successfully published, you should obtain the following output:

```shell
root@devpc1:/home/net2dev/aptostut# aptos move publish
Compiling, may take a little while to download git dependencies...
UPDATING GIT DEPENDENCY https://github.com/aptos-labs/aptos-core.git
INCLUDING DEPENDENCY AptosFramework
INCLUDING DEPENDENCY AptosStdlib
INCLUDING DEPENDENCY MoveStdlib
BUILDING aptostut
package size 1321 bytes
Do you want to submit a transaction for a range of [143400 - 215100] Octas at a gas unit price of 100 Octas? [yes/no] >
yes
Transaction submitted: https://explorer.aptoslabs.com/txn/0x792e76f80d1d0a853a3f49113d10da5b9ba89ac88a2a9f4bbaa4b8146c0dedc5?network=devnet
{
  "Result": {
    "transaction_hash": "0x792e76f80d1d0a853a3f49113d10da5b9ba89ac88a2a9f4bbaa4b8146c0dedc5",
    "gas_used": 1434,
    "gas_unit_price": 100,
    "sender": "9bdbaee9431e26a2ccb0a26bd65179fc2302954bf302635281ac516becc0e5fc",
    "sequence_number": 0,
    "success": true,
    "timestamp_us": 1723344907152746,
    "version": 137896229,
    "vm_status": "Executed successfully"
  }
}
```

To test the contract functions watch @ ?t=23m53s
