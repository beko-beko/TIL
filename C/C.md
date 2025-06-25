<details>
  <summary>文</summary>
  
- 文は`;`で終わる

<details>
<summary>選択文</summary>

- プログラムの流れを選択的に分岐させる
- if文とswitch文がある

<details>
  <summary>if文</summary>
  
  if ( 式 ) 文
  式を評価してその値が非0（ゼロでなければ）であれば文を実行する<br>
  
  - 制御式
    if文の条件判定のために（）内に置かれた式<br>
    後ろに`;`を置かないこと
  - else
    制御式を評価した値が0だった場合elseの文を実行する
    ```c
    if　(　式　)　文
    　　文1（値  =  非0）;
    else
      　文2（値  =  0）;
    ```
  - else if文
    - if文には、if(式)文、if(式)文 else文の2種類しかないが、入れ子にすることで分岐を増やすことが可能
    - else if文は、厳密にはelseの後の文に新たにif文が追加されている形式になる
    if文
    else if文  
    else文
    の形で、else ifは間に入れる
  - 非ゼロの判定
```c
if (num)
　puts(”ゼロでない”);
else
　puts(”ゼロ”);
```
　制御式に定数を入れることもできるが、その場合絶対ゼロにはならない
- 0はTrueかFalseか
　```c
　int a = 0;

	if (a = 0){
		puts("aは0です");
	} else {
		puts("aは0ではありません");
	}
　```
1.aにゼロを代入する<br>
2.もし、<br>
3.式でaにゼロを代入する<br>
4-1.if文は値を評価して非ゼロだった場合最初の文、「aは0です」と表示する<br>
4-2.値を評価してゼロだった場合else文、「aは0ではありません」と表示する<br>
<br>
ifの式で0を代入しているので値はゼロになる。そのため必ずelse文の「aは0ではありません」と表示される<br>
<br>
```c
int a = 0;

	if (a == 0){
		puts("aは0です");
	} else {
		puts("aは0ではありません");
	}
```
1. aにゼロを代入する<br>
2.もし、<br>
3.式でaと0が等しいか評価している<br>
4-1.if文は値を評価して非ゼロだった場合最初の文、「aは0です」と表示する<br>
4-2.値を評価してゼロだった場合else文、「aは0ではありません」と表示する<br>
<br>
「もしaと0が等しければif文の最初の文を返すプログラムなので、aは0です」と表示される<br>

</details>

</details>

<details>
<summary>switch文</summary>

switch ( 制御式 ) 文<br><br>

```c
switch ( 制御式 ) {
　case 0 :　・・・;　break;
　case 1 :　・・・;　break;
　case 2 :  ・・・;　break;
}
```
- 単一の式に基づいて、複数の分岐をする場合、簡潔に表現できる
- if文よりswitch文の方が読み間違えや書き間違いと誤解されることが減る
- 制御式を評価した値に基づいて結果に対応するラベルのプログラムに飛ぶ
- ()に囲まれた制御式は整数でなければいけない
- ラベル<br>
　`case 1 :`という形式で書かれる<br>
　ラベルの値は定数でなければいけない
　複数のラベルが同じ値を持つことはできない
　同じ処理をしたいcaseを上下に並べ、上のcaseを空白にして、break文もおかないことで、同じ処理をさせることができる
  「case」と「1」の間の空白は省略不可

<details>
<summary>break文</summary>

- ラベルの後の文が実行された後、`break;`とつけることで、switch文を中断させる
- break文がないと、次のcaseが続けて実行される
- 最後のcaseの末尾にもbreak文を置くことで、ラベルの増減に対応できる

</details>

- default<br>
制御式を評価した値がどのcaseにも一致しない際に飛ぶラベル

</details>

</details>

<details>
<summary>複合文（ブロック）</summary>

- `{}`を使う文
- {0個以上の文または宣言の並び}
- 文は何個でもよく、宣言も何個でもよい
- 文の一種で、構造上は単一の文とみなされる
- if文、elseは1つの文しか制御できない。<br>複数の文を制御するには複合文を使う

</details>


    
</details>

<details>
  <summary>式</summary>
  
