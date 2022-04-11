//string.h库函数介绍

/**
 * @description: 在参数 str 所指向的字符串的前 n 个字节中搜索第一次出现字符 c（一个无符号字符）的位置。
 * @param {void} *str 指向要执行搜索的内存块。
 * @param {int} c 以 int 形式传递的值，但是函数在每次字节搜索时是使用该值的无符号字符形式。
 * @param {size_t} n 要被分析的字节数。
 * @return {*}
 */
void *memchr(const void *str, int c, size_t n)
/*
例：
void main(void)
{
    char *res1,*res2,*res3;
    res1=memchr("aabbccbbaa",'b',2);
    res2=memchr("aabbccbbaa",'b',3);
    res3=memchr("aabbccbbaa",'b',4);
    printf("%s %s %s",res1,res2,res3);
}
输出结果：(null) bbccbbaa bbccbbaa
*/


/**
 * @description: 从存储区 str1 和存储区 str2 的第一个字节开始比较，str1 大于 str2返回1，
 *               str1 小于 str2返回-1，str1 等于 str2则继续比较下一字节，直到比较完前 n 个字节，若都相等则返回0。
 * @param {void} *str1 指向内存块的指针。
 * @param {void} *str2 指向内存块的指针。
 * @param {size_t} n 要被比较的字节数。
 * @return {*}
 * 如果返回值 < 0，则表示 str1 小于 str2。
 * 如果返回值 > 0，则表示 str1 大于 str2。
 * 如果返回值 = 0，则表示 str1 等于 str2。
 */
int memcmp(const void *str1, const void *str2, size_t n))
/*
例：
void main(void)
{
    char res1,res2,res3;
    res1=memcmp("aBc","AbC",3);
    res2=memcmp("AbC","aBc",3);
    res3=memcmp("ABCD","ABCd",3);
    printf("%d %d %d",res1,res2,res3);
}
输出结果：1 -1 0
*/


/**
 * @description: 从存储区 str2 复制 n 个字节到存储区 str1。
 * @param {void} *str1 指向用于存储复制内容的目标数组，类型强制转换为 void* 指针。
 * @param {void} *str2 指向要复制的数据源，类型强制转换为 void* 指针。
 * @param {size_t} n 要被复制的字节数。
 * @return {*} 该函数返回一个指向目标存储区 str1 的指针。
 */
void *memcpy(void *str1, const void *str2, size_t n)
/*
例：
void main(void)
{
    char *res1;
    char src[20]="abcdefghij";
    char dest[20]={0};
    char dest1[20]="*****";

    res1=memcpy(dest,src,10);
    memcpy(src,dest1,5);
    printf("%s %s %s",res1,dest,src);
}
输出结果：abcdefghij abcdefghij *****fghij
*/


/**
 * @description: 从 str2 复制 n 个字符到 str1，但是在重叠内存块这方面，memmove() 是比 memcpy() 更安全的方法。
 *               如果目标区域和源区域有重叠的话，memmove() 能够保证源串在被覆盖之前将重叠区域的字节拷贝到目标区域中，
 *               复制后源区域的内容会被更改。如果目标区域与源区域没有重叠，则和 memcpy() 函数功能相同。
 * @param {void} *str1 指向用于存储复制内容的目标数组，类型强制转换为 void* 指针。
 * @param {void} *str2 指向要复制的数据源，类型强制转换为 void* 指针。
 * @param {size_t} n 要被复制的字节数。
 * @return {*} 该函数返回一个指向目标存储区 str1 的指针。
 */
void *memmove(void *str1, const void *str2, size_t n)
/*
例：
void main(void)
{
    char *res;
    char src[20]="***";
    char dest[20]="abcdefghij";

    res=memmove(dest,src,3);
    printf("%s %s",res,dest);
}
输出结果：***defghij ***defghij
*/


/**
 * @description: 复制字符 c（一个无符号字符）到参数 str 所指向的字符串的前 n 个字符。
 * @param {void} *str 指向要填充的内存块。
 * @param {int} c 要被设置的值。该值以 int 形式传递，但是函数在填充内存块时是使用该值的无符号字符形式。
 * @param {size_t} n 要被设置为该值的字符数。
 * @return {*} 该值返回一个指向存储区 str 的指针。
 */
