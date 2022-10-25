1. delegatecall是哪个类型的成员变量？

- [ ] 它本身就是一种类型
- [ ] function
- [ ] bool
- [x] address

2. 当用户A通过合约B来delegatecall合约C时，执行了__的函数，语境是__，msg.sender和msg.value来自__， 并且如果函数改变一些状态变量，产生的效果会作用于__的变量上

- [x] C;B;A;B
- [ ] C;C;B;C
- [ ] B;B;A;B
- [ ] C;B;A;C

3. delegatecall在调用合约时__________________________

- [ ] 不可以指定交易发送的gas，但可以指定发送的ETH数额
- [x] 可以指定交易发送的gas，但不可以指定发送的ETH数额
- [ ] 不可以指定交易发送的gas，也不可以指定发送的ETH数额
- [ ] 可以指定交易发送的gas，也可以指定发送的ETH数额

4. 使用delegatecall对当前合约和目标合约的状态变量有什么要求？

- [x] 变量名可以不同，变量类型、声明顺序必须相同
- [ ] 变量名、变量类型、声明顺序都必须相同
- [ ] 声明顺序可以不同，变量名、变量类型必须相同
- [ ] 变量类型可以不同，变量名、声明顺序必须相同

5. 假设存在如下函数：
    function delegatecallMint(address _addr, uint _num) external payable{
        ________________________________________
    }
那么下面选项中可以填在横线上的是？

- [ ] (bool success, bytes memory data) = _addr.delegatecall(abi.encodeWithSignature("mint(uint)", _num);
- [ ] (bool success, bytes memory data) = _addr.delegatecall(abi.encodeWithSignature("mint(uint)", num);
- [x] (bool success, bytes memory data) = _addr.delegatecall(abi.encodeWithSignature("mint(uint256)", _num);
- [ ] (bool success, bytes memory data) = _addr.delegatecall(abi.encodeWithSignature(mint(uint256), num);

6. 在代理合约中，存储所有相关的变量的是___，存储所有函数的是___，同时____________

- [ ] 逻辑合约; 代理合约; 逻辑合约delegatecall代理合约
- [ ] 代理合约; 逻辑合约; 逻辑合约delegatecall代理合约
- [ ] 逻辑合约; 代理合约; 代理合约delegatecall逻辑合约
- [x] 代理合约; 逻辑合约; 代理合约delegatecall逻辑合约