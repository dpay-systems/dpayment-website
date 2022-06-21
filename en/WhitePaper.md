# DPayment 协议白皮书

:star::star: **2022 年 5 月 10 日修订**

## 引言
随着数字货币逐渐被更多人认可和接受，基于数字货币构建的经济生态也推动了 Web3 时代的到来。诸如 Uniswap 的去中心化交易所，MakerDao 的借贷/稳定币锻造平台，都已证明去中心化产品替代中心化产品的可行性，但数字货币支付相关的产品仍然以中心化设施为主。

与此同时，Swap / Cross-Chain / Layer2 相关设施及技术也趋于成熟，利用这些设施和解决方案可以快速和安全的构建体验和性能更好的支付服务。

去中心化的特性，可以让用户和商家免除 KYC 的烦恼，像使用 Metamask 一样自由。

对于创始团队，用去中心化的方式搭建数字货币支付系统，是理想也是趋势。

## 摘要
DPayment 协议的愿景是为用户和商家提供快速、稳定、安全的通用支付服务，该计划的基础是基于区块链和 DPayment 协议搭建的去中心支付网络，简称 DPay 支付系统。

DPay 支付系统作为抽象层，为多链网络和多币种支付提供链上合约和链下资源接口，使商家无需知晓区块链数字货币工作原理即可享受快捷安全的数字货币支付服务。

理想的 DPay 支付系统，需要满足以下特性：
- 符合 Web3 应用规范：商家和用户仅需要拥有一个钱包即可开始使用；
- 抽象复杂性：使开发人员和用户可以便捷的使用协议和系统，而无需熟悉复杂的底层；
- 可靠的性能：确保 DPay 支付系统可以达到高性能分布式系统的性能需求，提供稳定可靠的服务；
- 安全性：区块链中的数据具有天然透明的特性，需要为敏感数据提供新的保密保护；
- 减少信任：通过智能合约和其他可信技术保障最低信任的运行；
- 基于激励的安全：确保 DPay 系统的节点具有强大的经济动机来可靠和正确的运行，即使面对足够大的作弊诱惑也是如此；
- 索引服务：更符合支付服务特点的索引服务，通过 API 为开发者和商家提供数据服务。

以上特性，会用不同的服务产品体现：
- 商户服务平台：商家可通过该平台管理账户资产、订单/资金流水，查看报表等；
- 支付网关：包含收银台、用户钱包等前端边界产品和相关的接口产品；
- Layer2网络：使用 AppChain 方式部署和发布网络或使用其他高性能公链，但必须拥有独立的经济模型；
- 索引产品：基于大数据套件实现的流数据产品；
- 开发者产品：多语言 SDK 和文档。

## DPayment 协议概述

### DPayment 支付协议
DPayment 支付协议是一系列部署在区块链上的智能合约，用户、商家基于 DPayment协议可完成收付款、记账、清结算。

DPayment 支付协议包含主流公链上发布的收付款/资产池合约、账务核心合约、Layer2网络。当用户支付完成后，通过跨链桥协议将备付金以 Token 的方式登记在 Layer2 链上，商家也可在 Layer2链 上对资产转移、交易等，也可以通过跨链协议在其他公链上提取资产。

### DPayment 跨链协议
DPayment 协议中包含一组用于资产、订单的跨链协议。基于该协议，可以将商家的订单信息记录在性能更优秀的公链上，商家可以通过与这条公链上的支付协议查询所有链上的支付信息，也可以将结算资金通过DPayment 协议支持的公链中的其中一条链进行提款。

