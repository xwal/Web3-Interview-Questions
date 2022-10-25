1. Solidity中创建新合约的关键字是：

- [ ] create
- [ ] create1
- [ ] create2
- [x] new

2. Contract x = new Contract{value: _value}(params)，表达式中value代表什么？

- [x] 当前合约发送给新创建合约的ETH
- [ ] 当前合约发送给新创建合约的Token
- [ ] 当前合约调用者发送给当前合约的ETH
- [ ] 当前合约调用者发送给当前合约的Token

3. Contract x = new Contract{value: _value}(params)，表达式中params代表什么？

- [ ] 新合约的字节码
- [ ] 新合约初始化函数的参数
- [x] 新合约的构造函数的参数

4. 1个工厂合约PairFactory创建Pair合约的最大数量一般由什么决定？

- [ ] 1个PairFactory只能创建1个pari合约
- [ ] Pair合约逻辑
- [x] PairFactory合约逻辑

5. 示例中Pair合约创建时的msg.sender是？

- [ ] 当前交易的tx.orgin
- [x] 工厂合约PairFactory