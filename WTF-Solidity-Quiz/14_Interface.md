1. 已知foo是一个未实现的函数，那么下面代码中书写正确的是？

- [ ] abstract contract A{ function foo(uint a) internal pure virtual returns(uint); }
- [ ] contract A{ function foo(uint a) external pure virtual returns(uint); }
- [ ] abstract contract A{ function foo(uint a) public view returns(uint); }
- [ ] contract A{ function foo(uint a) internal returns(uint); }

2. 被标记为abstract的合约能否被部署？

- [ ] 能
- [ ] 不能
- [ ] 如果实现了所有函数的子合约已经被部署，则该合约能被部署

3. 下列关于接口的规则中，错误的是

- [ ] 不能继承除接口外的其他合约
- [ ] 不能包含构造函数
- [ ] 不能包含状态变量
- [ ] 所有函数都必须是external且不能有函数体
- [ ] 继承接口的合约可以不实现接口定义的全部功能

4. 下列关于接口的描述，错误的是

- [ ] 如果已知一个合约实现了IERC20接口，那么还需要知道它具体代码实现，才可以与之交互
- [ ] 接口提供了每个函数的函数签名
- [ ] 接口与合约ABI等价，可以相互转换
- [ ] 接口提供了自身的接口id
- [ ] 接口提供了合约里每个函数的选择器

5. 已知Azuki的合约地址为0xED5AF388653567Af2F388E6224dC7C4b3241C544，那么利用该地址创建接口合约变量的语句是

- [ ] IERC721 Azuki = interface(0xED5AF388653567Af2F388E6224dC7C4b3241C544)
- [ ] IERC721 Azuki = abstract(0xED5AF388653567Af2F388E6224dC7C4b3241C544)
- [ ] IERC721 Azuki = IERC721(0xED5AF388653567Af2F388E6224dC7C4b3241C544)
- [ ] IERC721 Azuki = "0xED5AF388653567Af2F388E6224dC7C4b3241C544"

6. 已知Azuki合约中存在ownerOf(uint256 tokenId)函数可用来查询某一NFT的拥有者，现在vitalik想利用上文中创建的接口合约变量调用这一函数，并写出了如下代码：
function  ownerOfAzuki(uint256 id) external view returns (address){ 
      _________________________________
 }
那么下面哪个选项可以填在横线处？

- [ ] return Azuki.ownerOf(id);
- [ ] return ownerOf(id);
- [ ] return Azuki.ownerOfAzuki(id);
- [ ] return Azuki(ownerOf, id);

7. 已知Azuki合约中存在approve(address to, uint256 tokenId)函数可以让NFT的拥有者将自己某一NFT的许可权授予另一地址，且该函数没有返回值，现在某个Azuki拥有者想利用上文中创建的接口合约变量调用这一函数  ，那么他写出的代码可能是？
*
- [ ] function approveAzuki(address to, uint256 id) external view returns(bool){ Azuki.approve(to, id);}
- [ ] function approveAzuki(address to, uint256 id) external returns(bool){ Azuki.approve(to, id);}
- [ ] function approveAzuki(address to, uint256 id) external{ Azuki.approve(to, id);}
- [ ] function approveAzuki(address to, uint256 id) external view { Azuki.approve(to, id);}