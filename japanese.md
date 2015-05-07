## PHP Coding Style Guide(PSR-1 + PSR-2) 日本語
- 複数メンバーがコードを読む際の認識のずれを抑えること
- これはPHPコードをどのような書式にするかについて、ルールや期待値を共有することで実現します。
- [韓国語](https://github.com/BoomLEE/document/blob/master/README.md)
- 後でexampleも追加します。

## PSR-1
- PHPコードは「<?php」及び 「<?=」タグを使用しなければならない。
- 文字コードはUTF-8を使用する。
- Namespaceとclassは必ずPSR-0とPSR-4の"autoloading"準拠しなければならない。
- classの名前は必ず Studlycapsにする。
- class定数 (区切りはアンダースコアですべて大文字)。
- Propertyは $Studlycaps, $camelCase, $under_score
   何でも大丈夫ですが $under_scoreに統一しましょう。
- メソッド名は必ずcamelCaseにする。


## PSR-2
- PSR-1準拠しなければならない。
- intentは四つのspaceを適用,tapは使いません。
- ラインの長さは80文字以内にしましょう。
- namespaceの宣言後には空間一つをいれてください。
- useの宣言後には空間一つをいれてください。
- Classの括弧({})は必ず次のラインに追加。
- Methodの括弧({})は必ず次のラインに追加。
- すべてのプロパティとメッサードは必ずvisibilityを宣言してください。
 - Visibility : public, private, protected
  - private : selected class
  - protected : selected class, subclass
  - public  : all
- abstractと finalは必ずvisibilityの前に宣言する。
- staticは必ずvisibilityの後ろに宣言する。

## メソッド名は動詞から始める
- これは有名ですね。「メソッドはそのオブジェクトに命令を下すもの」なので、
命令型が良いのです。なので動詞からすぐはじめる。
以下のリストでほとんどカバーできていると思います。

|動詞名|日本語表現|主な戻り値|
|:-----|:--------:|:---------:|
|Get|取得する|オブジェクト|
|Set|設定する|void|
|Update|更新する|void(updateした件数返す場合も)|
|Delete|削除する|void(deleteした件数返す場合も)|
|Insert|挿入する|void|
|Select|選択する|オブジェクト|
|Find|選択する|オブジェクト|
|Add|追加する|void|
|Remove|削除する|オブジェクト|
|Clear|クリアする|void|
|Append|追記する|void or 追加後のオブジェクト|
|Trim|整形する|オブジェクト|
|Compare|比較する|比較結果(-1,0,1)|
|Concat|結合する|オブジェクト|
|Split|分割する|オブジェクト|
|Enumerate|列挙する|配列|
|Move|移動する|void|
|Copy|コピーする|void|
|Create|作成する|オブジェクト|
|Make|作成する|オブジェクト|
|Generate|作成する|オブジェクト|
|New|生成する|オブジェクト|
|Build|組み立てる|オブジェクトもしくはvoidで引数に与えられた変数を組み立て|
|Flush|フラッシュする|void|
|Begin|始める|void|
|End|終わる|void|
|Initalize|初期化する|void|
|Load|ロードする|void|
|Merge|マージする|オブジェクト|
|Read|読む|オブジェクト|
|Write|書く|void|
|To|変換する|オブジェクト|
|Convert|変換する|オブジェクト|
|Accept|許容する|void|
|Fill|満たす|void|
|Apply|適用する|void|
|Show|表示する|void|
|Union|和集合を取得する|オブジェクト|
|Intersect|積集合を取得する|オブジェクト|
|Do|実行する|void|
|Run|実行する|void|
|Shutdown|シャットダウンする|void|
|Save|保存する|void|
|Cancel|キャンセルする|void|
|Refresh|リフレッシュする|void|
|Execute|実行する|bool(成功か失敗か)|
|Resolve|解決する|オブジェクト|
|Invoke|呼び出す|オブジェクト|
|Handle|ハンドルする|オブジェクト|
|Raise|呼び出す|void|
|Is|〜かどうか？|bool|
|Contains|含んでる？|bool|
|Exists|存在する?|bool|
|Verify|評価する|bool(voidでNGなら例外でもいいかも）|
|Validate|評価する|bool|
|Try|試みる|bool(voidでNGなら例外でもいいかも）|
|Has|持っている？|bool|
|Equals|比較する|bool|
|Can|できるか？|bool|

名が体を表さないのはNG。Getメソッドなのに、メソッド内でSetしちゃっているとか良くみかけるコードです。
[参考リンク](http://qiita.com/Koki-Shimizu/items/f3d3e824f98d182d4100?utm_source=Qiita%E3%83%8B%E3%83%A5%E3%83%BC%E3%82%B9&utm_campaign=7f74e3810a-Qiita_newsletter_155_05_06_2015&utm_medium=email&utm_term=0_e44feaa081-7f74e3810a-32988249#%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E5%90%8D%E3%81%AF%E5%8B%95%E8%A9%9E%E3%81%8B%E3%82%89%E5%A7%8B%E3%82%81%E3%82%8B)

# Link
- http://www.php-fig.org/psr/psr-1/
- http://www.php-fig.org/psr/psr-2/
