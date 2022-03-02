# 获取基本信息接口

请求地址：/api/getBaseInfo

请求方式：GET

请求参数：

| 字段名称  | 字段描述  | 类型     | 是否必须 | 备注                                                                                    |
| ----- | ----- | ------ | ---- | ------------------------------------------------------------------------------------- |
| chain | 区块链名称 | string | 否    | 参见配置信息中《[主要区块链名称约定](../ji-ben-shuo-ming/zhu-yao-qu-kuai-lian-ming-cheng-yue-ding.md)》 |

输出参数：

| 字段名称        | 字段描述               | 类型                                 |
| ----------- | ------------------ | ---------------------------------- |
| tokens      | 币种信息列表             | 无chain参数时返回Object；有chain参数时返回Array |
| quoteSwitch | 是否可以询价开关，当前默认位true | bool                               |

输入示例：

[https://api.paths.finance/api/getBaseInfo](https://api.paths.finance/api/getBaseInfo)

输出示例：

```
// 无chain参数时的返回
{
    "resCode": "100",
    "resMsg": "Success",
    "data": {
        "tokens": {
            "ETH": [
                {
                    "symbol": "ETH",
                    "name": "Ethereum Token",
                    "address": "0xeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee",
                    "decimals": 18,
                    "logoURI": "https://swap.swftcoin.com/swft-v3/images/coins/ETH.png",
                    "isCrossEnable": true
                },
                {
                    "symbol": "WETH",
                    "name": "Wrapped Ether",
                    "address": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
                    "decimals": 18,
                    "logoURI": "https://images.swft.pro/inch1/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2.png",
                    "isCrossEnable": true
                },
                {
                    "symbol": "LINK",
                    "name": "ChainLink Token",
                    "address": "0x514910771af9ca656af840dff83e8264ecf986ca",
                    "decimals": 18,
                    "logoURI": "https://images.swft.pro/inch1/0x514910771af9ca656af840dff83e8264ecf986ca.png",
                    "isCrossEnable": false
                }
            ]
        },
        "quoteSwitch": true
    }
}
```

```
// 有chain参数的返回
{
    "resCode": "100",
    "resMsg": "Success",
    "data": {
        "tokens": [
            {
                "symbol": "BNB",
                "name": "BNB",
                "address": "0xeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee",
                "decimals": 18,
                "logoURI": "https://images.swft.pro/inch1/0xbb4cdb9cbd36b01bd1cbaebf2de08d9173bc095c.png",
                "isCrossEnable": false
            },
            {
                "symbol": "USDT",
                "name": "Tether USD",
                "address": "0x55d398326f99059ff775485246999027b3197955",
                "decimals": 18,
                "logoURI": "https://images.swft.pro/inch1/0xdac17f958d2ee523a2206206994597c13d831ec7.png",
                "isCrossEnable": false
            },
            {
                "symbol": "WBNB",
                "name": "Wrapped BNB",
                "address": "0xbb4cdb9cbd36b01bd1cbaebf2de08d9173bc095c",
                "decimals": 18,
                "logoURI": "https://images.swft.pro/inch1/0xbb4cdb9cbd36b01bd1cbaebf2de08d9173bc095c.png",
                "isCrossEnable": false
            }
        ],
        "quoteSwitch": true
    }
}
```
