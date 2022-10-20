1. returns关键字的作用

- [ ] 用于函数主体中，返回指定的变量
- [ ] 加在函数名后面，用于声明返回的变量类型及变量名

2. return关键字的作用

- [ ] 加在函数名后面，用于声明返回的变量类型及变量名
- [ ] 用于函数主体中，返回指定的变量

3. 采用命名式返回的函数主体中能否使用return?

- [ ] 能
- [ ] 不能
- [ ] 视函数返回的数据类型和数量而定

4. 解构式赋值能否只读取函数部分返回值

- [ ] 能
- [ ] 不能
- [ ] 视函数返回的数据类型和数量而定

5. 假设存在如下函数：
function returnNamed() public pure returns(uint256 , bool , string, uint256[3] memory)，
那么它可能的返回结果是？

- [ ] return (64, true, true, [1, 2, 3])
- [ ] return (64, true, "abcd", [1, 2, 3])
- [ ] return (64, "abcd", [1, 2, 3])
- [ ] return ( , true, "abcd", [1, 2, 3])

6. 下列属于命名式返回的是

- [ ] function returnNamed() public pure returns(uint256 _number, bool _bool, uint256[3] memory _array)
- [ ] function returnNamed() public pure returns(_number, _bool, _array)
- [ ] function returnNamed() public pure returns(uint256 , bool , uint256[3] memory)

7. 假设存在如下函数：
    function returnNamed() public pure returns(uint256 _number, bool _bool, string 
memory _str){
        _number = 2;
    }
那么调用该函数返回的结果是？

8. 假设存在如下函数：
function returnMultiple() public pure returns(uint256, bool, uint256[3] memory){
        return(1, true, [1,2,5]);
    }
那么下面哪个选项正确使用了该函数？

- [ ] bool _bool ; (, ,_bool) = returnMultiple();
- [ ] bool _bool ; (, _bool, ) = returnMultiple();
- [ ] bool _bool ; (_bool) = returnMultiple();
- [ ] bool _bool ; (_bool, , ) = returnMultiple();