### 索引服务
DPayment 通过采集链上数据构建数据仓库，为通用浏览器、数据分析工具、商户服务平台提供索引服务。开发者可通过 API 或者 SDK 便捷的获取系统数据，构建个性化的产品。常见的通过索引服务构建的产品有：[Etherscan](https://etherscan.io/ "The Ethereum Blockchain Explorer") / [Uniswap Analytics](https://info.uniswap.org/# "") 等。

### DPayment 协议治理
DPT 是 DPayment 发行的治理型代币，DPayment 协议由世界各地的 DPT 持有者管理。通过由执行投票和治理投票组成的科学型治理系统，DPT 持有者可以管理 DPayment 协议的运营风险，从而确保该协议的稳定性、透明性和高效性。投票合约中锁定的每一个 DPT 代币均等同于一票。

### 与中心化支付系统对比的优势
|项目|中心化支付系统|Dpayment 协议|优劣|
|-------|-----------|------------|-------|
|数据安全|搭建异地灾备|去中心化节点|:white_check_mark:|
|账户功能|搭建账户系统|区块链原生能力|:white_check_mark:|
|数据一致性|搭建消息服务|区块链原生能力|:white_check_mark:|
|性能|性能瓶颈高|性能提升速度慢于中心化系统|:x:|
|商户接入条件| KYC 审核|无限制|:white_check_mark:|
|支付体验|转账收款，弱订单一致性|合约收款，强订单一致性|:white_check_mark:|
|监管合规|接入监管系统自主报备|完全开放，合规性更强|:white_check_mark:|
|市场|区域市场|全球市场|:white_check_mark:|

## DPayment 协议的设计
### 全景架构图
![DPayment 架构图](/img-wp/dpay-frame1.jpg)

### 商家接入
商家仅需要准备一个符合 EVM 规范的钱包账户即可开始接入系统，无需提供任何审核资料，也无需系统开通权限。

钱包与大部分的区块链网络中的账户体系相兼容，可通过 Secp256k1 椭圆曲线算法生成。推荐使用 [ethers.js](https://docs.ethers.io/v5/api/signer/#Wallet "Ether's JS-SDK ") 的 Wallet相关函数便捷的生成密钥对。

### 生成订单
商家按照 DPayment 订单规范构建订单信息后，使用结算账号私钥对订单按照 [EIP-191](https://eips.ethereum.org/EIPS/eip-191 "EIP-191 提案内容") 规范进行签名，将订单签名结果和订单内容合并组成完整的支付订单。

>#### 关于订单最小内容
>目标收款金额/目标收款币种/唯一订单编号/签名信息。DPayment 协议在实际场景中会需要更多的字段来描述订单。

>#### 关于签名算法
>- 为了在 Web Brower 下可以使用钱包插件完成签名，故采用目前使用最广泛的 [EIP-191](https://eips.ethereum.org/EIPS/eip-191 "EIP-191 提案内容") 规范进行签名。该规范在 [Metamask](https://metamask.io/ "EVM通用钱包插件") 环境下，可使用 eth_signTypedData_v4 指令完成签名。
>- 在服务端环境中，可使用 [ethers.js](https://docs.ethers.io/v5/api/signer/#Signer-signMessage) 中的 signMessage() / hashMessage() 完成签名。这里不限其他语言实现，具体参考 [ethers.js](https://docs.ethers.io/v5/api/signer/#Signer-signMessage) 中的签名实现。
>- 通过原始数据和签名，通过椭圆曲线算法可以计算出签名公钥，故 DPayment 协议通过签名计算得出商家的公钥地址，订单支付完成后，DPayment 协议将订单和公钥进行关联，并将备付金登记在该公钥即钱包地址下。

>#### 关于订单使用
>- 使用商家开发的专用收银台（DApp 客户端）与 DPayment 协议完成支付；
>- 使用 DPayment 提供的通用收银台与 DPayment 协议完成支付；
>- 使用社区提供的个性化收银台与 DPayment 协议完成支付。

### 订单支付/收款
用户借助收银台或其他 DApp 与 DPayment 协议进行交互，完成付款。付款交易在支付链上确认后，会发出相应的事件，Layer2 网络的链下工作机（Off-Chain-Worker）采集到相关事件，并在 Layer2 上登记订单并对商户进行记账。

>#### 关于付款
>- 如果用户支付 ERC20 资产，则需要先对收款合约进行 Approve ，Approve 额度根据合约开放及安全程度决定，在合约满足绝对安全前提下，会建议用户对其进行最高额度授权。
>- 向合约提交付款交易时，需要携带订单的完整信息，用于关联商户支付的订单。支付完成后，也需要将相应的内容通过事件进行登记。
>- 付款交易在区块完全确认后，Layer2 的链下工作机（Off-Chain-Worker）会将该笔订单信息登记在自己的网络中，并将收到的资产在自己的网络中生成跨链资产，并记录在商家名下。
>- 未支付的订单无需处理，也不会上链占用存储资源。

>#### 关于支持的链和币种
>原则上 DPay 系统支持已部署 DPayment 协议链上的所有 ERC20 和原生代币，假设商家希望接收稳定币 USDC，用户可以选择支付任何 Token，因为 DPayment 的合约会通过所在链上的 Swap 协议将用户支付的 Token 实时兑换成 USDC ，但存在一些限制条件：
>- 如果用户想支付的 Token 与商家目标收款的 Token 不存在 Swap 兑换链，则无法支持兑换。
>- 用户计划付款所在链上没有合法的 USDC 存在，则无法支持 USDC 的兑换及收款，用户则需要选择支持 USDC 的链完成支付。
>- 在稳定币支付场景中，DAI/USDT/USDC/UST 等 Token 都属于稳定型代币，DPayment 协议是可以在一些条件下，允许同类的稳定性代币享有同等权利。

>#### 关于手续费
>- DPayment 协议预设了一套阶梯的手续费模型，会根据商家交易周期内交易总额进行调整，当商家某一交易周期交易总额满足某一阶梯要求时，会按照阶梯的费率与结算时的费率差返还已收的交易手续费并将费率设置为已满足的费率。
>- 阶段费率只降不升。
>- 早期运营阶段，在一定周期内不收取支付手续费，但提现及付款需要收取一定的成本费用。
>- 手续费的模块以插件的形式接入 DPayment 协议中，进入 DAO 治理模式后，可以根据社区进行更换。

>#### 关于结算周期
> DPayment 协议由社区决定，早期设置结算周期为 5 分钟，可以认为是实时结算。但实时结算会面临流动性不足的问题。例如商家提现或付款，由于商家订单来自多条公链网络，通过其中一条链进行大额提现，当付款链中跨链桥的资金不足以全额付款时，会增加额外的资金调拨成本。可选解决方案有：
>- 通过社区激励，为跨链桥中注入流动性。
>- 引入做市或套利机构，为跨链桥中注入流动性。

### 提现/付款
商家在 Layer2 网络中发起提现/付款申请，待区块确认成功，根据申请参数，会进行不同的付款流程:
>- 申请取款凭证，由担保节点为商家提供提取款证签名。商家拿到取款凭证后，可在指定公链提取指定数量的数字货币。
>- 申请直接付款，由付款人（ DPayment 协议中有效的付款钱包或节点）为用户进行链上转账。转账成功后，将 Layer2 的资产付给付款人。付款人可通过调用跨链桥资金池付款，亦可通过自己的账户付款，通过自己账户付款成功后，将获得 Layer2 网络中的映射资产。

### 其他协议
除核心合约外，包含用于市场推广的代理商合约、服务于商户的多角色管理等合约。社区开发者可以通过学习和模仿创始团队开发的扩展合约，开发更专业的扩展合约提升产品，与此同时开发者可以出租或者出售自己的产品获得报酬。

## 应用链的设计
应用链为 DPayment 协议提供安全、高效的二层网络服务。DPayment 为了支持多链收款，单链结算的业务场景，需要将多链订单汇聚在一条链上，DPayment 不同于其他Defi项目，创始团队在设计 DPayment 协议之初，便确定了使用应用链来承载协议的运行的方向。

### 为什么建设应用链
- 现有的大部分公链性能，不足以支持支付业务的需求。
- 在一些高性能公链中，如 Solana / Avax / Near / Polkadot 等，链上运行了非常多的产品，性能会受到损耗，其次会因为一些项目的活动或套利机会导致公链的不稳定。
- 除个别公链外，链上的使用成本偏高，如 BSC 上提交一笔交易预计需要 0.5U 的成本，会增加DPayment 协议的使用成本。

### 如何建设应用链
创始团队大部分成员有 SubStrate 构建公链的经验，因此，创始团队具备构建应用链的综合能力。
##### 关于能力要求
- Layer2 网络必须支持 EVM，由于团队技术栈偏 SubStrate 方向，使用 Parity 的 Frontier 作为 EVM 兼容层是优先选择方向。

##### 关于网络安全
- Layer2 网络必须符合区块链网络安全性的必要条件，但自建网络需要组建社区和验证人来提供安全性，这是组建一条链最难的部分。
- Polkadot 生态的应用链通过拍卖卡槽接入网络，共享安全性，应用链无需组建验证人社区来获得安全性，但卡槽数量仅限 100 个，导致其当前的租赁成本达到了每年 6000 万美元之高。
- Near 生态下应用链设施，章鱼网络（[Octopus.network](https://oct.network "章鱼网络为应用链提供灵活且负担得起的租用安全，跨链互操作，基础设施和社区建设指导。")）。章鱼网络的租用安全设施，年成本约 60 万美元。由于章鱼网络的使用成本低于其他方案，会优先考虑并入章鱼网络。

##### 关于性能
- 2021 年 7 月，团队对 SubStrate 的 Babe 共识，在单节点配置 8C16G 的 EVM 中组网压力测试，得到的测试报告为链上处理性能约为 750TPS，单块包含交易为 4500 笔左右，节点资源的使用情况为 20-30%。在参数调优和提升运行环境物理配置后，理论可得到更高的性能报告。由于该结构已满足阶段性要求，并未继续深入测试。详细报告及工具可参考：[Substrate-Loadtest](https://github.com/nulls-network/chain-loadtest);

## DPayment 的经济模型
DPayment 为上述业务模型提出如下的通证经济模型：

总发行量为 1,000,000,000 DPT

- 募集资金
  - 为项目初期提供资金支持。
  - 共出售 120,000,000(12%) DPT 代币，募资出售比例和价格根据阶段性动态调整。
  - 所有私募获得的代币，均在完全付款完成三个月后，分 3 年按天线性释放。假设私募可获得的总 DPT 为 1,000,000 ，每天可获得的 DPT≈1000000/356*3 枚。
  - 项目开启流动性预售后，则将未完成出售的 DPT 注入金库，不再出售。
- 流动性预售（Initial Liquidity Offering）
  - 预售阶段不设置白名单。
  - 出售15,000,000(1.5%) DPT 代币，代币价格使用最后一次私募的价格。
  - 募集结束后，用10,000,000(1%) DPT 代币与总募集的 ETH，加入 UniswapV2，为项目提供初始流动性。
  - 所得 LP 代币将全部转入0x0000..dead 进行销毁，永久锁定流动性。
  - 参与预售获得的 DPT 在 360 天内按天线性解锁。
  - 使用 5,000,000(0.5%) DPT 用来提供 LP Staking 奖励，为期 3 个月。
- 交易奖励
  - 奖励为推广 DPayment 的商家或经销商提供实质奖励，故只有一级商户或代理商可享有交易量奖励。
  - 使用 100,000,000(10%) DPT用于提供为期一年的商家交易奖励，为了防止刷交易量套取奖励，将会有一系列奖励规则。详见 xxxx。
  - 交易奖励周期为 2 年， 每日可奖励的 DPT≈100000000/(365*2)。
- DPT Staking 奖励
  - 代币持有者可通过质押 DPT 获取手续费收益。
  - 手续费收益会在每月 1 号根据上一个月质押的情况进行分配，分配原则为根据自己质押 DPT 的总数和时长决定，最大时间为 31 天，在分配收益前取出代币，则无法获得收益。
  - 用户可通过质押的 DPT 总数 * 质押天数计算得到自己的分配相对值，用该相对值除以总的质押相对值得到自己可以获得的分配比例。
  - 手续费可能为多种代币，DAO 组织会将其兑换为 USDC / DAI 作为奖励。
- DPayment 基金会
  - 基金会固定持有 300,000,000(30%) DPT 代币，5 年内不可转让不可出售，其他权利不变。
  - 基金会持有的 DPT 可用于 Staking 奖励。当手续费营收不足以支持当期基金会时，分红资金优先满足基金会开支预算。基金会也可根据自身现金流情况选择放弃该权利。
- 

![Tokenomics](/img-wp/tokenomics4.png)
## DPayment 协议的治理
> :exclamation:本章节内容存在较大修正的可能性，仅做指引阅读。

### 基金会义务和权利
基金会负责为 DPayment 协议的安全稳定运行提供一切保障，当社区不足保障 DPayment 协议的正常运作时，基金会会接管 DPayment 协议的部分权限，当协议重新符合社区运作时，将权限交还社区。

基金会的义务包含但不限于：
- 为参与 DPayment 协议建设的个人或团队提供资金保障。
- 为 DPayment 协议运行提供所需的资金保障。
- 为社区建设和秩序维护提供后方支撑。
- 当出现安全事故，导致资金损失时，由基金会提供最大能力资金保障。

基金会的权利包含但不限于：
- 通过质押 DPT 获得手续费收益。收益额度包含月度基本开销预算、风险保证金预算等。
- 可对个人或组织发放授权，深度参与协议建设。
- 自由支配基金会资金，但必须完全公示。
- 基金会可以交换资源的方式授权特约商家特殊费率。

基金会所补充条款：
- 当出现损失，基金会资金无法偿还全部损失时，可通过赔付基金会所有的 DPT 或者变卖 DPT 来弥补损失。
- 当基金会现金流十分充裕时，可抵押 DPT 参与节点建设，但原则是基金会不能持有超过总数 5% 的节点数。
- 当基金会现金流十分充裕时，可为 DPT 无偿提供流动性。
  - 获得的 LP 代币不可参与流动性锁仓奖励。
  - 赎回流动性时，需要保障得到的 DPT 必须等于锁仓之前的 DPT。
  - 当可赎回的 DPT 总数高于添加流动性前总数的 5%时，不允许赎回。
  - 当可赎回的 DPT 总数小于添加流动性前总数时，赎回流动性后，需要购买 DPT 补齐添加流动性前总数。

### Exit to DAO
创始团队设想的 DPayment 的**最终形态**是一个去中心化自治组织（DAO），由 DAO 的成员决定项目的发展方向。创始团队相信真正能驱动一个 DAO 高效前进的要因不是币价，而是参与者们对于项目愿景的共识。在完成第一阶段的建设后，创始团队会开始探索，并逐渐将整个项目方向的主导权、财政权等，从初创团队移交到 DAO 手中。关于 DAO 的治理不在此次白皮书中进行讨论。

### 业务安全节点
网络安全可通过应用链的机制保障，但业务安全需要 DPayment 协议的中的Tokenomics 保障。运行机制如下：
- 任何持有 DPT 的用户均可通过质押 DPT 获得从资金池中授权的权利。
- 可授权额度根据质押 DPT 的总量来决定。
- 成为业务安全节点需要质押至少 1,000,000(0.1%) DPT。
- 业务安全节点完成每笔授权后，均可获得一定的手续费奖励。
- DPayment 协议会根据一定算法随机选出付款请求的处理节点，防止节点作弊。
- 当发现节点作恶时，其他节点自发投票将作恶节点踢出网络并没收作恶节点质押的全部 DPT。

##  路线图（Roadmap）
![Roadmap](/img-wp/roadmap2.jpg)


**当Visa 和 Master宣布对俄罗斯普通民众停止服务的那一刻开始，DPayment 的机会来了。我们不会创造历史，只是顺应潮流。**

欢迎加入我们。

## Links 
- Website : dpay.systems
- E-Mail : public@dpay.systems

## 参考资料
1. The Ethereum Blockchain Explorer: https://etherscan.io/
2. Ether's JS-SDK : https://docs.ethers.io/v5/api/signer/#Wallet
3. EIP-191 提案内容: https://eips.ethereum.org/EIPS/eip-191
4. Metamask钱包: https://metamask.io/
5. 章鱼网络: https://oct.network
6. Substrate Node 性能测试报告和工具：https://github.com/nulls-network/chain-loadtest