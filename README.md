# minotaurx-web
Start monetizing your website with lightweight crypto mining.
## Why mining
Cryptos have a place in the website monetization. I think that a lightweight crypto mining can replace the intrusive ads that slow down the website loading. Mining is silent and transparent for the user. It works in background and keeps the website loading fast.
## Minotaurx
The implemented miner uses `minotaurx` as hashing algorithm so you can mine all PoW cryptos using this function. Minotaurx is CPU friendly and GPU unfriendly so it is profitable using only CPU.
## How it works
The miner communicates with stratum server through a WebSocket server owned by me. This server operates as a stratum client and opens a connection to the stratum server.
### Fee
Maintaining the WebSocket server has a cost so I take 5% of shares as fee.
## Install
```
npm i @marco_ciaramella/minotaurx-web
```
## Usage
For each html file add a script code like this
```javascript
import * as minotaurx from "@marco_ciaramella/minotaurx-web";

try {
    minotaurx.mine({
        // required
        stratum: {
            server: "stratum-eu.rplant.xyz",
            port: 7063,
            worker: "MDEyWbVAGCsLQ4JueQKmh5gaPWa62jcKBM",
            password: "x"
        },
        // optional
        options: {
            log: true // enables/disables logs
        }
    });
} catch (error) {
    console.error(error);
}
```