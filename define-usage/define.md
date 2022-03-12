**1. ��ͨ�궨��**
```c
#define PI 3.1415926
```
**2. �꺯��(���ں��ڱ��������Զ��滻������ADD�����滻��ü�һ������)**
```c
#define ADD(a,b) ((a)+(b))
#define MAX(a,b) ((a)>(b)?(a):(b))
```
**3. ���к궨��**
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
**4. ��������1: (ע�⣬��Ԥ����󣬺���滻Ϊ�գ����ԣ���Ӧ��ʹ�ú���Ϊ����ʹ��)**
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
**5. ��������2(ͷ�ļ��б����ظ�����)**
```c
#ifndef HTTP_H
#define HTTP_H

#endif // !HTTP_H
```
**6. Ԥ��������ú꣨������C��׼��ָ����ƽ̨��[δȫ]**
```c
#define NOW()  __TIME__ 
#define DATE()  __DATE__
#define FILENAME()  __FILE__ 
#define LINE()  __LINE__ 
```
**7. �곣��Ƭ��**
```c
// (1) �ֶ��ڽṹ���е�ƫ����
#define OFFSETOF(type,field) ((size_t)&(((type*)0)->field))

// (2) �ṹ�����ֶ���ռ�õ��ֽ�
#define FIELDSIZE(type,field) sizeof(((type*)0)->field)

// (3) ��Сд����ת��
#define TO_UPPER_OR_LETTER(c) ((c)^32)

// (4) ������Ԫ�ظ���
#define SIZE_OF_ARRAY(arr) (sizeof((arr))/sizeof((arr[0])))

// (5) ���ݴ�С�Ƚ�
#define MIN(a,b) ((a)<(b)?(a):(b))
#define MAX(a,b) ((a)>(b)?(a):(b))
```

