# 回顾C语言的语法

## 回顾

1. ![image-20221127174316507](C:\Users\12414\AppData\Roaming\Typora\typora-user-images\image-20221127174316507.png)

2. ![image-20221127174619081](C:\Users\12414\AppData\Roaming\Typora\typora-user-images\image-20221127174619081.png)

## 新类型

1. `bool`:用来描述`“ture”，“false”`在内存中占一个字节
   - 非零为真（只有当`bool`类型=0时为假）



## 内联函数

1. 通过内存膨胀的方式，以空间换时间 

2. 目的：提高运行速度

3. 内存膨胀：直接将代码放在内存中代码区，不存放在栈区

4. 实例

   ```c++
   
   #include<iostream>
   using namespace std;
   
   
   inline void printf_s(int n)
   {
       cout<<n<<endl;
   }
   
   int main()
   {
       printf_s(8);
       system("pause");
       return 0;
   }
   
   ```

   

## 函数重载

1. 在同一个项目中函数名字可以重复
2. 要求：函数名必须一致，函数参数列表不同，返回值不参与讨论
3. 尽量少使用函数重载，避免二义性

## 函数参数缺省

1. 缺省：缺少实参或者没有实参，函数的正常调用

2. 在定义的时候给形参一个默认值，如果没有给函数形参则使用默认值

3. 默认值必须从后往前给

4. 如果在main函数后面，定义的函数，声明的时候给初值，定义的时候不给

5. 实例

   ```c++
   #include<iostream>
   using namespace std;
   
   int add(int a;int b=0)//在这里初始化的时候将b=0,则将它默认值
   {
       return a+b;
   }
   
   int main()
   {
       int a=3;
       int b;
       cout<<add(a)<<endl;//这里传一个值不会出错,如果将a=0,不给b赋初值，则会报错
       return 0;
   }
   
   ```



## 引用（&）

1. 给一个变量或者对象取别名

2. 定义引用的时候必须要初始化（必须要清楚给谁起别名）

   ```c++
   int a=0;
   int&b=a;//a的别名是b
   ```



## 命名空间

1. 用来组织和重用代码的编译单元

2. 通过命名空间来避免冲突，解决重名现象

3. 作用域符号`：：`（可以都成里面的）

4. 注意定义`namespace`不加`；`

5. 支持嵌套定义，在`namespace`里面定义一个`namespace`

6. 不支持在函数里面定义一个`namespace`

7. 可以分步定义同一个命名空间(命名污染)

   ```c++
   namespace name
   {
       char ch;
   }
   namespace name
   {
       int num;
   }
   ```

8. 取别名使用`=`

   ```c++
   namespace name1=name2;
   ```

   

9. 实例

   ```c++
   namespace name_1
   {
       int num=10;
       int add(int a,int b=0)
       {
           return a+b;
       }
       void add();
   }
   
   
   void name_1::add()
   {
       cout<<"void add()"<<endl;
   }
   int main()
   {
       int a=2;
       int& b=a;
       int&& c=2;
       int num=20;
       b=10;
       cout<<a<<endl;
       cout<<c<<endl;
       cout<<num<<endl;//输出20
       cout<<name_1::num<<endl;//输出10
       system("pause");
       return 0;
   }
   ```



## `cin`和`cout`

1. 单独使用`cin`,`cout`

   ```c++
   using std::cin;
   using std::cout;
   ```



## `new`和`delete`

1. 申请单个内存

   ```c++
   int* p1=new int;
   delete p1;
   ```

   

2. 申请单个内存并赋初值

   ```c++
   int* p2=new int(10);//等效于*p2=10;
   delete p2;
   ```

3. 申请一段连续的内存

   ```c++
   int *p3=new int [3];
   delete[] p3;
   ```

4. `new`和`malloc`,`free`和`delete`的区别:

   - `new`,`delete`是关键字
   - `malloc`,`free`是函数,头文件：`<stdlib.h>`