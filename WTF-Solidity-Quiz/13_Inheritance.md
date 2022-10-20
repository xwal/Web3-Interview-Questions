1. 对virtual关键字描述正确的是：

- [ ] 父合约中的函数，如果希望子合约重写，需要加上该关键字。
- [ ] 子合约中重写了父合约中的函数，需要加上该关键字。

2. 对override关键字描述正确的是：

- [ ] 父合约中的函数，如果希望子合约重写，需要加上该关键字。
- [ ] 子合约中重写了父合约中的函数，需要加上该关键字。

3. 下面哪个选项表示A合约继承了B合约：

- [ ] contract A override B
- [ ] contract A is B
- [ ] contract A virtual B

4. function a() public override{} 意思是

- [ ] 希望子合约重写函数a()
- [ ] 函数a()重写了父合约中的同名函数

5. 如果合约B继承了合约A，合约C要继承A和B，要怎么写？

- [ ] contract C is A, B
- [ ] contract C is B, A
- [ ] contract C is B

6. 合约B继承了合约A，下面选项中，正确调用父合约构造函数的是：

- [ ] constructor(uint _num) { A(_num);}
- [ ] constructor(uint _num) { A.constructor(_num);}
- [ ] constructor(uint _num) A(_num){}

7. 合约B继承了合约A，两个合约都有pop()函数，下面选项中，正确调用父合约函数的是：

- [ ] A.pop();
- [ ] super.pop();
- [ ] 都正确