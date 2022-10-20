1. 一个合约可以定义多个构造函数（constructor）：

- [ ] 正确
- [ ] 错误

2. 构造函数的运行，只能通过手动调用：

- [ ] 正确
- [ ] 错误

3. 构造函数是否可以用来初始化合约参数？

- [ ] 是
- [ ] 否

4. 关于solidity中的修饰器（modifier），以下描述中正确的个数为：
* 可以用来声明函数某些特性
* 主要使用场景是运行函数前的检查
* 可以减少代码冗余
* modifier类似面向对象编程中的decorator

- [ ] 1
- [ ] 2
- [ ] 3
- [ ] 4

5. 阅读图中代码，非owner地址是否可以调用函数F？
```solidity
address owner;
    // 省略部分代码
    modifier M {
        require(msg.sender == owner);
        _;
    }

    function F (address _address) external M{
        owner = _address;
    }
```

- [ ] 是
- [ ] 否