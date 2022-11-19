# c++

## c++概念



## 简单语法

1. 头文件：`<iostream>`

   第一个代码：

   ```c
   #include<iostream>//c++头文件
   using namespace std;//命名空间，c++的概念
   
   int main()
   {
   	cout << "hello chg" << endl;//打印
       //因为使用了using nameplace std所以不用下面代码
       std::cout<<"hello chg"<<std::cout
   	return 0;
   }
   ```

2. cout<< 输出内容<<endl  =  printf("内容")

3. `stew(n)`:预设宽度

## 主函数相关变体

1. ```c
   void main()
   {
       return;
   }
   ```

2. ```c
   int main(int a,char* arr[])
   {
       return 0;
   }
   ```



## 常见关键字

![image-20221113181747946](C:\Users\12414\AppData\Roaming\Typora\typora-user-images\image-20221113181747946.png)

![image-20221113182408586](C:\Users\12414\AppData\Roaming\Typora\typora-user-images\image-20221113182408586.png)

![image-20221113190749425](C:\Users\12414\AppData\Roaming\Typora\typora-user-images\image-20221113190749425.png)

## 常见标识符

1. 注意事项![image-20221113191332583](C:\Users\12414\AppData\Roaming\Typora\typora-user-images\image-20221113191332583.png)

2.  布尔变量的定义

   ```c
   bool ans=ture;
   bool ans2=false;
   ```



## 类型修饰符

1. `unsigned`,`signed`

 