void *memset(void *str, int c, size_t n)
/*
例：
void main(void)
{
    char *res;
    char src[20]="*********";

    res=memset(src,'#',5);
    printf("%s %s",res,src);
}
输出结果：#####**** #####****
*/


/**
 * @description: 把 src 所指向的字符串追加到 dest 所指向的字符串的结尾。
 * @param {char} *dest 指向目标数组，该数组包含了一个 C 字符串，且足够容纳追加后的字符串。
 * @param {char} *src 指向要追加的字符串，该字符串不会覆盖目标字符串。
 * @return {*} 该函数返回一个指向最终的目标字符串 dest 的指针。
 */
char *strcat(char *dest, const char *src)
/*
例：
void main(void)
{
    char *res;
    char src[10]="56789";
    char dest[10]="01234";

    res=strcat(dest,src);
    printf("%s %s",res,dest);
}
输出结果：0123456789 0123456789
*/


/**
 * @description: 把 src 所指向的字符串前n个字符追加到 dest 所指向的字符串的结尾。
 * @param {char} *dest 指向目标数组，该数组包含了一个 C 字符串，且足够容纳追加后的字符串，包括额外的空字符。
 * @param {char} *src 要追加的字符串。
 * @param {size_t} n 要追加的最大字符数。
 * @return {*} 该函数返回一个指向最终的目标字符串 dest 的指针。
 */
char *strncat(char *dest, const char *src, size_t n)
/*
例：
void main(void)
{
    char *res;
    char src[10]="56789";
    char dest[10]="01234";

    res=strncat(dest,src,4);
    printf("%s %s",res,dest);
}
输出结果：012345678 012345678
*/


/**
 * @description: 在参数 str 所指向的字符串中搜索第一次出现字符 c（一个无符号字符）的位置。
 * @param {char} *str 要被检索的 C 字符串。
 * @param {int} c 在 str 中要搜索的字符。
 * @return {*}该函数返回在字符串 str 中第一次出现字符 c 的位置，如果未找到该字符则返回 NULL。
 */
char *strchr(const char *str, int c)
/*
例：
void main(void)
{
    char *res;
    char src='b';
    char dest[10]="aaabcdaaa";

    res=strchr(dest,src);
    printf("%s",res);
}
输出结果：bcdaaa
*/


/**
 * @description: 从字符串 str1 和字符串 str2的第一个字节开始比较，str1 大于 str2返回1，
 *               str1 小于 str2返回-1，str1 等于 str2则继续比较下一字节，直到比较完所有字节，若都相等则返回0。
 * @param {char} *str1 要进行比较的第一个字符串。
 * @param {char} *str2 要进行比较的第二个字符串。
 * @return {*}
 * 如果返回值 < 0，则表示 str1 小于 str2。
 * 如果返回值 > 0，则表示 str1 大于 str2。
 * 如果返回值 = 0，则表示 str1 等于 str2。
 */
int strcmp(const char *str1, const char *str2)
/*
例：
void main(void)
{
    int res1,res2,res3;
    res1=strcmp("aBc","AbCD");
    res2=strcmp("ABC","ABCD");
    res3=strcmp("ABC","ABC");
    printf("%d %d %d",res1,res2,res3);
}
输出结果：1 -1 0
*/


/**
 * @description: 从字符串 str1 和字符串 str2的第一个字节开始比较，str1 大于 str2返回正数，
 *               str1 小于 str2返回负数，str1 等于 str2则继续比较下一字节，直到比较完前 n 个字节，若都相等则返回0。
 * @param {char} *str1 要进行比较的第一个字符串。
 * @param {char} *str2 要进行比较的第二个字符串。
 * @param {size_t} n
 * @return {*}
 * 如果返回值 < 0，则表示 str1 小于 str2。
 * 如果返回值 > 0，则表示 str1 大于 str2。
 * 如果返回值 = 0，则表示 str1 等于 str2。
 */
int strncmp(const char *str1, const char *str2, size_t n)
/*
例：
void main(void)
{
    int res1,res2,res3;
    res1=strncmp("aBc","AbCD",3);
    res2=strncmp("ABC","ABCD",4);
    res3=strncmp("ABC","ABc",2);
    printf("%d %d %d",res1,res2,res3);
}
输出结果：32 -68 0
*/


