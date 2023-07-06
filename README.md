# C-p40-1-
C语言学习笔记 p40指针笔试面试题讲解(1)
#include<stdio.h>
#include<string.h>
int main()
{
    chard arr[]="abcdef";
    printf("%d\n",sizeof(arr));//7 sizeof(arr)计算的是数组的大小
    printf("%d\n",sizeof(arr+0));//4/8 计算的是首元素地址的大小
    printf("%d\n",sizeof(*arr));//1 *arr是首元素，sizeof(*arr)计算的是首元素的大小
    printf("%d\n",sizeof(arr[1]));//1 arr[1]计算的是第二个元素的大小
    printf("%d\n",sizeof(&arr));//4/8 整个数组的大小 &arr虽然是数组的地址 但仍是地址
    printf("%d\n",sizeof(&arr+1));// 4/8 &arr+1是跳过整个数组后的地址，但也是地址
    printf("%d\n",sizeof(&arr[0]+1));//4/8 第二个元素的地址
    return 0;
}

int main()
{
    char arr[]="abcdef";
    printf("%d\n",strlen(arr));//6
    printf("%d\n",strlen(arr+0));//6
    printf("%d\n",strlen(*arr));//err 这里解引用不是地址而是一个数字97 所以是非法访问内存
    printf("%d\n",strlen(arr[1]));//err 这里传了一个98 依然非法访问内存
    printf("%d\n",strlen(&arr));//6 &arr-数组的地址-数组指针char (*p)[7]=&arr,这里类型不兼容，但不影响
    printf("%d\n",strlen(&arr+1));//随机值
    printf("%d\n",strlen(&arr[0]+1));//5
    return 0;
}

int main()
{
    char* p="abcdef";//这里因为是char* 保存的是p的第一个元素a的地址

    printf("%d\n",sizeof(p));//4/8 计算指针变量p的大小
    printf("%d\n",sizeof(p+1));//4/8 p+1计算的是b的地址{
    printf("%d\n",sizeof(*p));//1 *p就是字符串的第一个字符-‘a'
    printf("%d\n",sizeof(p[0]));//int arr[10];arr[0]=="(arr+0) p[0]==*(p+0) p[0]==*(p+0)=='0'
    printf("%d\n",sizeof(&p));//4/8
    printf("%d\n",sizeof(&p+1));//4/8
    printf("%d\n",sizeof(&p[0]+1));//4/8
    return 0;
}

int main()
{
    char* p="abcdef";
   
    printf("%d\n",strlen(p));//6
    printf("%d\n",strlen(p+1));//5 
    printf("%d\n",strlen(*p));//err
    printf("%d\n",strlen(p[0]));//err
    printf("%d\n",strlen(&p));//随机值
    printf("%d\n",strlen(&p+1));//随机值
    printf("%d\n",strlen(&p[0]+1));//5
    return 0;
}

