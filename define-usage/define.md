**1. 普通宏定义**
```c
#define PI 3.1415926
```
**2. 宏函数(由于宏在编译器会自动替换，所以ADD函数替换最好加一层括号)**
```c
#define ADD(a,b) ((a)+(b))
#define MAX(a,b) ((a)>(b)?(a):(b))
```
**3. 多行宏定义**
```c
#define PRINTARR(arr,n) \
	char* format=""; \
	unsigned char space=sizeof(arr)/n;\
	if(space==2 || space==1) {\
		format="%d "; \
	}else if(space==4 || space==8){\
		format="%.2f "; \
	}\
	for(unsigned int i=0;i<n;i++) {\
		printf(format,arr[i]); \
	}
```
**4. 条件编译1: (注意，在预编译后，宏会替换为空，所以，不应该使用宏作为变量使用)**
```c
#define C_LANG_RUNTIME
#define CPP_LANG_RUNTIME

#ifndef C_LANG_RUNTIME	
#define COMPILE="C"
#endif // !C_LANG_RUNTIME

#ifndef CPP_LANG_RUNTIME
#define COMPILE="CPP"
#endif // !CPP_LANG_RUNTIME
```
**5. 条件编译2(头文件中避免重复定义)**
```c
#ifndef HTTP_H
#define HTTP_H

#endif // !HTTP_H
```
**6. 预定义的内置宏（依赖于C标准和指定的平台）[未全]**
```c
#define NOW()  __TIME__ 
#define DATE()  __DATE__
#define FILENAME()  __FILE__ 
#define LINE()  __LINE__ 
```
**7. 宏常见片段**
```c
// (1) 字段在结构体中的偏移量
#define OFFSETOF(type,field) ((size_t)&(((type*)0)->field))

// (2) 结构体中字段所占用的字节
#define FIELDSIZE(type,field) sizeof(((type*)0)->field)

// (3) 大小写互相转换
#define TO_UPPER_OR_LETTER(c) ((c)^32)

// (4) 数组中元素个数
#define SIZE_OF_ARRAY(arr) (sizeof((arr))/sizeof((arr[0])))

// (5) 数据大小比较
#define MIN(a,b) ((a)<(b)?(a):(b))
#define MAX(a,b) ((a)>(b)?(a):(b))
```

