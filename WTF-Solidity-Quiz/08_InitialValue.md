1. address类型的初始值是：

- [ ] 0
- [ ] 0x0
- [ ] 0x0000000000000000000000000000000000000000
- [ ] 0x000000000000000000000000000000000000dEaD

2. bool类型的初始值是：

- [ ] true
- [ ] false
- [ ] 1
- [ ] 0

3. bytes1的初始值是：

- [ ] 0
- [ ] 1
- [ ] 0x0
- [ ] 0x00

4. 
string  public _string = "true";
function d() external returns(string memory){
delete _string;
return _string;
}
调用函数d，将返回：

- [ ] true
- [ ] false
- [ ] 0
- [ ] ""

5. 
mapping(address => uint256) private _balances;
这是ERC20合约中的一行代码，其中未记录的用户的_balances值是：

- [ ] 0
- [ ] false
- [ ] 无法判断
- [ ] 依据整体代码而定