# 通用说明

### 数据请求和返回数据类型说明：

生产api地址：[https://api.paths.finance](https://api.paths.finance)

测试api地址：[https://api-test.paths.finance](https://api.paths.finance)

POST请求数据格式和返回数据的格式均是**JSON**数据类型。

### 状态码说明：

| 状态码  | 含义 |
| ---- | -- |
| 100  | 成功 |
| 非100 | 失败 |

### 设备码说明：

```
// 设备码nodejs生成逻辑参考代码
          let equipmentNo = ''
          if (address.length <= 32) {
            let n = 32 - address.length
            for (let i = 0; i < n; i++) {
              equipmentNo += 'x'
            }
            equipmentNo += address
          } else {
            equipmentNo = address.slice(0, 32)
          }
```
