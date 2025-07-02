```c
#include <stdio.h>

int main(void)
{
	int len;

	puts("左上直角二等辺三角形を表示します。");
	printf("短辺：");
	fflush(0);
	scanf("%d", &len);

	for (int i = len; i >= 1; i--) { // i行（i = 1, 2, … , len)
		for (int j = 1; j <= i; j++) { // 各行にi個の'*'を表示
			printf("*");
		}
		putchar('\n'); // 改行
	}

	return 0;
}

i <= len
3     3  i--
2     3
```

<details>
<summary>演習4-23-1</summary>

```c
/*
 * 左上、右上が直角の二等辺三角形を表示
 * （List4-20を書き換える）
 *
 */

#include <stdio.h>
int main(void)
{
    int len;

    puts("左上直角の二等辺三角形を作ります。");
    printf("短編：");
    fflush(0);  scanf("%d", &len);
    putchar('\n');

    for ( int i = len; i >= 1; i-- ){	//list4-20と異なる箇所
        for( int j = 1; j <= i; j++){
            putchar('*');
        }
        putchar('\n');
    }

    //別解
    printf("----------\n");
    for ( int i = 1; i <= len; i++ ){
    	for( int j = 1; j <= len - i + 1; j++){		//list4-20と異なる箇所
    		putchar('*');
    	}
    	putchar('\n');
    }

    return 0;
}
/* 実行結果 */

//左上直角の二等辺三角形を作ります。
//短編：5
//
//*****
//****
//***
//**
//*
//----------
//*****
//****
//***
//**
//*
```

</details>

<details>
<summary>演習4-23-2</summary>

```c
/*
 * 左上、右上が直角の二等辺三角形を表示
 * （List4-21を書き換える）
 *
 */
#include <stdio.h>
int main(void)
{
    int len;

    puts("左上、右上が直角の二等辺三角形を作ります。");
    printf("短編：");
    fflush(0);  scanf("%d", &len);
    putchar('\n');


    for( int i = len; i >= 1; i--){		//list4-21と異なる箇所
        for ( int  j = 1; j <= len - i; j++){
            putchar('~');
        }
        for ( int j = 1; j <= i; j++ ){
            putchar('*');
        }
        putchar('\n');
    }


    //別解
    printf("----------\n");
    for (int i = 1; i <= len; i++) {
    	for ( int  j = 1; j <= i - 1; j++){		//list4-21と異なる箇所
    		putchar('~');
    	}
    	for ( int j = 1; j <= len - i + 1; j++ ){	//list4-21と異なる箇所
    		putchar('*');
    	}
    	putchar('\n');
    }

    return 0;
}
/* 実行結果 */

//左上、右上が直角の二等辺三角形を作ります。
//短編：5
//
//*****
// ****
//  ***
//   **
//    *
//----------
//*****
//~****
//~~***
//~~~**
//~~~~*
```

</details>

<details>
<summary>演習4-24</summary>

```c
/*
 * 読み込んだ整数の段数を持つピラミッド表示する
 *
 */

#include <stdio.h>
int main(void)
{
    int height;

    puts("ピラミッドを作ります");
    printf("何段ですか：");
    fflush(0);  scanf("%d", &height);

/* 	ピラミッドを作成する
 *  '*'の数を求める式 ：(i - 1) * 2 + 1
 *  空白の個数を求める式： height - i
 *  */

    for( int i = 1; i <= height; i++){
        for( int j = 1; j <= height - i; j++){
            putchar('.');
        }
        for( int j = 1; j <= (i - 1) * 2 + 1; j++){
            putchar('*');
        }
        putchar('\n');
    }

    /*/////  この問題もやってみよう /////*/
    /*
     *  逆向きピラミッドを作成する
     */

    printf("----------\n");

    for( int i = 1; i <= height; i++){
        for( int j = 1; j < i; j++){
            putchar('.');
        }
        for( int j = 1; j <= (height - i) * 2 + 1; j++){
            putchar('*');
        }
        putchar('\n');
    }


    return 0;
}
// 実行結果
//ピラミッドを作ります
//何段ですか：4
//...*
//..***
//.*****
//*******
//----------
//*******
//.*****
//..***
//...*
```

</details>

<details>
<summary>演習4-25</summary>

```c
/*
 * 読み込んだ整数の段数を持つピラミッド表示する
 *
 */

#include <stdio.h>
int main(void)
{
    int height;

    puts("下向き数字ピラミッド"
            "を作ります");
    printf("何段ですか：");
    fflush(0);  scanf("%d",&height);

    /* ピラミッドを作成する
     * 数字の個数を求める式 ：(height - i) * 2 + 1
     * 空白の個数を求める式 ：i - 1
     */
    for( int i = 1; i <= height; i++){
        for( int j = 1; j <= i - 1; j++){
            putchar('.');
        }
        for( int j = 1; j <= (height - i) * 2 + 1; j++){
            printf("%d", i % 10);
        }
        putchar('\n');
    }

    return 0;
}
// 実行結果
//何段ですか：4
//1111111
//.22222
//..333
//...4

//下向き数字ピラミッドを作ります
//何段ですか：12
//11111111111111111111111
//.222222222222222222222
//..3333333333333333333
//...44444444444444444
//....555555555555555
//.....6666666666666
//......77777777777
//.......888888888
//........9999999
//.........00000
//..........111
//...........2
//
```

</details>
