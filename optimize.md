wasm vm optimize for ontology

1.以当前ontology master为基础

2.Folk最新的wagon项目作为单独repo

3.保留wasm 的 executionEngine作为wasm执行的入口

4.excutionEngine 需要增加input buffer 和 return buffer处理输入输出

5.System call(service) 接口为：func([]uint64,ctx)(uint64,error)

6.Wasm vm 增加 validation接口，供合约deploy时调用，validation 要检查import的库是否被允许

7.Wasm vm 删除所有Float相关

8.Wasm vm需要增加 gaslimit和service map接口，以便注入

9.Wasm vm需要增加对（env function）的处理，以便调用service map中的函数

10.Wasm vm 的 跨合约调用 stack 深度限制

11. wasm vm总step限制（防止预执行攻击）
