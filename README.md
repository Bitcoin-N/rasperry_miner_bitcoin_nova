<img src="http://pool.bitcoinn.biz/bitcoin-nova.png">

# rasperry_miner_bitcoin_nova

you need the version "Raspbian Stretch Lite"
https://www.raspberrypi.org/downloads/raspbian/

for everything else download from the github and use.

modify the following files to add your favorite pool and your wallet

cpuminer-multi: "start"
```
./cpuminer -a cryptonight -o stratum+tcp://pool.bitcoinn.biz:11122 -p x -u EAsX15ieXY1NAk9Yu3NoVBfBqUgsFPsv47Ff4W1t491vHiD8fyGHD7nR7gVk1FrcbP2d2mJfBt3M45NgbV6ZRcSdHixcSPH --api-bind 0


./cpuminer -a cryptonight -o stratum+tcp://pool:port -p x -u address_wallet --api-bind 0
```

xmrig: "config.json"

```
"algo": "cryptonight",  // cryptonight (default) or cryptonight-lite
    "av": 0,                // algorithm variation, 0 auto select
    "background": false,    // true to run the miner in the background
    "colors": true,         // false to disable colored output    
    "cpu-affinity": null,   // set process affinity to CPU core(s), mask "0x3" for cores 0 and 1
    "cpu-priority": null,   // set process priority (0 idle, 2 normal to 5 highest)
    "donate-level": 1,      // donate level, mininum 1%
    "log-file": null,       // log all output to a file, example: "c:/some/path/xmrig.log"
    "max-cpu-usage": 100,    // maximum CPU usage for automatic mode, usually limiting factor is CPU cache not this option.  
    "print-time": 60,       // print hashrate report every N seconds
    "retries": 5,           // number of times to retry before switch to backup server
    "retry-pause": 5,       // time to pause between retries
    "safe": false,          // true to safe adjust threads and av settings for current CPU
    "threads": 4,        // number of miner threads
    "pools": [
        {
            "url": "pool.bitcoinn.biz:11122",   // URL of mining server
            "user": "EAsX15ieXY1NAk9Yu3NoVBfBqUgsFPsv47Ff4W1t491vHiD8fyGHD7nR7gVk1FrcbP2d2mJfBt3M45NgbV6ZRcSdHixcSPH",                        // username for mining server
            "pass": "x",                       // password for mining server
            "keepalive": true,                 // send keepalived for prevent timeout (need pool support)
            "nicehash": false                  // enable nicehash/xmrig-proxy support
        }
    ],
    "api": {
        "port": 0,                             // port for the miner API https://github.com/xmrig/xmrig/wiki/API
        "access-token": null,                  // access token for API
        "worker-id": null                      // custom worker-id for API
    }
}

```

```
"algo": "cryptonight",  // cryptonight (default) or cryptonight-lite
    "av": 0,                // algorithm variation, 0 auto select
    "background": false,    // true to run the miner in the background
    "colors": true,         // false to disable colored output    
    "cpu-affinity": null,   // set process affinity to CPU core(s), mask "0x3" for cores 0 and 1
    "cpu-priority": null,   // set process priority (0 idle, 2 normal to 5 highest)
    "donate-level": 1,      // donate level, mininum 1%
    "log-file": null,       // log all output to a file, example: "c:/some/path/xmrig.log"
    "max-cpu-usage": 100,    // maximum CPU usage for automatic mode, usually limiting factor is CPU cache not this option.  
    "print-time": 60,       // print hashrate report every N seconds
    "retries": 5,           // number of times to retry before switch to backup server
    "retry-pause": 5,       // time to pause between retries
    "safe": false,          // true to safe adjust threads and av settings for current CPU
    "threads": 4,        // number of miner threads
    "pools": [
        {
            "url": "pool:port"  // URL of mining server
            "user": "wallet_addres"           // username for mining server
            "pass": "x",                       // password for mining server
            "keepalive": true,                 // send keepalived for prevent timeout (need pool support)
            "nicehash": false                  // enable nicehash/xmrig-proxy support
        }
    ],
    "api": {
        "port": 0,                             // port for the miner API https://github.com/xmrig/xmrig/wiki/API
        "access-token": null,                  // access token for API
        "worker-id": null                      // custom worker-id for API
    }
}

```

executable:
cpuminer-multi= "start"
xmrig = "xmrig"
