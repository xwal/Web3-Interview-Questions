1. 下列关于智能合约调用其他智能合约的说法，正确的一项是：

- [x] 智能合约调用其他智能合约这一功能，主要起到了方便代码复用的作用
- [ ] 在智能合约 A 中调用智能合约 B，比起在链下直接调用智能合约 B，要更节省 gas
- [ ] 智能合约 B 中可见性为 internal 的函数，也可以被智能合约 A 调用

下面的几道题目中，共用相同的题目假设。也就是说，题目中出现的所有条件在几道题中都是通用的，比如已部署的合约地址、已部署的合约内容等。
我们首先定义了一个接口 IOtherContract，然后基于此接口实现了一个具体合约 OtherContract：
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.6;

interface IOtherContract {
    function getBalance() external returns(uint);
    function setX(uint256 x) external payable;
    function getX() external view returns(uint x);
}

contract OtherContract is IOtherContract{
    uint256 private _x = 0;
    event Log(uint amount, uint gas);
    
    function getBalance() external view override returns(uint) {
        return address(this).balance;
    }

    function setX(uint256 x) external override payable{
        _x = x;
        if(msg.value > 0){
            emit Log(msg.value, gasleft());
        }
    }

    function getX() external view override returns(uint x){
        x = _x;
    }
}
```

2. 假设我们部署了上述合约 OtherContract，其合约地址为 
0xd9145CCE52D386f254917e481eB44e9943F39138。
我们希望在另一个合约中调用该合约，考虑如下两种方式：

(1) OtherContract other = OtherContract(0xd9145CCE52D386f254917e481eB44e9943F39138)
(2) IOtherContract other = IOtherContract(0xd9145CCE52D386f254917e481eB44e9943F39138)

下列说法正确的是：

- [ ] (1)(2) 两种写法均会报错
- [ ] 仅 (1) 是调用其他合约的正确写法，(2) 会报错
- [ ] 仅 (2) 是调用其他合约的正确写法，(1) 会报错
- [x] (1)(2) 均是调用其他合约的正确写法

3. 我们新写了一个合约，并在合约中调用上述已部署的合约 0xd9145CCE52D386f254917e481eB44e9943F39138，如下：
```solidity
contract MyContract {
    OtherContract other = OtherContract(0xd9145CCE52D386f254917e481eB44e9943F39138);
    function call_getX() external view returns(uint x){
        x = other.getX();
    }
    function call_setX(uint256 x) external{
        other.setX(x);
    }
}
```
部署该合约，其地址为 0x9D7f74d0C41E726EC95884E0e97Fa6129e3b5E99。下列说法正确的是：

- [ ] MyContract 可以算作 OtherContract 的子类
- [ ] MyContract 可以算作接口 IOtherContract 的一个实现
- [ ] MyContract 需要 0xd9145CCE52D386f254917e481eB44e9943F39138 的某种许可，才可以调用其中的函数
- [x] MyContract 的函数 call_setX 可以实现，这意味着 OtherContract 中 setX 的权限没有门槛，是很大安全隐患

4. 我们尝试依次进行如下操作：

(1) 在0xd9145CCE52D386f254917e481eB44e9943F39138 调用函数 setX(10);
(2) 在 0xd9145CCE52D386f254917e481eB44e9943F39138 调用函数 getX();
(3) 在 0x9D7f74d0C41E726EC95884E0e97Fa6129e3b5E99 调用函数 call_setX(20);
(4) 在 0x9D7f74d0C41E726EC95884E0e97Fa6129e3b5E99 调用函数 call_getX();

下列说法正确的是：

- [ ] (2)(4) 的返回结果分别是 10, 10
- [x] (2)(4) 的返回结果分别是 10, 20
- [ ] 运行 (3) 的时候会报错，因此无法继续运行 (4)
- [ ] (3) 可以顺利运行，但是运行 (4) 的时候会报错

5. 我们可以看到，OtherContract 中 setX 函数是 payable 的。如果我们想在已部署的合约 0xd9145CCE52D386f254917e481eB44e9943F39138 中调用 setX 的时候向合约转账 50 wei，那么正确的写法是：

- [ ] payable(0xd9145CCE52D386f254917e481eB44e9943F39138).setX(x, value=50);
- [ ] payable(0xd9145CCE52D386f254917e481eB44e9943F39138).setX{value: 50}(x);
- [ ] OtherContract(0xd9145CCE52D386f254917e481eB44e9943F39138).setX(x, value=50);
- [x] OtherContract(0xd9145CCE52D386f254917e481eB44e9943F39138).setX{value: 50}(x);