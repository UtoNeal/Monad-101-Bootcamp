## 第一章：走进 Web3 世界

1. 简单描述一下本地开发、部署合约的流程

在开发环境比如：VS Code 上面使用 foundry 初始化一个项目，并进行相关配置之后，编写智能合约，之后再进行测试，比如单元测试，fuzzy test 等，最后使用命令 forge create --rpc-url <本地 RPC 地址> --private-key <私钥> <合约路径>:<合约名称>部署到相应位置

2. 简单描述一下用户在使用一个 DApp 时与合约交互的流程

通过浏览器连接钱包插件，并通过钱包与链上进行交互（调用智能合约，查看链上数据等）

3. 通读[「区块链黑暗森林自救手册」](https://github.com/slowmist/Blockchain-dark-forest-selfguard-handbook/blob/main/README_CN.md)，列出你觉得最重要的三个安全技巧

（1）切忌泄露自己的私钥，最好用硬件钱包存储自己的资产
（2）在合约部署上链之前进行合约测试和合约审计，防止合约漏洞被攻击
（3）仔细观察合约地址，网址，防止钓鱼执法
