1. 下面三种发送ETH的方法中，哪一种没有gas限制？

- [ ] send
- [x] call
- [ ] transfer

2. 下面三种发送ETH的方法中，哪一种发送失败会自动revert交易?

- [ ] send
- [x] transfer
- [ ] call

3. transfer的gas限制为？

- [ ] 2400
- [ ] 23000
- [x] 2300
- [ ] 24000

4. vitalik写了一个合约，并且该合约在被部署时可以转ETH进去，那么该合约的构造函数可能为？

- [ ] constructor() {}
- [ ] constructor(uint256 _amount) payable{ (address(this)).transfer(_amount); }
- [x] constructor() payable{}

5. vitalik写了一个用send()发送ETH的函数：
error SendFailed(); 
function sendETH(address payable _to, uint256 amount) external payable{
            ______________________________________
    }
该函数执行失败时会自动revert交易，那么下面哪个选项可以填入横线处？

- [x] bool success = _to.send(amount); if( !success ){ revert SendFailed(); }
- [ ] bool success = _to.send{value: amount}(" "); if( !success ){ revert SendFailed(); }
- [ ] bool success = _to.call(amount); if( !success ){ revert SendFailed(); }
- [ ] _to.send(amount);

6. vitalik又写了一个用call()发送ETH的函数：
error CallFailed();
function callETH(address payable _to, uint256 amount) external payable{
            ______________________________________
    }
该函数执行失败时会自动revert交易，那么下面哪个选项可以填入横线处？

- [ ] _to.call(amount);
- [ ] bool success = _to.call{value: amount}(" "); if( !success ){ revert CallFailed(); }
- [ ] (bool success,) = _to.call(amount); if( !success ){ revert CallFailed(); }
- [x] (bool success,) = _to.call{value: amount}(" "); if( !success ){ revert CallFailed(); }

7. 假设存在如下两个合约(sendETH和ReceiveETH)，两个合约目前ETH余额皆为0，现在vitalik想通过SendETH合约的callETH函数往ReceiveETH合约转入1ETH，他将交易的value设置为2ETH，同时交易成功执行，那么此时sendETH合约和ReceiveETH的ETH余额分别为？（题在下方）

```solidity
error SendFailed();
error CallFailed();

contract SendETH {
    constructor() payable{}
    receive() external payable {}
    function callETH(address payable _to, uint256 amount) external payable{
        (bool sucess,) - _to.call{value: amount}("");
        if(!sucess) {
            revert CallFailed();
        }
    }
}

contract ReceiveETH {
    event Log(uint amount, uint gas);
    receive() external payable{
        emit Log(msg.value, gasLeft());
    }
}
```

- [ ] 0ETH；1ETH
- [ ] 2ETH；0ETH
- [x] 1ETH；1ETH
- [ ] 0ETH；2ETH