- 変数や定数、それらを演算子で結合したものを式と呼ぶ<br>
```x + 32;```<br>
では`x`、`32`、`x + 32`のいずれも式とみなす<br>
代入演算子を用いた式は代入式という
- 式を評価する=答えが出る<br>
定数は評価されるとそのままの数が出てくる<br>
Trueは1、Falseは0と出る
  
</details>

<details>
  <summary>式文</summary>
  
- 式の末尾に`;`がついて文という形になる
- 式の後ろに`;`を置いた文は式文という
  
</details>

<details>
  <summary>プログラム</summary>
  
　人が読めるもの　コンピュータが理解できるもの<br>
　ソースプログラム　→　実行プログラム<br>
　　　　　　　 コンパイル
          
</details>

<details>
  <summary>コメント</summary>
  
<details>    
  <summary>伝統的コメント</summary>
    
　```/*・・・*/```
- 行の先頭や末尾でなくてもよい
- 複数行にまたがることができる
- `*/`で閉め忘れると大変なことになる
      
</details>
  
<details>
<summary>行末コメント</summary>
    
　```//・・・```
- //から行末までがコメント
- 開始は行の先頭でなくてもよい
    
</details>
  
<details>
  <summary>入れ子</summary>
    
<details>
  <summary>可能な入れ子</summary>
      
　```/*・・・//・・・*/```
　```//・・・/*・・・*/```
         
</details>

<details>
  <summary>不可能な入れ子</summary>
    
　```/*・・・/*・・・*/・・・*/```
      
</details>
</details>
</details>

<details>
  <summary>引数</summary>
    
　仮引数　　実引数<br>
　printf("こんにちは");<br>
　関数
  
</details>

<details>
  <summary>処理系</summary>
  
<details>
  <summary>コンパイル方式</summary>
    
- ソースコードをコンピューターが直接理解・実行できる形式に翻訳する方式
    
</details>
  
<details>
  <summary>インタプリタ方式</summary>
    
- ソースコードをコンピューターがプログラムを一行ずつ解釈しながら実行する方式
    
</details>
  
</details>

<details>
  <summary>書式</summary>
  
  - printf関数に与える最初の実引数は書式文字列という
  - %dは書式の指示で変換指定という
  - \n = ¥n = 改行文字
  
</details>

<details>
  <summary>変換指定</summary>
  
　％０９．９ｆ<br>
　　&nbsp;↓&nbsp;&nbsp;↓&nbsp;&nbsp;&nbsp;↓&nbsp;&nbsp;&nbsp;&nbsp;↓<br>
　　Ａ&nbsp;Ｂ&nbsp;C&nbsp;&nbsp;&nbsp;D<br>
  - A　フラグ
    - 0が指定されていると、数値の前に余白があるとき、０をつめて表示する
    - このフラグを省略すると空白がつめられる
    - -が指定されると左詰めになり、指定がないと右詰めになる
  - B　最小フィールド幅
    - 最低限の表示文字数の指定<br>
    この指定が省略されたり、指定された値を超える数値を表示するときは、その数値を表示するのに必要な桁数で表示される
  - C 精度
    - 表示する最小の桁数の指定<br>
    省略すると、整数の制度は１とされ、浮動小数点数の精度は6とされる
  - D 変換指定子
    - d・・・int型の整数を10進数で表示する指定
    - f・・・double型の浮動小数点数を10進数で表示する指定
    
</details>

<details>
  <summary>定数</summary>
  
- 変数だけでなく、プログラムに埋め込まれた定数にも型がある
- 整数定数<br>
  5や37など。基本的にint型
- 浮動小数点定数<br>
  3.14や2.0など。基本的にdouble型
   
</details>

<details>
  <summary>変数</summary>
  
<details>
  <summary>変数の宣言</summary>
    
　型&nbsp;&nbsp;&nbsp;名前<br>
　int&nbsp;&nbsp;&nbsp;　n<br>
　intという型でnという名前の変数を宣言した<br>
- 変数は定義された型の性質に則って作られる
- 表現できる範囲も型に依存する
    
</details>
  
<details>
  <summary>初期化</summary>
    
- 実数に入れる値がわかっている際、最初から設定すること<br>
```c
int x = 57;
```
57のように宣言の際に設定する変数を初期化子という
    
</details>
  
<details>
  <summary>不定値</summary>
    
