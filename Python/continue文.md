# continue文とは
繰り返し処理の中で、その後の処理をスキップして次のループに以降するもの　

```Python
while True:
    num = int(input("1-10の数字を入力してください: "))

    if num not in range(1, 11):
        print("1-10以外の数字は入力しないでください：")
        continue
    
    print("入力した数字は" + str(num) + "です")
    break
```

1から10の数字を入力してほしいのに、それ以外の数字を入力された場合に、そのループは中断して次のループがはじまる
