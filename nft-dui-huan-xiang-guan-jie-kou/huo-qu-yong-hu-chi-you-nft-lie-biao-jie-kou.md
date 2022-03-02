# 获取用户持有NFT列表接口

请求地址：/api/v1/meta/getOwnedAssets

请求方式：GET

请求参数：

| 字段名称     | 字段描述 | 类型      | 是否必须 | 备注 |
| -------- | ---- | ------- | ---- | -- |
| owner    | 用户地址 | string  | 是    |    |
| page     | 页码   | integer | 是    |    |
| pageSize | 每页数量 | integer | 是    |    |

输出参数：

| 字段名称         | 字段描述                   | 类型      |
| ------------ | ---------------------- | ------- |
| tokenId      | token id               | string  |
| contractAddr | NFT合约地址                | string  |
| name         | NFT名称                  | string  |
| imageUrl     | NFT图片地址                | string  |
| mainnet      | NFT合约所在链               | string  |
| platformId   | NFT平台主键ID              | integer |
| canSell      | 是否能卖，true：能卖，false：不能卖 | bool    |

输入示例：

[https://api.paths.finance/api/v1/meta/getOwnedAssets?owner=0x76336d2903e8f6d62cc3f5d05283108e3d2785e0\&page=1\&pageSize=50](https://api.paths.finance/api/v1/meta/getOwnedAssets?owner=0x76336d2903e8f6d62cc3f5d05283108e3d2785e0\&page=1\&pageSize=50)

输出示例：

```
{
    "resCode": "100",
    "resMsg": "Success",
    "data": {
        "assets": [
            {
                "tokenId": "1560218",
                "contractAddr": "0x22c1f6050e56d2876009903609a2cc3fef83b415",
                "name": "Dapp-Learning-111",
                "imageUrl": "https://lh3.googleusercontent.com/2CHkr8agGwOm9NIyhNFBgG2kSzO_OLhiYury3nOtdB5lbHX8W-RoBcHVfXgNoc-72ZzhLJoa6ALrB2o0pxZy8PcMuWYEGZc9zexSYIc",
                "mainnet": "ETH",
                "platformId": "386405378620468200",
                "canSell": false
            },
            {
                "tokenId": "158456339822817985252103554542",
                "contractAddr": "0x7227e371540cf7b8e512544ba6871472031f3335",
                "name": "Bliss Agent: Renegade",
                "imageUrl": "https://api.treasureland.market/v1/resourceS3?uri=images/matic/0x7227e371540cf7b8e512544ba6871472031f3335/369df65834b14d7035410de0440d7d63.png",
                "canSell": false,
                "platformId": "386405400144891905",
                "mainnet": "POLYGON"
            }
        ]
    }
}
```
