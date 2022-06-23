# 获取兑换信息详情接口

请求地址：/api/exchangeRecord/getTransDetail

请求方式：GET

请求参数：

| 字段名称 | 字段描述   | 类型     | 是否必须 | 备注 |
| ---- | ------ | ------ | ---- | -- |
| hash | 交易hash | string | 是    |    |

输出参数：定义同[添加兑换信息接口](tian-jia-dui-huan-xin-xi-jie-kou.md)返回。

输入示例：

[https://api.paths.finance/api/exchangeRecord/getTransDetail?hash=0xd5629104c4190c2bf161fba15ff3909148dcc12291e052479f0565761197f24e](https://api.paths.finance/api/exchangeRecord/getTransDetail?hash=0xd5629104c4190c2bf161fba15ff3909148dcc12291e052479f0565761197f24e)

输出示例：

```
{
    "resCode": 100,
    "resMsg": "success",
    "data": {
        "txHash": "0xd5629104c4190c2bf161fba15ff3909148dcc12291e052479f0565761197f24e",
        "fromTokenAddress": "0xc2132d05d31c914a87c6611c10748aeb04b58e8f",
        "fromTokenChain": "POLYGON",
        "fromTokenSymbol": "USDT",
        "fromTokenUrl": "https://swap.swftcoin.com/swft-v3/images/coins/USDT(MATIC).png",
        "toTokenAddress": "0xa71edc38d189767582c38a3145b5873052c3e47a",
        "toTokenSymbol": "USDT",
        "toTokenChain": "HECO",
        "toTokenUrl": "https://images.swft.pro/heco/0xa71edc38d189767582c38a3145b5873052c3e47a.png",
        "fromAmount": 48.926755,
        "toTokenAmount": "48.026755",
        "finalStatus": "success",
        "createTime": "2022-02-28 11:55:47",
        "status": [
            {
                "chain": "POLYGON",
                "txHash": "0xd5629104c4190c2bf161fba15ff3909148dcc12291e052479f0565761197f24e",
                "url": "https://polygonscan.com/tx/0xd5629104c4190c2bf161fba15ff3909148dcc12291e052479f0565761197f24e",
                "status": "success"
            },
            {
                "chain": "HECO",
                "txHash": "0xec237f4b64829c81f0f112665dd9a33e5948e3487548963e0169bbae639cea15",
                "url": "https://hecoinfo.com/tx/0xec237f4b64829c81f0f112665dd9a33e5948e3487548963e0169bbae639cea15",
                "status": "success"
            }
        ]
    }
}
```
