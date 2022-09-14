﻿# TokenPay
<p>
<a href="https://www.gnu.org/licenses/gpl-3.0.html"><img src="https://img.shields.io/badge/license-GPLV3-blue" alt="license GPLV3"></a>
<a href="https://www.php.net/releases/7_4_0.php"><img src="https://img.shields.io/badge/.NET-6-orange" alt=".net6"></a>
<a href="https://github.com/assimon/dujiaoka/releases/tag/1.0.0"><img src="https://img.shields.io/badge/version-1.0.0-red" alt="version 1.0.0"></a>
</p>

## TokenPay - `USDT-TRC20`、`TRX` 动态收款地址解决方案

>一款开源`USDT-TRC20`、`TRX`动态收款地址的解决方案！

## 项目简介
- `TokenPay`是一个由`C#语言`编写的私有化部署`USDT-TRC20`、`TRX`收款解决方案。     
- 本项目不依赖任何外部资源，无需另外部署`数据库`，采用轻量化的`sqlite`，也无需`redis`。
- 任意项目都可以对接，轻松实现`USDT-TRC20`、`TRX`收款！😊 😊 😊
- `TokenPay` 遵守 [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) 开源协议!

## 项目特点
- `C#语言`跨平台实现，支持x86和arm芯片架构的win/linux/mac设备😁
- 支持每单一个收款地址，或每个用户一个收款地址，解决了单一地址收款，容易导致错误完成订单的痛点。
- 无需额外环境配置，仅运行一个编译后二进制文件即可使用

## 项目结构
```
TokenPay
    ├── Plugs ---> (插件)
    ├── Wiki ---> (知识库）
    └── src ---> (项目核心目录)
```

## 教程（待完善）：
- 宝塔运行`TokenPay`教程👉🏻[宝塔运行TokenPay](Wiki/BT_RUN.md)
- 手动运行`TokenPay`教程👉🏻[手动运行TokenPay](Wiki/manual_RUN.md)


## 加入交流/意见反馈
- `TokenPay`频道[https://t.me/TokenPayChannel](https://t.me/TokenPayChannel)
- `TokenPay`交流群组[https://t.me/TokenPayGroup](https://t.me/TokenPayGroup)

## 设计实现
`TokenPay`的实现方式与其他项目原理类似，都是通过`TronGrid`提供的api节点，      
轮询有订单的钱包地址的`USDT`代币、`TRX`入账事件，将入账金额，与数据库的订单金额进行对比，若一致，则视为订单完成
```
简单的原理：
0.服务器定时同步交易所最新汇率
1.客户支付，交易上链
2.服务器定时通过API轮询，获取监听地址下的最新USDT入账交易，并与数据库订单对比
3.若金额一致，将订单标记为完成
4.订单完成后，异步通知任务将订单完成事件回调给平台
```

## 打赏
如果该项目对您有所帮助，希望可以请我喝一杯咖啡☕️
```
USDT-TRC20打赏地址: TQWM6cuy6YesssqqzSucoUkS1A11kAAAAA
```
<img src="Wiki/imgs/usdt_thanks.jpg" width = "400" height = "500" alt="usdt扫码打赏"/>

## 致谢
感谢以下开源项目：

[Serilog](https://github.com/serilog/serilog) ![Github stars](https://img.shields.io/github/stars/serilog/serilog?style=social)

[FreeSql](https://github.com/dotnetcore/FreeSql) ![Github stars](https://img.shields.io/github/stars/dotnetcore/FreeSql?style=social)

[Flurl](https://github.com/tmenier/Flurl) ![Github stars](https://img.shields.io/github/stars/tmenier/Flurl?style=social)

[HDWallet](https://github.com/farukterzioglu/HDWallet) ![Github stars](https://github.com/farukterzioglu/HDWallet?style=social)

## 声明
`TokenPay`为开源的产品，仅用于学习交流使用！       
不可用于任何违反中华人民共和国(含台湾省)或使用者所在地区法律法规的用途。           
因为作者即本人仅完成代码的开发和开源活动(开源即任何人都可以下载使用或修改分发)，从未参与用户的任何运营和盈利活动。       
且不知晓用户后续将程序源代码用于何种用途，故用户使用过程中所带来的任何法律责任即由用户自己承担。            
```
！！！Warning！！！
项目中所涉及区块链代币均为学习用途，作者并不赞成区块链所繁衍出代币的金融属性
亦不鼓励和支持任何"挖矿"，"炒币"，"虚拟币ICO"等非法行为
虚拟币市场行为不受监管要求和控制，投资交易需谨慎，仅供学习区块链知识
```
[![Stargazers over time](https://starchart.cc/LightCountry/TokenPay.svg)](https://starchart.cc/LightCountry/TokenPay)