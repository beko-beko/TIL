<details>
  <summary>文</summary>
    -文は`;`で終わる
</details>

<details>
  <summary>式</summary>
  -変数や定数、それらを演算子で結合したものを式と呼ぶ
  ```x + 32;```
  では`x`、`32`、`x + 32`のいずれも式とみなす
  代入演算子を用いた式は代入式という
</details>

<details>
  <summary>式文</summary>
  -式の末尾に`;`がついて文という形になる
  -式の後ろに`;`を置いた文は式文という
</details>

<details>
  <summary>プログラム</summary>
    人が読めるもの　コンピュータが理解できるもの
   ソースプログラム　→　実行プログラム
  　　　　　　　 コンパイル
</details>
<details>
  <summary>コメント</summary>
  <details>
    <summary>伝統的コメント</summary>
      ```/*・・・*```
      -行の先頭や末尾でなくてもよい
      -複数行にまたがることができる
      -`*/`で閉め忘れると大変なことになる
  </details>
  <details>
  <summary>行末コメント</summary>
    ```//・・・```
    -//から行末までがコメント
    -開始は行の先頭でなくてもよい
  </details>
  <details>
    <summary>入れ子</summary>
    <details>
      <summary>可能な入れ子</summary>
      ```/*・・・//・・・*/
         //・・・/*・・・*/```
    </details>
    <summary>不可能な入れ子</summary>
      ```/*・・・/*・・・*/・・・*/```
  </details>
</details>
  <details>
  <summary>引数</summary>
  仮引数　　実引数
  printf("こんにちは");
  関数
</details>
<details>
  <summary>処理系</summary>
  <details>
    <summary>コンパイル方式</summary>
    ソースコードをコンピューターが直接理解・実行できる形式に翻訳する方式
  </details>
  <details>
    <summary>インタプリタ方式</summary>
    ソースコードをコンピューターがプログラムを一行ずつ解釈しながら実行する方式
  </details>
</details>
<details>
  <summary>書式</summary>
  -printf関数に与える最初の実引数は書式文字列という
  -%dは書式の指示で変換指定という
  -\n = ¥n = 改行文字
</details>

<details>
  <summary>変換指定</summary>
  ％０９．９ｆ
  　↓ ↓  ↓  ↓
   Ａ Ｂ C  D
  -A フラグ
    -0が指定されていると、数値の前に余白があるとき、０をつめて表示する
    -このフラグを省略すると空白がつめられる
    - -が指定されると左詰めになり、指定がないと右詰めになる
  -B 最小フィールド幅
    -最低限の表示文字数の指定。この指定が省略されたり、指定された値を超える数値を表示するときは、その数値を表示するのに必要な桁数で表示される
  -C 精度
    -表示する最小の桁数の指定。省略すると、整数の制度は１とされ、浮動小数点数の精度は6とされる
  -D 変換指定子
    -d・・・int型の整数を10進数で表示する指定
    -f・・・double型の浮動小数点数を10進数で表示する指定
</details>

<details>
  <summary>定数</summary>
  -変数だけでなく、プログラムに埋め込まれた定数にも型がある
  
  -整数定数
    5や37など。基本的にint型
　-浮動小数点定数
  　3.14や2.0など。基本的にdouble型
</details>

<details>
  <summary>変数</summary>
  <details>
    <summary>変数の宣言</summary>
    型　名前
    int  n
    intという型でnという名前の変数を宣言した
    -変数は定義された型の性質に則って作られる
    -表現できる範囲も型に依存する
  </details>
  
  <details>
    <summary>初期化</summary>
    -実数に入れる値がわかっている際、最初から設定すること
    ```int x = 57;```
    57のように宣言の際に設定する変数を初期化子という
  </details>
  <details>
    <summary>不定値</summary>
    変数の値を設定しないと、変数名を宣言したときに、とりあえず作られたその変数名のための場所に、昔そこにあったデータが残っていて、それが代入されてしまう
    ```printf("nの値は%dです。\n", n);```
    →出力結果
    　> nの値は7です。
      不定値（ゴミの値）
    初期化せず、宣言だけした変数に、まだ代入していない状態で別の変数にその変数を代      入しようとするとwarningが出るので避ける
  </details>
</details>

