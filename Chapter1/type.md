# 数据类型

## 基本类型

| 类型 | 关键字 | 长度（字节） |
| :--: | :--: | :----: |
| 布尔型 | bool | 1 |
| 字符型 | char | 1 |
| 整型 | int | 4 |
| 浮点型 | float | 4 |
| 双浮点型 | double | 8 |
| 无类型 | void |  |
| 宽字符型 | wchar_t | 2 |

### 基本类型修饰符

- signed
- unsigned
- short
- long

### wchar_t 本质

```c++
typedef wchar_t short int;
```

### 类型所占字节数
`sizeof(int)`

### 类型的最大值和最小值
- **最小值**：`(numeric_limits<int>::min)()`
- **最大值**：`(numeric_limits<int>::max)()`

### 

### 指针

int a = 100;

int* p = &a;

### 数组

int[] a = {1,2,3};

### 字符串

char[] a = "12345";

### 结构体

struct

### 枚举

enum

### 联合体

union

### 模板

template

### 类

class