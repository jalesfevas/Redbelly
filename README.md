# Redbelly
Deploying Smart Contract In Redbelly Devnet using REMIX (for advance user only)

What you need :
-  EVM wallet (ex.metamask)
-  Redbelly faucet token

Open your metamask, add new network (Redbelly Devnet) then connect to it :
```bash
Network Name: Devnet Redbelly
RPC URL: https://rbn-gcp-us-east5-a-0-b.devnet.redbelly.network:8545/
ChainID: 161
Currency Symbol: RBNT
Block explorer URL: https://monitoring.devnet.redbelly.network/
```
*if the RPC doesn't work, help yourself by asking the new RPC on Redbelly Discord Channel

Get faucet on Redbelly Discord
```bash
- Go to Redbelly Discord
- Go to #devnet-faucet room
- Use the bot and paste your wallet address
```

Go to REMIX
```bash
- Create new contract, name it whatever you like (ex.redbelly)
- Remix will create new file "redbelly.sol"
```

Double click redbelly.sol file, paste this code :
```bash
pragma solidity ^0.8.4;
contract FunctionTypes{
 uint256 public number = 5;
 
 constructor() payable {}

 function add() external{
 number = number + 1;
 }

 function addPure(uint256 _number) external pure returns(uint256 new_number){
 new_number = _number+1;
 }
 
 function addView() external view returns(uint256 new_number) {
 new_number = number + 1;
 }

 function minus() internal {
 number = number - 1;
 }

 function minusCall() external {
 minus();
 }

 function minusPayable() external payable returns(uint256 balance) {
 minus(); 
 balance = address(this).balance;
 }
}
```

Go to Compiler tab
```bash
- Use compiler version 0.8.18
- Click Compile redbelly.sol
- You will see checkmark on the compiler logo
```

Go to Deploy & Run Transactions tab
```bash
- Change the Environment to Injected Provider
- Connect your Metamask (make sure you’re on the Redbelly Devnet network)
- Click “ Deploy “ and “Confirm” on your metamask
- If you see "gas estimation failed", just continue and click Send Transaction
```

Scroll down (just right after "setting" tab) you'll see "Deployed Contract"
```bash
- Copy the contract
- Go to Redbelly Devnet Block Explorer (https://explorer.devnet.redbelly.network/overview)
- Paste your contract address
- You'll see your deployed contract address on Redbelly Devnet Network
```

Congratulation !!!
