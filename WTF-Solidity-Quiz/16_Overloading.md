1. 什么是函数重载（Overloading）?

- [ ] 名字相同但输入参数类型不同的函数可以同时存在，他们被视为不同的函数。
- [ ] 子合约中函数继承并改写父合约的函数。
- [ ] 在创建合约时执行一次的函数，用于初始化合约状态

2. Solidity中是否允许修饰器（modifier）重载？

- [ ] 允许
- [ ] 不允许

3. 下面两个函数的函数选择器是否相同？

function saySomething() public pure returns(string memory){ 
  return("Nothing"); 
} 
 
function saySomething(string memory something) public pure returns(string memory){ 
  return(something); 
}

- [ ] 相同
- [ ] 不相同

4. 使用上一题代码，如果我们调用 saySomething("WTF")，返回值为：

- [ ] "Nothing"
- [ ] "WTF"
- [ ] 报错

5. 下面两个函数的函数选择器是否相同？

function f(uint8 _in) public pure returns (uint8 out) { 
 out = _in; 
 } 

function f(uint256 _in) public pure returns (uint256 out) { 
 out = _in; 
 }

- [ ] 相同
- [ ] 不相同

6. 使用上一题代码，如果我们调用 f(50)，返回值为：

- [ ] 50
- [ ] 0x32
- [ ] 报错