/**
 * @description: 从字符串 str1 和字符串 str2的第一个字节开始比较，str1 大于 str2返回1，
 *               str1 小于 str2返回-1，str1 等于 str2则继续比较下一字节，
 *               直到比较完所有字节，若都相等则返回0。(结果取决于 LC_COLLATE 设置。)
 * @param {char} *str1 要进行比较的第一个字符串。
 * @param {char} *str2 要进行比较的第二个字符串。
 * @return {*}
 * 如果返回值 < 0，则表示 str1 小于 str2。
 * 如果返回值 > 0，则表示 str1 大于 str2。
 * 如果返回值 = 0，则表示 str1 等于 str2。
 */
int strcoll(const char *str1, const char *str2)
/*
例：
void main(void)
{
    int res1,res2,res3;
    res1=strcoll("aBc","AbCD");
    res2=strcoll("ABC","ABCD");
    res3=strcoll("ABC","ABC");
    printf("%d %d %d",res1,res2,res3);
}
输出结果：1 -1 0
*/


/**
 * @description: 把 src 所指向的字符串复制到 dest。
 *               需要注意的是如果目标数组 dest 不够大，而源字符串的长度又太长，可能会造成缓冲溢出的情况。
 * @param {char} *dest 指向用于存储复制内容的目标数组。
 * @param {char} *src  要复制的字符串。
 * @return {*} 该函数返回一个指向最终的目标字符串 dest 的指针。
 */
char *strcpy(char *dest, const char *src)
/*
例：
void main(void)
{
	char src[3]="FG";
	char dest[10]="ABCDE";
	char *p;

	p=strcpy(dest, src);

    printf("%s %s",dest,p);
}
输出结果：FG FG
*/


/**
 * @description: 把 src 所指向的字符串复制到 dest，最多复制 n 个字符。
 *               当 src 的长度小于 n 时，dest 的剩余部分将用空字节填充。
 * @param {char} *dest 指向用于存储复制内容的目标数组。
 * @param {char} *src 要复制的字符串。
 * @param {size_t} n 要从源中复制的字符数。
 * @return {*} 该函数返回一个指向最终的目标字符串 dest 的指针。
 */
char *strncpy(char *dest, const char *src, size_t n)
/*
例：
void main(void)
{
	char src[3]="FGH";
	char dest[6]="ABCDE";
	char *p;

	p=strncpy(dest, src, 2);

    printf("%s %s",dest,p);
}
输出结果：FGCDE FGCDE
*/


/**
 * @description: 检索字符串 str1 开头连续有几个字符都不含字符串 str2 中的字符。
 * @param {char} *str1 被检索的 C 字符串。
 * @param {char} *str2 该字符串包含了要在 str1 中进行匹配的字符列表。
 * @return {*} 该函数返回 str1 开头连续都不含字符串 str2 中字符的字符数。
 */
size_t strcspn(const char *str1, const char *str2)
/*
例：
void main(void)
{
	int len;
	char str1[] = "ABCDEFGFEDC";
	char str2[] = "EFD";

	len = strcspn(str1, str2);

    printf("%d",len);
}
输出结果：3
*/


/**
 * @description: 从内部数组中搜索错误号 errnum，并返回一个指向错误消息字符串的指针。
 *               strerror 生成的错误字符串取决于开发平台和编译器。
 * @param {int} errnum 错误号，通常是 errno。
 * @return {*} 该函数返回一个指向错误字符串的指针，该错误字符串描述了错误 errnum。
 */
char *strerror(int errnum)
/*
例：
#include <stdio.h>
#include <string.h>
#include <errno.h>
void main(void)
{
   FILE *fp;

   fp = fopen("file.txt","r");
   if( fp == NULL ) 
   {
      printf("Error: %s\n", strerror(errno));
   }
}
输出结果：Error: No such file or directory
*/


/**
 * @description: 计算字符串 str 的长度，直到空结束字符，但不包括空结束字符。
 * @param {char} *str 要计算长度的字符串。
 * @return {*} 该函数返回字符串的长度。
 */
size_t strlen(const char *str)
/*
例：
void main(void)
{
	char str1[20]="ABCDEFGH";
	char str2[20]="ABCDEFGH\0";// \0为结束符
	int len1,len2;

	len1 = strlen(str1);
	len2 = strlen(str2);
	printf("%d %d",len1,len2);
}
输出结果：8 8
*/