- 変数の値を設定しないと、変数名を宣言したときに、とりあえず作られたその変数名のための場所に、昔そこにあったデータが残っていて、それが代入されてしまう<br>
```c
printf("nの値は%dです。\n", n);
```
→出力結果<br>
> nの値は7です。<br>

　不定値（ゴミの値）<br>
　初期化せず、宣言だけした変数に、まだ代入していない状態で別の変数にその変数を代入しようとするとwarningが出るので避ける
  
</details>
  
</details>

<details>
  <summary>型</summary>
  
- 暗黙の型変換
- 異なる型の変数同士で計算すると、勝手に一方の変数の型が格上げされ、同じ型同士の計算になる 
- より大きくて小数部を格納できる型に変換される

- キャスト<br>
　（型）式<br>
　の形式で、式の型を（）の型に変更する
  
<details>
  <summary>int型</summary>
    
- 整数型      
- 小数点以下の数は扱えない
- int型で確実に表現できる値は-32767から32767まで<br>
```c
int x = 3.5;
```

　とすると、xに代入される値は3になる
```c
int x = 3.5; int y = x + 5.7;
```
　とすると、yに代入される値は8になる
         
</details>

<details>
  <summary>double型</summary>
    
- 実数を浮動小数点数という形式で表す
- double型はそのひとつ
```c
double x = 3.141592;
printf("円周率は%fです。", x)
```
　→　出力結果
> 円周率は3.141592です。

- double型では小数点以下6桁まで表示される（5.2は5.200000となる）
    
</details>
  
</details>
  
<details>
  <summary>関数</summary>
  
- 第一引数の1番目の変換指定(%dなど)に1番目の第二引数の整数を、第二引数の2番目の変換指定(%d)に2番目の第二変数の整数を自動的に代入する
  
<details>
<summary>printf関数</summary>
    
```c
int no = 5;
printf(”%dに10を足した値は%dです。”, no, no + 10);
```
    
</details>

<details>
　<summary>puts関数</summary>
    
- 実引数として与えられた文字の並びを出力した上で改行文字を出力する
- puts(”・・・”)はprintf(”・・・\n”)とほぼ同じ働きをする
- puts関数は書式設定や数値の出力は不可能
    
</details>
  
<details>
　 <summary>scanf関数</summary>
    
- キーボードからの読み込みを行う関数
- ひとつの関数で複数入力させる場合は、値と値の間で改行・タブ・スペースのいずれかを使用する
```c
scanf("%d", &no);
```
　第一引数で変換指定、第二引数で読み込む<br>
　noは変数名。変数名の前に&をつける
```c
scanf("%d%d", &n1, &n2);
```
　n1が一つ目の%dに、n2は二つ目の%dに読み込みされる
    
</details>
  
</details>

<details>
<summary>演算子</summary>
<details>
<summary>単項算術演算子</summary>  
<details>
<summary>単項+演算子</summary>
  
- +a aの値<br>
- 負の値を入力しても負の値のまま表示する<br>
- +をつけずにそのままの変数を実引数としても動作は同じ
 
</details>

<details>
<summary>単項-演算子</summary>
  
- -a<br>
aの符号を反転した値<br>
- 負の整数を入力すると反転されるので、正の値が出力される
    
</details>
    
- !演算子
- ~演算子
    
- オペランドを１個のみ必要とするのが単項演算子
- ２個必要とするものは２項演算子
- ３個必要とするものは３項演算子
- 演算の優先度
- 数学と一緒で、式の中に（）があれば優先される
- 加減算より乗除算が優先される

</details>

<details>
  <summary>代入演算子</summary>
    
- 正式名称は単純代入演算子
- =のこと
    
</details>

<details>
  <summary>等価演算子</summary>
    
　どちらも等価演算子という
    
<details>
<summary>==演算子</summary>

- `==` で左右のオペランドの値が等しいか判定する
- 等しければ 1、そうでなければ 0 という値を生成する
- `=`は代入になるので使用しないこと

</details>

<details>
  <summary>!=演算子</summary>
    
- 左右のオペランドが等しくないかどうか判定する
    
</details>

</details>

<details>
<summary>加減演算子</summary>

- 加算 +
- 減算 -

</details>

<details>
<summary>乗除演算子</summary>