<details>
  <summary>型</summary>
  -暗黙の型変換
   -異なる型の変数同士で計算すると、勝手に一方の変数の型が格上げされ、同じ型同士の     計算になる 
   -より大きくて小数部を格納できる型に変換される

  -キャスト
    （型）式
    の形式で、式の型を（）の型に変更する
  
  <details>
    <summary>int型</summary>
    <details>
      <summary>整数型</summary>
    -小数点以下の数は扱えない
    -int型で確実に表現できる値は-32767から32767まで
      ```int x = 3.5;```
      とすると、xに代入される値は3になる
      ```int x = 3.5;
         int y = x + 5.7;
         とすると、yに代入される値は8になる
    </details>

  <details>
    <summary>double型</summary>
    -実数を浮動小数点数という形式で表す
    -double型はそのひとつ
    ```double x = 3.141592;
    printf("円周率は%fです。", x)```
    →　出力結果
    > 円周率は3.141592です。
    -double型では小数点以下6桁まで表示される（5.2は5.200000となる）
  </details>
  
  </details>
<details>
  <summary>関数</summary>
  -第一引数の1番目の変換指定(%dなど)に1番目の第二引数の整数を、第二引数の2番目の変換指定(%d)に2番目の第二変数の整数を自動的に代入する
  <details>
    <summary>printf関数</summary>
    ```int no = 5;
    printf(”%dに10を足した値は%dです。”, no, no + 10)```
  </details>

  <details>
    <summary>puts関数</summary>
    -実引数として与えられた文字の並びを出力した上で改行文字を出力する
    -puts(”・・・”)はprintf(”・・・\n”)とほぼ同じ働きをする
    -puts関数は書式設定や数値の出力は不可能
  </details>
  
  <details>
    <summary>scanf関数</summary>
    -キーボードからの読み込みを行う関数
    -ひとつの関数で複数入力させる場合は、値と値の間で改行・タブ・スペースのいずれかを使用する
    ```scanf("%d", &no);```
    第一引数で変換指定、第二引数で読み込む。noは変数名。変数名の前に&をつける
    ```scanf("%d%d", &n1, &n2);```
    n1が一つ目の%dに、n2は二つ目の%dに読み込みされる
  </details>
</details>

<details>
  <summary>演算子</summary>
  <details>
    <summary>単項算術演算子</summary>
    <details>
      <summary>単項+演算子</summary>
      - +a 　aの値
      -負の値を入力しても負の値のまま表示する
      - +をつけずにそのままの変数を実引数としても動作は同じ
    </details>

    <details>
    <summary>単項-演算子</summary>
    - -a 　aの符号を反転した値
    -負の整数を入力すると反転されるので、正の値が出力される
    </details>
    -!演算子
    -~演算子
  <details>
    
  -オペランドを１個のみ必要とするのが単項演算子
  -２個必要とするものは２項演算子
  -３個必要とするものは３項演算子
  -演算の優先度
    -数学と一緒で、式の中に（）があれば優先される
    -加減算より乗除算が優先される

  <details>
    <summary>代入演算子</summary>
    -正式名称は単純代入演算子
    - =のこと
  </details>

  <details>
    <summary>等価演算子</summary>
    どちらも等価演算子という
    <details>
      <summary>==演算子</summary>
      -==  で左右のオペランドの値が等しいか判定する
       等しければ  1  、そうでなければ  0  という値を生成する
    </details>

  <details>
    <summary>!=演算子</summary>
    -左右のオペランドが等しくないかどうか判定する
    </details>
<details>
  <summary>
</details>
  </details>

  -加算 +
  -減算 -
  -乗算 *
  -除算 / (10÷2) = (10/2)
  <details><summary>余り % （7÷3=2…1)（7 % 3 = 1）</summary>
    文字列として%を表示するには%%と入力する
    整数 % 10 は最下位桁が出力される
  </details>
  </details>
  <details>
    <summary>オペランド</summary>
    -演算の対象となる変数や定数
    - x + y のとき、xとyはオペランド、+は演算子という
    -左側のオペランドは第１オペランド/左オペランドという
    -右側のオペランドは第２オペランド/右オペランドという
  </details>
</details>
<details>
  <summary></summary>
</details>

<details>
  <summary>if文</summary>
  if ( 式 ) 文
  式を評価してその値が非0（ゼロでなければ）であれば文を実行する
  -制御式
    if文の条件判定のために（）内に置かれた式
  -else
    制御式を評価した値が0だった場合elseの文を実行する
    if  (  式  )  文
      　文1（値  =  非0）;
    else
      　文2（値  =  0）;
  -else if文
    -if文には、if(式)文、if(式)文 else文の2種類しかないが、入れ子にすることで分岐を増やすことが可能
    -else if文は、厳密にはelseの後の文に新たにif文が追加されている形式になる
    if文
    else if文  
    else文
    の形で、else ifは間に入れる
  -非ゼロの判定
    if (num)
       puts(”ゼロでない”);
  　else
       puts(”ゼロ”);
    制御式に定数を入れることもできるが、その場合絶対ゼロにはならない
</details>
