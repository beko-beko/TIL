<details>
<summary>演習4-9</summary>
	
```c
#include <stdio.h>

int main(void)
{
	int no;

	printf("正の整数：");
	fflush(0);  scanf("%d", &no); //noに入力された数字を入れる

	/* 0以下の場合何も表示しない */
	if( no > 0){ //noが0以下になるまで実行する
	}

		int i = 1; //カウントしていく値の1カウント目を1にする

		while ( i <= no ) //カウントが入力された数と同じになるまで行う
		{
			if( i % 2 )		//27行目でなく、ここで i++ してもよい。奇数ならi÷2の余りが1になるので真になる。偶数なら0になるので偽となる
				putchar('+'); //真（奇数）なら+が出力
			else
				putchar('-'); //偽（偶数）なら-が出力

			i++; //出力後、iに1を足す
		}
		putchar('\a');
		putchar('\n');
	}
```

別パターン
```c
#include <stdio.h>

int main(void)
{
	int no;

	printf("正の整数：");
	fflush(0);
	scanf("%d", &no);

	while ( no-- > 0){
		// putchar('+');
		putchar('-');
		if ( no-- > 0){
		//	putchar('-');
			putchar('+');
		}
	}
	putchar('\n');

	return 0;
}
```

</details>

<details>
<summary>演習4-10</summary>
	
```c
#include <stdio.h>
int main(void){
    int no;  	//入力用

    printf("正の整数：");
    fflush(0);  scanf("%d", &no);

    // '*'を表示して改行
    while( no-- > 0 ){	// 0以下の値は条件不成立
        putchar('*');	// となるため、実行しない
        putchar('\n');
    }

    return 0;
}
```

別パターン
```c
#include <stdio.h>

int main(void)
{
	int no;

	printf("正の整数："); fflush(0); scanf("%d", &no);

	while (no-- > 0){
		printf("*\n");

	}

	return 0;
}

 * 読み込んだ整数値の個数だけ * を縦に連続して表示する。
 * なお、0 以下の整数が入力されたときは何も表示しない。
```

</details>

<details>
<summary>演習4-11</summary>
	
```c
#include <stdio.h>

int main(void)
{
	int no;

	do {
		printf("正の整数を入力せよ：");
		fflush(0);
		scanf("%d", &no);
		if (no <= 0)
			puts("\a正でない数を入力しないでください。");
	} while (no <= 0);

	// noは0より大きくなっている
	printf("%dを逆から読むと", no);
	while (no > 0) {
		printf("%d", no % 10); //最下位の桁の値を表示
		no /= 10; // 右に１桁ずらす

	}
	puts("です。");
	// printf("です。\n);

	return 0;
}
```

</details>

<details>
<summary>演習4-12</summary>
	
```c
#include <stdio.h>

int main(void)
{
	int no;
	int noo;
	int cnt = 0;

	printf("正の整数を入力せよ：");
	fflush(0);
	scanf("%d", &no);

	noo = no;

	while (noo > 0){

		cnt += 1;
		noo /= 10;
	}

	printf("%dは%d桁です。", no, cnt);

	return 0;
}
```

</details>

<details>
<summary>リスト4-12</summary>
	
```c
// 読み込んだ正の整数値までカウントアップ（for文）

#include<stdio.h>

int main(void)
{

	int no;

	printf("正の整数を入力せよ：");
	fflush(0);
	scanf("%d", &no);

	for (int i = 0; i <= no; i++)
		printf("%d", i);
	putchar('\n'); // 改行

	return 0;
}
```

</details>

<details>
<summary>リスト44-13</summary>
	
```c
// 読み込んだ整数の個数だけ*を連続表示（for文）

#include <stdio.h>

int main(void)
{
	int no;

	printf("正の整数：");
	fflush(0);
	scanf("%d", &no);

	for (int i = 0; i < no; i++)
		putchar('*');
	putchar('\n');

	return 0;
}
```

</details>

<details>
<summary>リスト4-14</summary>
	
```c
// 指示された個数だけ整数を読み込んで合計値と平均値を表示

#include <stdio.h>

int main(void)
{
	int num;

	printf("整数は何個：");
	fflush(0);
	scanf("%d", &num);                            // num = 入力された整数の個数

	int sum = 0;                                  // 合計値
	for (int i = 1; i <= num; i++){               // 変数iに初期値1を設定。numがi以上のときループを行う。iに1を足す
		int tmp;
		printf("No.%d：", i);	                   // 変数iに1ずつ足して「No.1」という表記を作成
		fflush(0);
		scanf("%d", &tmp);                        // 変数tmpに入力された数値を代入
		sum += tmp;                                // 変数sumに入力された数値を足し合わせる
	}

	printf("合計値：%d\n", sum);                  // 全ての入力された数値を足し合わせたもの
	printf("平均値：%.2f\n", (double)sum / num); // double型にした合計値÷個数で平均値が出る

	return 0;
}
```
</details>

