# okxSocketDemo

install required packages with ```npm install```

run with ```npm index.js```

## This application is a fully functional template for okx websockets utilizing PENDAX-SDK

Add your api key, secret, and passphrase in index.js under the socket config. adjust parameters as neccesary. If the endpoint you are trying to
use is private, change isPrivate: true. For market data and other public endpoints, isPrivate: false.

create a subscription inside the doSubscriptions function.

This sample code is using a single okxSubscription, however to add more just declare a new variable and a new socket config. You can refrence more
than one at a time inside the try block in startSocket function.

ex:
```    
function doSubscriptions(socket) {
subscriptions.tickers = {
        name: 'tickers',
        args:
            [{ channel: 'tickers', instId: 'BTC-USDT-SWAP' }]
    }
    socket.subscribe(subscriptions.tickers)
    console.log('Attempting subscriptions')
}
```

Edit what you want to happen when a message comes in on this channel inside the handleMessage function:
```        
case 'tickers':
            console.log(msg.data)
            break;
```
            
All websocket functionality available from OKX at time of writing is present in this template     
