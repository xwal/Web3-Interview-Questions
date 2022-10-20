1. 下面哪一项不是 Solidity 中的函数可见性说明符？

- [ ] external
- [ ] private
- [ ] protected
- [ ] public

2. 下面关于 view 关键字的描述，哪一项是准确的？

- [ ] 包含 view 关键字的函数，不能读取也不能写入存储在链上的状态变量
- [ ] 包含 view 关键字的函数，可以读取但不能写入存储在链上的状态变量
- [ ] 包含 view 关键字的函数，可以读取也可以写入存储在链上的状态变量

3. 下面关于 pure 和 view 两个关键字的描述，哪一项是错误的？

- [ ] 每个函数在声明时必须包含这两个关键字中的一个
- [ ] 这两个关键字可以控制函数的权限
- [ ] 包含这两个关键字的函数，调用时都不消耗 gas
- [ ] 其他编程语言中，一般不包含这两个关键字

4. 以下代码截取自 SafeMath Library，其定义了一个函数以替代“加法”，如果加法的结果溢出则会返回异常：

function add(uint256 a, uint256 b) internal _____ returns (uint256) {
    uint256 c = a + b;
    assert(c >= a);  // 本行代码意为：若c不大于等于a，则说明加法运算溢出，抛出异常
    return c;
}

那么，下划线处最适合填写的关键字是：

- [ ] pure
- [ ] view
- [ ] payable

5. 以下代码截取自 USDT 的 Token 合约，其声明了一个函数，任何用户都可以调用这个函数以查询某个地址的 USDT 余额：

function balanceOf(address who) _____ returns (uint)

那么，下划线处最适合填写的关键字是：

- [ ] internal
- [ ] private
- [ ] public
- [ ] payable