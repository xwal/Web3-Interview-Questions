1. 下面定义变量的语句中，会报错的一项是：

- [ ] uint256 public constant x1;
- [ ] uint256 public constant x2 = 10;
- [ ] uint256 public immutable x3;
- [ ] uint256 public immutable x4 = 10;

2. 下面定义变量的语句中，会报错的一项是：

- [ ] string constant x5 = "hello world";
- [ ] address constant x6 = address(0);
- [ ] string immutable x7 = "hello world";
- [ ] address immutable x8 = address(0);

3. 下面哪一项不符合对 constant 和 immutable 的描述？

- [ ] constant 变量初始化之后，尝试改变它的值，会编译不通过
- [ ] immutable 变量初始化之后，尝试改变它的值，会编译不通过
- [ ] constant 和 immutable 的使用可以增强合约的安全性
- [ ] constant 和 immutable 的使用并不会节省 gas

4. 在如下的合约中，我们定义了四个 immutable 的变量 y1, y2, y3, y4。
uint256 immutable y1;
address immutable y2;
address immutable y3;
uint256 immutable y4;
constructor (uint256 _y4){
    y1 = block.number;
    y2 = address(this);
    y3 = msg.sender;
    y4 = _y4;
}

其中，确实有必要在构造函数 constructor 中才赋值的一项是：

- [ ] y1
- [ ] y2
- [ ] y3
- [ ] y4

5. 下列哪一个变量不适合用 constant 或 immutable 来修饰？

- [ ] 合约的部署者地址
- [ ] 合约的部署时间
- [ ] 合约中的 ETH 数量
- [ ] 合约本身的地址