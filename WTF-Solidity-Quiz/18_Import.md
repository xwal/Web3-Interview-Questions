1. Solidity中import的作用是：

- [ ] 导入其他合约中的接口
- [ ] 导入其他合约中的私有变量
- [x] 导入其他合约中的全局符号
- [ ] 导入其他合约中的内部变量

2. import导入文件的来源可以是：

- [ ] 源文件网址
- [ ] npm的目录
- [ ] 本地文件
- [x] 以上都可以

3. 以下import写法错误的是：

- [x] import from"./Yeye.sol";
- [ ] import {Yeye} from "./Yeye.sol";
- [ ] import {Yeye as Wowo} from "./Yeye.sol";
- [ ] import * as Wowo from "./Yeye.sol";

4. import导入文件中的全局符号可以单独指定其中的：

- [ ] 合约
- [ ] 纯函数
- [ ] 结构体类型
- [x] 以上都可以

5. 被导入文件中的全局符号想要被其他合约单独导入，应该怎么编写？

- [ ] 将合约结构包含
- [ ] 包含在合约结构中
- [x] 与合约并列在文件结构中