## Wallet api module

### 1. query balance by address 
- request way: post
- api name: api/get_balance
- request example
```
{
    "device_id": "1111111221",
    "wallet_uuid": "222222111",
    "index":"0",
    "chain": "Arbitrum",
    "symbol": "ETH",
    "network": "mainnet",
    "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
    "contract_address": ""
}
```

response example

```
{
    "ok": true,
    "code": 200,
    "result": {
        "balance": "6.1126",
        "asset_usd": "6.1126",
        "asset_cny": "42.7879",
        "data_stat": []
    }
}
```

### 2. query balance by wallet 
- request way: post
- api name: api/get_wallet_balance
- request example
```
{
    "device_id": "100220112ea",
    "wallet_uuid": "20122310101",
    "chain": "Ethereum"
}
```

response example

```
{
    "ok": true,
    "code": 200,
    "result": {
        "chain": "Arbitrum",
        "network": "mainnet",
        "device_id": "1111111221",
        "wallet_uuid": "222222111",
        "wallet_name": "yueyue",
        "asset_usd": "0.0000",
        "asset_cny": "0.0000",
        "token_list": [
            {
                "id": 9,
                "symbol": "ETH",
                "logo": "wallet/2022/11/13/虎符智能链_h.png",
                "contract_addr": "",
                "balance": "0.0000",
                "asset_usd": "0.00",
                "asset_cny": "0.00",
                "address_list": [
                    {
                        "id": 9,
                        "index": "0",
                        "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
                        "balance": "0.0000",
                        "asset_usd": "0.00",
                        "asset_cny": "0.00"
                    },
                    {
                        "id": 10,
                        "index": "1",
                        "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
                        "balance": "1.0000",
                        "asset_usd": "1.00",
                        "asset_cny": "1.00"
                    }
                ]
            },
            {
                "id": 10,
                "symbol": "USDT",
                "logo": "wallet/2022/11/15/虎符智能链_h.png",
                "contract_addr": "0xdAC17F958D2ee523a2206206994597C13D831ec7",
                "balance": "1.0000",
                "asset_usd": "1.00",
                "asset_cny": "1.00",
                "address_list": [
                    {
                        "id": 9,
                        "index": "0",
                        "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
                        "balance": "6112556512368236419.0000",
                        "asset_usd": "6.11",
                        "asset_cny": "42.79"
                    },
                    {
                        "id": 10,
                        "index": "1",
                        "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
                        "balance": "0.0000",
                        "asset_usd": "0.00",
                        "asset_cny": "0.00"
                    }
                ]
            }
        ]
    }
}
```

### 3. submit wallet info
- request way: post
- api name: api/submit_wallet_info
- request example

```
{
    "chain": "Arbitrum",
    "symbol": "ETH",
    "network": "mainnet",
    "device_id": "111111qqq1",
    "wallet_uuid": "22222qq2",
    "wallet_name": "shijiaaaang1",
    "index": "0",
    "address": "0x0000000000000000000000000000000",
    "contract_addr": "0x0000000000000000000000000000000"
}
```

response example

```
{
    "ok": true,
    "code": 200,
    "result": "submit wallet success"
}
```


### 4. batch submit wallet info
- request way: post
- api name: api/submit_wallet_info
- request example

```
{
    "batch_wallet": [
        {
            "chain": "eth",
            "symbol": "eth",
            "network": "mainnet",
            "device_id": "aaa",
            "wallet_uuid": "qqqq",
            "wallet_name": "sss",
            "index": "0",
            "address": "0x0000000000000000000000000000000",
            "contract_addr": "0x0000000000000000000000000000000"
        }
    ]
}
```

response example

```
{
    "ok": true,
    "code": 200,
    "result": "batch submit wallet success"
}
```


### 5. get wallet asset
- request way: post
- api name: api/get_wallet_asset
- request example

```
{
    "device_id": "1111111221"
}
```

response example

```
{
    "ok": true,
    "code": 200,
    "result": {
        "total_asset_usd": "0.0000",
        "total_asset_cny": "0.0000",
        "token_list": [
            {
                "wallet_name": "yueyue",
                "wallet_balance": [
                    {
                        "id": 9,
                        "symbol": "ETH",
                        "logo": "wallet/2022/11/13/虎符智能链_h.png",
                        "contract_addr": "",
                        "balance": "0.0000",
                        "asset_usd": "0.00",
                        "asset_cny": "0.00",
                        "address_list": [
                            {
                                "id": 9,
                                "index": "0",
                                "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
                                "balance": "0.0000",
                                "asset_usd": "0.00",
                                "asset_cny": "0.00"
                            },
                            {
                                "id": 10,
                                "index": "1",
                                "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
                                "balance": "1.0000",
                                "asset_usd": "1.00",
                                "asset_cny": "1.00"
                            }
                        ]
                    },
                    {
                        "id": 10,
                        "symbol": "USDT",
                        "logo": "wallet/2022/11/15/虎符智能链_h.png",
                        "contract_addr": "0xdAC17F958D2ee523a2206206994597C13D831ec7",
                        "balance": "1.0000",
                        "asset_usd": "1.00",
                        "asset_cny": "1.00",
                        "address_list": [
                            {
                                "id": 9,
                                "index": "0",
                                "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
                                "balance": "6112556512368236419.0000",
                                "asset_usd": "6.11",
                                "asset_cny": "42.79"
                            },
                            {
                                "id": 10,
                                "index": "1",
                                "address": "0x98E9D288743839e96A8005a6B51C770Bbf7788C0",
                                "balance": "0.0000",
                                "asset_usd": "0.00",
                                "asset_cny": "0.00"
                            }
                        ]
                    }
                ]
            }
        ]
    }
}
```

### 6. update wallet name
- request way: post
- api name: api/update_wallet_name
- request example

```
{
    "device_id": "1111111221",
    "wallet_uuid": "222222111",
    "wallet_name": "yueyue"
}
```

response example

```
{
    "ok": true,
    "code": 200,
    "result": "update wallet name success"
}
```


### 7. delete wallet
- request way: post
- api name: api/delete_wallet
- request example

```
{
    "device_id": "test111111111",
    "wallet_uuid": "test222222",
    "chain": "Arbitrum"
}
```

response example

```
{
    "ok": true,
    "code": 200,
    "result": "delete wallet success"
}
```


### 8. delete wallet token
- request way: post
- api name: api/delete_wallet_token
- request example

```
{
    "device_id": "test111111111",
    "wallet_uuid": "test222222",
    "chain": "Arbitrum",
    "symbol": "USDT",
    "contract_addr": "0x000"
}
```

response example

```
{
    "ok": true,
    "code": 200,
    "result": "delete wallet token success"
}
```





