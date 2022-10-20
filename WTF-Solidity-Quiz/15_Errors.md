1. Solidity抛出异常的方法有：

- [ ] error
- [ ] require
- [ ] assert
- [ ] 以上都是

2. 判断：对于error, 在合约执行过程中，可以搭配revert，也可以单独使用。

- [ ] 正确
- [ ] 错误

3. 判断： error可以带有参数。

- [ ] 正确
- [ ] 错误

4. require的使用方法为： require(检查条件，"异常的描述") 
判断：require消耗gas的数量会随着检查条件的增多以及"异常的描述"变长而增加。

- [ ] 正确
- [ ] 错误

5. 判断： assert和require一样，可以解释抛出异常的原因。

- [ ] 正确
- [ ] 错误

6. error，require和assert三种方法的gas消耗，从大到小依次为：

- [ ] error > require > assert
- [ ] assert > error > require
- [ ] require > assert > error
- [ ] assert > require > error

7. 在有以下定义的前提下，以下实现中能够正确抛出异常的写法为：
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.4;
error TransferNotOwner(); // 自定义 error

contract Errors {
    mapping(uint256 => address) private _owners;
}
```

- [ ] error方法
```solidity
function transferOwner1(unint256 tokenId, address newOwner) public {
    if(_owners[tokenId] != msg.sender) {
        TransferNotOwner();
    }
    _owners[tokenId] = newOwner;
}
```
- [ ] require方法
```solidity
function transferOwner2(unint256 tokenId, address newOwner) public {
    require(_owners[tokenId] == msg.sender);
    _owners[tokenId] = newOwner;
}
```
- [ ] assert方法
```solidity
function transferOwner3(unint256 tokenId, address newOwner) public {
    assert(_owners[tokenId] == msg.sender, "Transfer Not Owner");
    _owners[tokenId] = newOwner;
}
```