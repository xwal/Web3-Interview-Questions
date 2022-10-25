1. 函数选择器有几个字节？

- [ ] 1
- [ ] 2
- [ ] 3
- [x] 4

2. 如果一笔调用智能合约的交易的calldata为
0x6a6278420000000000000000000000002c44b726adf1963ca47af88b284c06f30380fc22
，被调用函数的选择器是？

- [ ] 0x6a
- [ ] 0x6a62
- [ ] 0x6a6278
- [x] 0x6a627842

3. transfer函数的函数签名是？

function transfer(address recipient, uint amount) external override returns (bool) {
        balanceOf[msg.sender] -= amount;
        balanceOf[recipient] += amount;
        emit Transfer(msg.sender, recipient, amount);
        return true;
    }

- [ ] "transfer()"
- [ ] "transfer(address,uint)"
- [x] "transfer(address,uint256)"
- [ ] "function transfer(address,uint256)"

4. 上一题中transfer函数的选择器为？

- [ ] 0x23b872dd
- [x] 0xa9059cbb
- [ ] 0xaab87wtf
- [ ] 0x00000000

5. 我想调用transfer函数将合约中的100枚 $PEOPLE 代币转给 0 地址，下面哪一个选项可以做到这一点。
  已知：
  1. 用pp指代 $PEOPLE 的ERC20合约地址。
  2. 从合约转账代币调用的是 transfer(address sender, uint256 amount) 函数


- [ ] pp.call(abi.encodeWithSelector(0x6a627842, uint256(100), address(0)));
- [ ] pp.call(abi.encode(0x6a627842, uint256(100), address(0)));
- [ ] pp.call(abi.encode(0xa9059cbb, uint256(100), address(0)));
- [x] pp.call(abi.encodeWithSelector(0xa9059cbb, uint256(100), address(0)));
- [ ] 其他:
