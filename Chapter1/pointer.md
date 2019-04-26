# 指针

保存另一个变量的地址的变量

```c++
#include <iostream>
using namespace std;

int main() {

    int val = 20;   //实际变量的声明
    int *ip;    //指针变量的声明
    ip = &val;

    cout << "Value of val variable: ";
    cout << val << endl;

    // 输出在指针变量中存储的地址
    cout << "Address stored in ip variable: ";
    cout << ip << endl;

    // 访问指针中地址的值
    cout << "Value of *ip variable: ";
    cout << *ip << endl;

    return 0;
}
```

### NULL 指针

>  在我的 ubuntu 64 位机上，指针声明时如果没有初始化的话默认赋值为 NULL；

如果指针没有确切的地址指向，可以赋值为空指针 NULL，是标准库的值为零的常量。内存地址为 0 表示该内存地址不可访问，空指针表示不指向任何地址。

可以通过 if 语句检查是否有空指针，NULL 代表0为false，其他地址非0为true

```c++
define NULL 0	// NULL 实际上定义为 0
```

## 指针的算术运算

可以对指针执行四种算术运算：++, --, +, -

如果指针是某类型的指针，每次加一减一移动的是这个类型所占的字节数，效果就是指向下一个该类型的值所在的地址。

```c++
#include <iostream>
using namespace std;
/**
 * 通过指针遍历数组
 * @return 
 */
int main() {
    
    int nums[7] = {1,2,3,4,5,6,7};
    
    int *p = nums;
    
    for(int i=0; i < 7; i++){
        cout << "nums[" << i <<"] 的地址是：";
        cout << p <<endl;
        cout << "nums[" << i <<"] 的值是：";
        cout << *p <<endl;
        
        //移动到下一个位置
        p++;
    }

    return 0;
}
```

## 指针的比较

指针的值可以比较，比较的是地址值。通过 ==, <, > 等，一般是两个指针相关，比如同一数组的不同元素的指针

## 指针 VS 数组

数组名实际上是一个指针，指向数组的开头，但它是一个指针常量，不能改变其地址值，但是可以改变地址所指向的内存中的值

```c++
#include <iostream>
 
using namespace std;
const int MAX = 3;
 
int main ()
{
   int  var[MAX] = {10, 100, 200};
 
   for (int i = 0; i < MAX; i++)
   {
      *var = i;    // 这是正确的语法
      var++;       // 这是不正确的
   }
   return 0;
}

```

## 指针数组

可以定义存储指针的数组，数组的每个元素是一个指针

```c++
#include <iostream>
using namespace std;
/**
 * 通过指针数组遍历数组
 * @return
 */
int main() {

    int nums[7] = {1,2,3,4,5,6,7};

    int* pnums[7];


    for(int i=0; i < 7; i++){
        pnums[i] = &nums[i];
    }

    for(int i=0; i < 7; i++){
        cout << "nums[" << i << "]的地址是：" << pnums[i] << endl;
        cout<< "nums[" << i << "]的值是：" << *pnums[i] << endl;

    }

    return 0;
}
```

### 指向指针的指针

可以创建指向其他指针的地址的指针

```c++
#include <iostream>
 
using namespace std;
 
int main ()
{
    int  var;
    int  *ptr;
    int  **pptr;
 
    var = 3000;
 
    // 获取 var 的地址
    ptr = &var;
 
    // 使用运算符 & 获取 ptr 的地址
    pptr = &ptr;
 
    // 使用 pptr 获取值
    cout << "var 值为 :" << var << endl;
    cout << "*ptr 值为:" << *ptr << endl;
    cout << "**pptr 值为:" << **pptr << endl;
 
    return 0;
}
```