<details>
<summary>演習4-13</summary>
	
```c

#include <stdio.h>

int main(void)
{
	int n;

	printf("nの値：");
	fflush(0);
	scanf("%d", &n);

	int sum = 0;

	// for (int i = 0; i <= n; i++) {
	for (int i = 1; i <= n; i++) {
		sum += i;
	}

	printf("1から%dまでの総和は%dです。", n, sum);

	return 0;

}
```

</details>

<details>
<summary>演習4-14</summary>
	
```c
#include <stdio.h>

int main(void)
{
	int no;

	printf("正の整数を入力せよ：");
	fflush(0);
	scanf("%d", &no);

	for (int i = 1; i <= no; i++) {
		printf("%d", i % 10);
	}
}
```

</details>

<details>
<summary>演習4-15</summary>
	
```c
#include <stdio.h>

int main(void)
{
	int low;
	int high;
	int aida;

	printf("何cmから：");
	fflush(0);
	scanf("%d", &low);

	printf("何cmまで：");
	fflush(0);
	scanf("%d", &high);

	printf("何cmごと：");
	fflush(0);
	scanf("%d", &aida);

	if (aida <= 0)
		puts("増分が正しくありません。");

	else{
		for (int i = low; i <= high; i += aida){

			printf("%dcm　%.2fkg\n", i, (i - 100) * 0.9);
		}

		if (high % aida != 0){
			printf("%dcm　%.2fkg\n",high ,(high - 100) * 0.9);
		}
	}
}
```

</details>

<details>
<summary>リスト4-15</summary>
	
```c
// 指示された個数だけ整数を読み込んで合計値と平均値を表示（中断あり）

#include <stdio.h>

int main(void)
{
	int num;

	printf("整数は何個：");
	fflush(0);
	scanf("%d", &num);
	printf("終了は-9999\n");

	int i;
	int sum = 0; //合計値
	for (i = 0; i < num; i++){
		int tmp;
		printf("No.%d：", i + 1);
		fflush(0);
		scanf("%d", &tmp);
		if (tmp == -9999) break;
		sum += tmp;
	}

	printf("合計値：%d\n", sum);
	printf("平均値：%.2f\n", (double)sum / i);

	return 0;
}
```

</details>

<details>
<summary>リスト4-16</summary>
	
```c
//読み込んだ整数値以下の偶数を表示

#include <stdio.h>

int main(void)
{
	int n;

	printf("整数値：");
	fflush(0);
	scanf("%d", &n);                 // 入力された数値をnに代入

	for (int i = 2; i <= n; i += 2)  // 変数iの初期値を2に。iがn以下のときループ。iに2を足してループ
		printf("%d ", i);			  // 2スタートで2ずつ足しているので偶数のみ表示される
	putchar('\n');

	return 0;
}
```

</details>

<details>
<summary>リスト4-17</summary>
	
```c
// 読み込んだ整数値の全約数を表示

#include <stdio.h>
int main(void)
{
	int n;

	printf("整数値：");
	fflush(0);
	scanf("%d", &n);				// 変数nに入力された数値を代入

	for (int i = 1; i <= n; i++)	// 変数iの初期値に1を設定。iがn以下までループ。i+1してループ。
		if (n % i == 0)				// nの約数 = n÷iが0
			printf("%d ", i);
	putchar('\n');

	return 0;
}
```

</details>

<details>
<summary>演習4-16</summary>
	
```c
#include <stdio.h>

int main(void)
{
	int n;

	printf("整数値：");
	fflush(0);
	scanf("%d", &n);

	for (int i = 1; i <= n; i+=2)
		printf("%d ", i);
	printf("\n");

	return 0;
}
```

</details>

<details>
<summary>演習4-17</summary>
	
```c
#include <stdio.h>

int main(void)
{
	int n;

	printf("nの値：");
	fflush(0);
	scanf("%d", &n);

	for (int i = 1; i <= n; i++)
		printf("%dの２乗は%d\n", i, i * i);
	printf("\n");

	return 0;
}
```

</details>

<details>
<summary>演習4-18></summary>
	
```c
#include <stdio.h>

int main(void)
{
	int n;

	printf("何個*を表示しますか：");
	fflush(0);
	scanf("%d", &n);

	for (int i = 1; i <= n; i++)
		if (i % 5 == 0)
			printf("*\n");
		else
			printf("*");

	return 0;
}
```

</details>
