# ethereum_node_running

### Step 1. Install APT — Advanced Package Tools
```
sudo apt-get install
```

### Step 2. Update package information
```
sudo apt-get update
```

### Step 3. Add ethereum repository
```
sudo add-apt-repository ppa:ethereum/ethereum && sudo apt-get update
```

### Step 4. Install the latest version of Go Ethereum - Geth
```
sudo apt-get install ethereum
```
### Step 5. Run the client
```
geth --syncmode "fast"
```
### Step 6. In a new session, open geth console

```
geth attach
```

## Useful Commands
```
eth.syncing
```
```
eth.syncing.currentBlock
```
```
eth.syncing.highestBlock
```
```
var lastPercentage = 0;var lastBlocksToGo = 0;var timeInterval = 10000;
setInterval(function(){
    var percentage = eth.syncing.currentBlock/eth.syncing.highestBlock*100;
    var percentagePerTime = percentage - lastPercentage;
    var blocksToGo = eth.syncing.highestBlock - eth.syncing.currentBlock;
    var bps = (lastBlocksToGo - blocksToGo) / (timeInterval / 1000)
    var etas = 100 / percentagePerTime * (timeInterval / 1000)

    var etaM = parseInt(etas/60,10);
    console.log(parseInt(percentage,10)+'% ETA: '+etaM+' minutes @ '+bps+'bps');

    lastPercentage = percentage;lastBlocksToGo = blocksToGo;
},timeInterval);
```
```
geth --syncmode "light"
```