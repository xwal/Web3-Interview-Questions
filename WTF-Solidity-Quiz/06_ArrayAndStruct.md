1. 以下选项中不属于固定长度数组的是

- [ ] uint[100] array0;
- [ ] address[] array1;
- [ ] byte[3] array2;
- [ ] bool[100] array3;

2. 以下选项中不属于可变长度数组的是

- [ ] uint[] array0;
- [ ] bytes array1;
- [ ] address[6] array2;
- [ ] byte[] array3;

3. 以下关于数组的说法中，正确的是

- [ ] 固定长度数组 和 bytes拥有 push() 成员，可以在数组最后添加一个0元素。
- [ ] 数组字面常数，例如 [uint(1),2,3]，需要声明第一个元素的类型，不然默认用存储空间最大的类型。
- [ ] 内存数组的长度在创建后是固定的。
- [ ] 对于memory可变长度数组，可以用new操作符来创建，并且不用声明长度，例如uint[] memory array = new uint[];。

4. 数组和结构体分别属于什么类型

- [ ] 数值类型和引用类型
- [ ] 引用类型和引用类型
- [ ] 数值类型和数值类型
- [ ] 引用类型和数值类型

5. 以下关于结构体的说法中，错误的是

- [ ] 通过结构体的形式可以定义新的类型。
- [ ] 结构体内可以包含字符串，整型等基本数据类型，也可以包含数组，映射，结构体等复杂类型。
- [ ] 结构体内可以包含其本身。

6. 有如下一段合约代码，执行 initStudent 方法后，student.id 和 student.score 的值分别为
contract StructTypes {
    struct Student{
        uint256 id;
        uint256 score;
    }
   Student student;
   function initStudent() external{
        student.id = 100;
        student.score = 200;
        Student storage _student = student;
        _student.id = 300;
        _student.score = 400;
    }
}

- [ ] 300 400
- [ ] 100 200
- [ ] 300 200
- [ ] 100 400