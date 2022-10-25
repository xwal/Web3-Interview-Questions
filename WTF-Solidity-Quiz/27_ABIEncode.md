1. 当我们调用智能合约时，传递给合约的数据的前若干个字节被称为“函数选择器 (Selector)”，它告诉合约我们想要调用哪个函数。假设我们想要调用的函数在智能合约中定义声明如下：

function foo(uint256 n, address sender, string s) public view returns(bool b)

那么该函数对应的函数选择器为：

- [ ] "foo(uint256,address,string)"
- [ ] "foo(uint256 n, address sender, string s)"
- [ ] keccak("foo(uint256,address,string)")
- [ ] keccak("foo(uint256 n, address sender, string s)")
- [x] bytes4(keccak("foo(uint256,address,string)"))
- [ ] bytes4(keccak("foo(uint256 n, address sender, string s)"))

2. 下列有关ABI编码的函数中，返回值不可能当作调用智能合约的数据的一项是：

- [ ] abi.encode
- [x] abi.encodePacked
- [ ] abi.encodeWithSignature
- [ ] abi.encodeWithSelector

3. 函数abi.decode用于将二进制编码解码，它对应的逆向操作函数（反函数）是：

- [x] abi.encode
- [ ] abi.encodePacked
- [ ] abi.encodeWithSignature
- [ ] abi.encodeWithSelector

4. 已知函数foo在智能合约中定义声明如下：

function foo(uint256 a) public view

而字符串"foo(uint256)"的keccak256哈希值为：

0x2fbebd3821c4e005fbe0a9002cc1bd25dc266d788dba1dbcb39cc66a07e7b38b

那么，当我们希望调用函数foo()时，以下生成调用数据的写法中，正确且最节省gas的一项是：

- [ ] abi.encodeWithSignature("foo(uint256)", a)
- [ ] abi.encodeWithSelector("foo(uint256)", a)
- [ ] abi.encodeWithSelector(bytes(keccak256("foo(uint256)")), a)
- [x] abi.encodeWithSelector(bytes4(0x2fbebd38), a)