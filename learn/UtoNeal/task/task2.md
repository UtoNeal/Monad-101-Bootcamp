## 第二章：Solidity 快速入门

### 一、填空题

1. Solidity 中存储成本最高的变量类型是`_storage__`变量，其数据永久存储在区块链上。
2. 使用`_constant__`关键字声明的常量可以节省 Gas 费，其值必须在编译时确定。
3. 当合约收到不带任何数据的以太转账时，会自动触发`__receive_`函数。

---

### 二、选择题

4. 函数选择器(selector)的计算方法是： B
   **A)** sha3(函数签名)  
   **B)** 函数名哈希的前 4 字节  
   **C)** 函数参数的 ABI 编码  
   **D)** 函数返回值的类型哈希

5. 以下关于 mapping 的叙述错误的是： C
   **A)** 键类型可以是任意基本类型  
   **B)** 值类型支持嵌套 mapping  
   **C)** 可以通过`length`属性获取大小  
   **D)** 无法直接遍历所有键值对

---

### 三、简答题

6. 请说明`require`、`assert`、`revert`三者的使用场景差异（从触发条件和 Gas 退还角度）

(1)require:用于验证外部输入或执行环境是否符合预期，Gas 退换：若条件不满足，回滚所有状态更新，退还剩余 Gas
(2)assert:检查合约内部逻辑的一致性；Gas 退换:若条件不满足，回滚所有更新状态，不退还剩余 Gas
(3)revert:无条件或者复杂逻辑；Gas 退换:若条件不满足，回滚所有状态更新，退还剩余 Gas 7. 某合约同时继承 A 和 B 合约

7. 某合约同时继承 A 和 B 合约，两者都有`foo()`函数：

```solidity
contract C is A, B {
    function foo() override(A,B) {...}
}
```

实际执行时会调用哪个父合约的函数？为什么？

B 合约的 foo()函数会被先调用，因为在 solidity 中，多重继承遵循 C3 线性化规则，合约声明时从右到左进行继承

8. 当使用`call`方法发送 ETH 时，以下两种写法有何本质区别？

```solidity
(1) addr.call{value: 1 ether}("")
(2) addr.transfer(1 ether)
```

区别：
（1）transfer 交易失败后，会自动 revert 交易，而 call 需要手动检查返回值
（2）transfer 的 Gas 费有限制（2300），call 没有限制
（3）transfer 更安全但是功能受限，call 功能丰富但容易遭到攻击
