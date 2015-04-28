## PHP Coding Style Guide(PSR-1 + PSR-2) 日本語
- 複数メンバーがコードを読む際の認識のずれを抑えること
- これはPHPコードをどのような書式にするかについて、ルールや期待値を共有することで実現します。
- [韓国語](https://github.com/BoomLEE/document/blob/master/README.md)

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

# Link
- http://www.php-fig.org/psr/psr-1/
- http://www.php-fig.org/psr/psr-2/
