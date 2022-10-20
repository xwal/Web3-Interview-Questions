1. 关于库函数的描述，下列描述错误的是：

- [ ] 必须熟悉库函数的代码实现，才能够使用库函数
- [ ] 库函数可以减少gas fee
- [ ] 库函数可以提高solidity代码复用性
- [ ] 库函数是一种特殊的合约

2. 库合约和普通合约的区别，下列描述错误的是：

- [ ] 库合约不能存在状态变量
- [ ] 库合约不能继承
- [ ] 库合约可以被继承
- [ ] 库合约不能被销毁

3. 以下属于常用库函数的有：

- [ ] String
- [ ] Address
- [ ] Create2
- [ ] Arrays
- [ ] 以上全部

4. String库合约是将uint256类型转换为相应的string类型的代码库，toHexString()为其中将uint256转换为16进制，在转换为string。
在以下利用"using for"指令，调用toHexString()。返回值return出正确的写法为：

    // 利用using for指令
    using Strings for uint256;
    function getString1(uint256 _number) public pure returns(string memory){
        return _____________
    }

- [ ] toHexString();
- [ ] toHexString(_number);
- [ ] _number.toHexString();
- [ ] String.toHexString();

5. 以下，通过库合约名称调用toHexString()，返回值return出正确的写法为：

    // 直接通过库合约名调用    function getString2(uint256 _number) public pure returns(string memory){
        return _______________
    }

- [ ] toHexString();
- [ ] toHexString(_number);
- [ ] Strings.toHexString();
- [ ] Strings.toHexString(_number);