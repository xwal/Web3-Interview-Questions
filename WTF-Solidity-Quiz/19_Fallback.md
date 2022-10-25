1. 下面哪个选项语法是正确的？

- [ ] receive(uint256 value) external { }
- [ ] receive() external { }
- [ ] function receive() external { }
- [x] receive() external payable { }

2. fallback(or receive)函数是否在任何情况下都没有gas limit？

- [ ] 错误，当且仅当fallback(or receive)被send调用时有2400 gas limit
- [ ] 错误，当且仅当fallback(or receive)被transfer调用时有2300 gas limit
- [x] 错误，fallback(or receive)被transfer或send调用时有2300 gas limit
- [ ] 正确

3. vitalik想部署一个只接收ETH同时不需要接收msg.data的合约，那么他部署的合约中______________________

- [x] 必须含有receive函数或fallback函数
- [ ] 必须同时含有receive函数和fallback函数
- [ ] 必须含有receive函数
- [ ] 必须含有fallback函数

4. 假设存在如下合约，现在vitalik向该合约发起一笔低级交互，value=100Wei，msg.data
=0xaa，那么会发生下面选项中的哪种情况？(选项在下方）
```solidity
contract ReceiveETH {
    event Received(address Sender, uint Value);
    receive() external payable{
        emit Received(msg.sender, msg.value);
    }
}
```

- [ ] receive函数被调用，value和msg.data被成功发送
- [ ] receive函数被调用，value成功发送，msg.data发送失败
- [x] error：'Fallback' function is not defined，value和msg.data均发送失败
- [ ] fallback函数被调用，value和msg.data被成功发送

5. 假设存在如下合约，现在vitalik想调用该合约中不存在的函数，他在calldata中输入
函数选择器，并将value设置为1ETH，那么会发生下面选项中的哪种情况？（选项在下方）
```solidity
contract a {
    event Received(address sender, uint value, string message);
    receive() external payable{
        emit Received(msg.sender, msg.value, 'receive');
    }
}
```

- [ ] receive函数被调用，value成功发送，msg.data发送失败
- [x] error：'Fallback' function is not defined，value和msg.data均发送失败
- [ ] fallback函数被调用，value和msg.data被成功发送
- [ ] receive函数被调用，value和msg.data被成功发送