1. call是什么类型的成员变量？

- [x] address
- [ ] bool
- [ ] enum
- [ ] 它本身就是一种类型

2. call被推荐用来干什么？

- [x] 发送ETH
- [ ] 调用另一个合约
- [ ] 调用Library
- [ ] 解码ABI

3. call的返回类型为

- [x] bool 和 bytes memory
- [ ] bool
- [ ] bytes
- [ ] bool 和 memory

4. 下面哪种使用方式不正确？

- [ ] address(nameReg).call{gas: 1000000}(abi.encodeWithSignature("register(string)", "MyName"));
- [ ] address(nameReg).call{value: 1 ether}(abi.encodeWithSignature("register(string)", "MyName"));
- [ ] address.call{gas: 1000000, value: 1 ether}
- [x] call{gas: 1000000, value: 1 ether}

5. 下面是一个退款合约，请问它是否有Bug?

pragma solidity >=0.6.2 <0.9.0;
contract Fund {
    mapping(address => uint) shares;
    function withdraw() public {
        if (payable(msg.sender).call.value(shares[msg.sender])())
            shares[msg.sender] = 0;
    }
}

- [x] 是
- [ ] 否

6. 如果我们给call输入的函数不存在于目标合约，那么目标合约的什么函数会被触发？

- [x] fallback
- [ ] receive
- [ ] reponse
- [ ] error

7. call在什么情况下会调用失败？

- [ ] 当调用不存在的函数时，被调用合约实现fallback
- [ ] 被调用合约没有实现receive
- [x] 当调用不存在的函数时，被调用合约没有实现fallback
- [ ] call从来不会失败