<!--
[date]: 2011-10-03
[title]:	[C/C++] 計時
[name]:	c_cplusplus-timing
[tag]:		C/C++, time | 計時
-->

C/C++ 中的使用 clock() 函數來計時，回傳的資料型別為 clock_t。
使用該函式與該資料型別時，必須要引入標頭檔 time.h （#include）。（C++可引入 ctime 此標頭檔）

<!--more-->

## Definition

函式定義為：`clock_t clock(void);`
回傳該程式執行後，所佔用的CPU時間（tick）。

`clock_t` 為保留時間用的資料型別，其定義為：

	#ifndef     _CLOCK_T_DEFINED
	typedef     long  clock_t;
	#define     _CLOCK_T_DEFINED
	#endif


由以上程式碼可得知，`clock_t` 為一個整數型別。

另外，在標頭檔中定義了一個常數 `CLOCKS_PER_SEC` 表示每秒會有幾次的 CPU 單位時間（tick）。因此可以使用 `clock() / CLOCKS_PER_SEC` 得到該程式目前執行的時間。

## Example

	#include <time.h>
	#include <stdio.h>

	int main() {
		clock_t begin, end;
		double timeCnt;
		
		begin = clock();
		/*
		ANYTING_YOU_WANT_TO_COUNT
		*/
		end = clock();
		timeCnt = (double)( end - begin ) / CLOCKS_PER_SEC;
		printf( "Time: %lf sec\n", timeCnt );
		
		return 0;
	}

上述範例，即可用來計算想要計時的程式片段所執行的時間長度。修改 `ANYTING_YOU_WANT_TO_COUNT` 部份為想要計時的程式碼。