- 乗算 *
- 除算 / (10÷2) = (10/2)
  
<details>
  <summary>余り % （7÷3=2…1)（7 % 3 = 1）</summary>
    
　文字列として%を表示するには%%と入力する
　整数 % 10 は最下位桁が出力される
    
</details>
</details>

<details>
<summary>関係演算子</summary>

- 二つのオペランドの大小関係を判定する演算子

<details>
<summary><演算子</summary>

　左が右よりも小さければ１，そうでなければ０（int型）

</details>

<details>
<summary>>演算子</summary>

　左が右より大きければ１，そうでなければ０（int型）
</details>

<details>
<summary><=演算子</summary>

　左が右以下であれば１，そうでなければ０（int型）
 
</details>

<details>
<summary>>=演算子</summary>

　左が右以上であれば１，そうでなければ０（int型）
</details>

- <=演算子と>=演算子は逆向きにできない
- 差を出すときは&&や||を使うこと<br>
　```c
　if (3 <= a <= 5)　//誤：3つのオペランドは扱えない
　if (a >= 3 && a <= 5)　//正
　```

</details>

</details>

<details>
<summary>条件演算子</summary>

　式1 ? 式2 : 式3<br>
1.　式1を評価。式1が非0であれば式2を評価した値となる<br>
2.　0であれば式3を評価した値となる<br>
- 唯一の3項演算子

```c
int max = n1 > n2 ? n1 :n2;
printf("大きいほうの値は%dです。\n", max);
```
　二つのプログラムは同じ結果が出力される
</details>

<details>
<summary>論理演算子</summary>

- 三つの変数が等しいかどうかを求めるときは
  `if ( a == b && b == c )`とする<br>
　`if ( a == b && c )`だと<br>
　aとbが等しいとき、True(1)になるので、1とcがFalseになる

- 短絡評価<br>
　&&演算子は、aを評価した値が0であればbの評価を行わない<br>
　||演算子も、aを評価した値が非0であればbの評価を行わない<br>

<details>
<summary>論理 AND 演算子</summary>

- `a && b`<br>
　a かつ b<br>
 
　論理積
| a | b | a && b|
----|----|---|
| 非0 | 非0 | ***1*** |
| 非0 | 0 | 0 |
| 0 | 非0 | 0 |
| 0 | 0 | 0 |
　両方ともTrue（非0）であれば 1<br>
 <br>

</details>

<details>
<summary>論理 OR 演算子</summary>

- `||`のこと
- `a || b`<br>
　a または b (a と bも含む）<br><br>
 
 　論理和
  | a | b | A || b |
  ----|----|----|
  | 非0 | 非0 | ***1*** |
  | 非0 | 0 | ***1*** |
  | 0 | 非0 | ***1*** |
  | 0 | 0 | 0|
　一方でもTrue（非0）であれば 1

</details>
</details>

<details>
<summary>様々な演算子の評価</summary>

```c
int n = 51;

	printf("n > 0 : %d\n", n > 0);
	// n > 0 : 1
	// 「n > 0 : (10進数で)(第1オペランドの方が第2オペランドより大きい場合は"1"、そうでなければ"０"を表示する)」

	printf("n == 0 : %d\n", n == 0);
	// n == 0 : 0
	// 「n == 0 : (10進数で)(第1オペランドと第2オペランドが等しければ"1"を、そうでなければ"0"を表示する)」

	printf("n / 2 = %d\n", n / 2);
	// n / 2 = 25

	printf("n / 2.0 = %.1f\n", n / 2.0);
	// n / 2.0 = 25.5

	printf("n %% 2 = %d\n", n % 2);
	// n % 2 = 1

	printf("n - 2 = %d\n", n - 2);
	// n - 2 = 49

	printf("(int)5.7 : %d\n", (int)5.7);
	// (int)5.7 : 5

	printf("(double)5 : %.1f\n", (double)5);
	// (double)5 : 5.0
```
</details>
</details>
  
<details>
  <summary>オペランド</summary>
    
- 演算の対象となる変数や定数
- x + y のとき、xとyはオペランド、+は演算子という
- 左側のオペランドは第１オペランド/左オペランドという
- 右側のオペランドは第２オペランド/右オペランドという
    
</details>
  
</details>


