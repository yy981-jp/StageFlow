# StageFlow
*	時間は基本相対的時間
*	ネストは深さ32まで許可
*	データ型はint,float,string,bool <mark>**(<-未実装)**</mark>
*	時間は、msやsをつけることでコンパイラがフレーム数に変換する
*	SpaceとTabは区別せず何個あっても連続していれば1つとみなす
*   インデントは任意

## コメントアウト
```
    // コメントアウト
    /*
        複数行のコメントアウト
    */
```

## ラベル

```
    :{ラベル名}
```
```
    :testLabel
```

## エンティティ配置
```
    spawn {エンティティ名} {パラメータ, ...}
```
```
    spawn enemyBezier x=100 y=50 pattern=spiral duration=2
```

## 待機
```
    wait {秒,ミリ秒}
```
```
    wait 1s // 1秒待機
    wait 50ms // 50ミリ秒待機
```

## 条件付き待機
* フラグの判定はtick毎に行う
```
    waitUntil {フラグ名}
```
```
    waitUntil bossDead
```

## ラベル呼び出し
```
    call {ラベル名}
```
```
    call testLabel
```

## 繰り返し
```
    repeat {繰り返し回数}
        // 何らかの処理
    end
```
```
	repeat 3
		spawn enemyBezier x=100 y=50 pattern=spiral duration=2
		wait 50ms
	end
```

## 条件付き繰り返し
* フラグがtrueの間は繰り返し続ける
* フラグの判定はループ毎に行う

```
    repeatUntil {フラグ名}
        // 何らかの処理
    end
```
```
	repeatUntil testFlag1
		wait 10s
	end
```