/**
 * @description: 检索字符串 str1 中第一个匹配字符串 str2 中字符的字符，不包含空结束字符。
 *               也就是说，依次检验字符串 str1 中的字符，当被检验字符在字符串 str2 中也包含时，则停止检验，并返回该字符位置。
 * @param {char} *str1 要被检索的 C 字符串。
 * @param {char} *str2 该字符串包含了要在 str1 中进行匹配的字符列表。
 * @return {*} 该函数返回指向 str1 中第一个匹配字符串 str2 中字符的指针，如果未找到字符则返回 NULL。
 */
char *strpbrk(const char *str1, const char *str2)
/*
例：
void main(void)
{
	char str1[20]="ABCDEFGEFG";
	char str2[20]="FE";
	char *ret;

	ret = strpbrk(str1, str2);
	printf("%s",ret);
}
输出结果：EFGEFG
*/


/**
 * @description: 在参数 str 所指向的字符串中搜索最后一次出现字符 c（一个无符号字符）的位置。
 * @param {char} *str 要被检索的 C 字符串。
 * @param {int} c 要搜索的字符。以 int 形式传递，但是最终会转换回 char 形式。
 * @return {*} 该函数返回指向 str 中最后一次出现字符 c 的指针。如果未找到该值，则函数返回一个空指针。
 */
char *strrchr(const char *str, int c)
/*
例：
void main(void)
{
	char str[20]="ABCDEFGEFG";
	char ch='E';
	char *ret;

	ret = strrchr(str, ch);
	printf("%s",ret);
}
输出结果：EFG
*/


/**
 * @description: 检索字符串 str1 中第一个不在字符串 str2 中出现的字符在str1中的位置。
 * @param {char} *str1 要被检索的 C 字符串。
 * @param {char} *str2 该字符串包含了要在 str1 中进行匹配的字符列表。
 * @return {*} 该函数返回 str1 中第一个不在字符串 str2 中出现的字符在str1中的位置。
 */
size_t strspn(const char *str1, const char *str2)
/*
例：
void main(void)
{
	char str1[20]="ABCDEFG";
	char str2[20]="ABCD";
	int len;

	len = strspn(str1, str2);
	printf("%d",len);
}
输出结果：4
*/

/**
 * @description: 在字符串 str1 中查找第一次出现字符串 str2 的位置，不包含终止符 '\0'。
 * @param {char} *str1 要被检索的 C 字符串。
 * @param {char} *str2 在 str1 字符串内要搜索的小字符串。
 * @return {*} 该函数返回在 str1 中第一次出现 str2 字符串的位置，如果未找到则返回 null。
 */
char *strstr(const char *str1, const char *str2)
/*
例：
void main(void)
{
	char str1[20]="ABCDEFGEFG";
	char str2[10]="EFG";
	char *ret;

	ret = strstr(str1, str2);
	printf("%s",ret);
}
输出结果：EFGEFG
*/


/**
 * @description: 以 str2 为分隔符分解字符串 str1 。
 * @param {char} *str1 要被分解的字符串。
 * @param {char} *str2 包含分隔符的 C 字符串。
 * @return {*} 该函数返回被分解的第一个子字符串，如果没有可检索的字符串，则返回一个空指针。
 */
char *strtok(char *str1, const char *str2)
/*
例：
void main(void)
{
	char str[20] = "ABC-DEF-GH";
	char s[2] = "-";
	char *res;

	/* 获取第一个子字符串 */
	res = strtok(str, s);

	/* 继续获取其他的子字符串 */
	while( res != NULL )
	{
		printf( "%s\n", res );

		res = strtok(NULL, s);
	}
}
输出结果：
ABC
DEF
GH
*/


/**
 * @description: 根据程序当前的区域选项中的 LC_COLLATE 来转换字符串 src2 的前 n 个字符，并把它们放置在字符串 src1 中。
 * @param {char} *str1 指向存储内容的目标数组的指针，如果参数 n 为 0，则它是一个空指针。
 * @param {char} *src2 要被转换的字符串。
 * @param {size_t} n 被复制到 str1 的最大字符数。
 * @return {*} 该函数返回被转换字符串的长度，不包括空结束字符。
 */
size_t strxfrm(char *str1, const char *src2, size_t n)
/*
例：
void main(void)
{
	char dest[20];
	char src[20]="ABCDEFGH";
	int len;

	len = strxfrm(dest, src, 20);

	printf("%s %d",dest,len);
}
输出结果：ABCDEFGH 8
*/
