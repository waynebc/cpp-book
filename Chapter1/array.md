# 数组

存储一系列相同类型的值，可以通过下标随即访问，随即访问效率高；一片连续的内存空间，在中间添加或删除元素需要移动其他数组元素，效率低。

## 数组的创建、初始化和访问

```c++
#include <iostream>
using namespace std;
int main() {
    //创建数组
    int nums[8];
    //创建数组的时候初始化
    int nums1[2] = {1,2};
    int nums2[] = {1,2,3};	//数组长度为3
    cout << "数组未初始化时各个元素是随机值：" << endl;
    for(int n : nums){
        cout << n << " ";
    }
    cout << endl;

    //初始化数组
    for(int i=0; i<8; i++){
        nums[i] = i + 100;
    }

    cout << "遍历输出数组初始化后的值：" << endl;
    for(int i=0; i<8; i++){
        cout << nums[i] << " ";
    }
    cout << endl;

    return 0;
}
```

- 初始化数组的时候可以只初始化部分值，其后的值会自动初始化为0。不初始化的话数组元素为随机值

## 多维数组

```c++
#include <iostream>
using namespace std;
int main() {

    //可以通过内嵌括号的方式初始化
    int a[3][4] = {
            {1,2,3,4},
            {5,6,7,8},
            {23,4,12,4}
    };
    //也可以不加内嵌括号，效果与上面相同
    int b[3][4] = {
            1,2,3,4,
            5,6,7,8,
            23,4,12,4
    };

    //遍历二维数组
    for(int i=0; i<3; i++){
        for(int j=0; j<4; j++){
            cout << a[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

## 传递数组给函数

- 形式参数是一个指针
- 形式参数是一个已定义大小的数组
- 形式参数是一个未定义大小的数组

```c++
void func1(int* param);	//形参是指针
void func2(int param[10]);	//形参是已定义大小的数组
void func3(int param[]);	//形参是未定义大小的数组
```

## 从函数返回数组

C++ 不允许返回类型为数组，只能返回指针

另外，C++ 不支持在函数外返回局部变量的地址（栈上分配的变量的生命周期为函数内），除非定义局部变量为 static 变量