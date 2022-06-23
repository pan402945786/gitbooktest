# 询价接口

请求地址：/api/multiQuote

请求方式：GET

请求参数：

| 字段名称             | 字段描述               | 类型      | 是否必须            | 备注                                                                               |
| ---------------- | ------------------ | ------- | --------------- | -------------------------------------------------------------------------------- |
| equipmentNo      | 设备码                | string  | 是               | TBD                                                                              |
| fromTokenAddress | 源币合约地址             | string  | 是               |                                                                                  |
| toTokenAddress   | 目标币合约地址            | string  | 是               |                                                                                  |
| fromTokenAmount  | 源币数量，乘以decimal后的数量 | integer | <p></p><p>是</p> |                                                                                  |
| fromTokenChain   | 源币所在链              | string  | 是               | 参见《[主要区块链名称约定](../ji-ben-shuo-ming/zhu-yao-qu-kuai-lian-ming-cheng-yue-ding.md)》 |
| toTokenChain     | 目标币所在链             | string  | 是               | 参见《[主要区块链名称约定](../ji-ben-shuo-ming/zhu-yao-qu-kuai-lian-ming-cheng-yue-ding.md)》 |
| userAddr         | 用户地址               | string  | 是               |                                                                                  |
| toAddress        | 收币地址               | string  | 是               |                                                                                  |
| slippage         | 用户可接受滑点，单位：%       | decimal | 是               |                                                                                  |

输出参数：

| 字段名称               | 字段描述                  | 类型      |
| ------------------ | --------------------- | ------- |
| fromTokenAmount    | 源币数量，乘以decimal后       | integer |
| fromTokenDecimal   | 源币小数位                 | integer |
| toTokenAmount      | 目标币数量，除以decimal后      | decimal |
| toTokenDecimal     | 目标币小数位                | integer |
| dex                | 兑换平台                  | string  |
| fee                | 手续费，与源币单位一致           | decimal |
| feeToken           | 手续费结算币种symbol         | string  |
| receiveTokenAmount | 预计收到的目标币数量，除以decimal后 | decimal |
| logoUrl            | 兑换平台logo              | string  |
| dexStatus          | 兑换平台状态，默认空字符          | string  |
| depositMax         | 最大源币兑换数量              | decimal |
| depositMin         | 最小源币兑换数量              | decimal |

输入示例：

[https://api.paths.finance/api/multiQuote?equipmentNo=0x76336d2903e8f6d62cc3f5d0528310\&fromTokenAddress=0x55d398326f99059ff775485246999027b3197955\&toTokenAddress=0xc2132d05d31c914a87c6611c10748aeb04b58e8f\&fromTokenAmount=212000000000000000000\&fromTokenChain=BSC\&toTokenChain=POLYGON\&userAddr=0x76336d2903e8f6d62cc3f5d05283108e3d2785e0\&toAddress=0x76336d2903e8f6d62cc3f5d05283108e3d2785e0\&slippage=1](https://api.paths.finance/api/multiQuote?equipmentNo=0x76336d2903e8f6d62cc3f5d0528310\&fromTokenAddress=0x55d398326f99059ff775485246999027b3197955\&toTokenAddress=0xc2132d05d31c914a87c6611c10748aeb04b58e8f\&fromTokenAmount=212000000000000000000\&fromTokenChain=BSC\&toTokenChain=POLYGON\&userAddr=0x76336d2903e8f6d62cc3f5d05283108e3d2785e0\&toAddress=0x76336d2903e8f6d62cc3f5d05283108e3d2785e0\&slippage=1)

输出示例：

```
{
    "resCode": "100",
    "resMsg": "Success",
    "data": {
        "txData": [
            {
                "fromTokenAmount": "212000000000000000000",
                "fromTokenDecimal": 18,
                "toTokenAmount": 211.852768,
                "toTokenDecimal": 6,
                "dex": "CBridgeV2",
                "path": [],
                "fee": 0.145425,
                "feeToken": "USDT",
                "receiveTokenAmount": 211.852768,
                "cBridgeInfo": {
                    "feeAmount": 145425,
                    "token": "USDT",
                    "fromChainId": 56,
                    "toChainId": 137,
                    "slippage": 1000000
                },
                "logoUrl": "https://images.swft.pro/dex/cBridge.png",
                "dexStatus": ""
            },
            {
                "fromTokenAmount": "212000000000000000000",
                "fromTokenDecimal": 18,
                "toTokenAmount": 211.576,
                "toTokenDecimal": 6,
                "dex": "SWFT",
                "path": [],
                "fee": "0.2% + 1",
                "feeToken": "USDT(MATIC)",
                "receiveTokenAmount": 210.576,
                "depositMin": "30",
                "depositMax": "15787.341",
                "kycInfo": {
                    "status": false,
                    "cnUrl": "https://swap.swftcoin.com/swft-v3/swft-v3-m/kyc/kyc.html?lang=cn&equipmentNo=0x76336d2903e8f6d62cc3f5d0528310",
                    "enUrl": "https://swap.swftcoin.com/swft-v3/swft-v3-m/kyc/kyc.html?lang=en&equipmentNo=0x76336d2903e8f6d62cc3f5d0528310"
                },
                "logoUrl": "https://images.swft.pro/dex/SWFT.png",
                "dexStatus": ""
            },
            {
                "fromTokenAmount": "212000000000000000000",
                "fromTokenDecimal": 18,
                "toTokenAmount": 211.1,
                "toTokenDecimal": 6,
                "dex": "AnySwapV3",
                "path": [],
                "fee": "0.9",
                "feeToken": "USDT",
                "receiveTokenAmount": 211.1,
                "depositMax": "20000000",
                "depositMin": "12",
                "logoUrl": "https://images.swft.pro/dex/anyswap.svg",
                "dexStatus": ""
            }
        ]
    }
}
```
