# substrate-develop
develop substrate notes.

## 为什么我们用 Substrate
- Rust 实现底层安全
- 开发链比较自由


## 学习链接

- [substrate](https://github.com/paritytech/substrate)
- [polkadot](https://github.com/paritytech/polkadot)
- [substrate 主页](https://substrate.dev)
- [substrate-node-template](https://github.com/substrate-developer-hub/substrate-node-template)
- [substrate官方学习](https://substrate.io)
- [bilibili](https://space.bilibili.com/67358318)
- [教程 repo](https://github.com/SubstrateCourse/substrate-node-template)
- [中文](https://core.tetcoin.org/docs/zh-CN/)
- [parity 代码最新的最详细的 crates](https://crates.parity.io/)
- [一个很简单的初始化配置](https://github.com/paritytech/substrate/blob/master/frame/sudo/src/lib.rs)
- [链上存证教程](https://docs.substrate.io/tutorials/v3/proof-of-existence/)


## 运行一条链

cargo build --release
[palkadot](https://polkadot.js.org/apps/)

## 常用宏

- frame_support::pallet 定义功能模块
- pallet::config 定义配置接口
- pallet::storage 存储单元
- pallet::event 事件
- pallet::error 错误信息
- pallet::call 包含可调用函数 
- pallet::hooks 区块不同时期的执行逻辑
- construct_runtime 添加模块到 Runtime

数据类型：
- 单值 StorageValue
- 映射 StorageMap
- 双键映射 StorageDoubleMap

hooks 宏

Runtime 模块里面存在保留函数，用于执行特写的逻辑：
- on_initialize: 在每个区块的开头执行
- on_finalize: 在每个区块的结束时执行
- offchain_worker: 开头且是链外执行，不占用链上的资源
- on_runtime_upgrade: 当有 runtime 升级时才会执行，用来迁移数据

construct_runtime! 加载模块。

## 注意
- 链上不要存大数据 
- 如果用到集合的类型，需要设置列表容量，不能超出了
- Verify First, Write Last
- 事务管理：Transactional macro
- `cargo update -p parity-db` 如果报错下载 parity-db 失败的情况即更新一下库。

## 存储功能开发

[链上存证教程](https://docs.substrate.io/tutorials/v3/proof-of-existence/)