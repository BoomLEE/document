## composerとlaravelのインストール

- curl -sS https://getcomposer.org/installer | sudo php
- php composer.phar /* 動作を確認する。 */
- vi composer.json /* 必要なpackageを作成 */

```
{
  "name":"your_project",
  "homepage":"your_project.net"
  "require":{
   "laravel/installer=~1.1"
  }
}
```

- php composer.phar global require "laravel/installer=~1.1"

## composerを利用してlaravelのProjectを作成。
- php composer.phar create-project laravel/laravel your_project --prefer-dist

## Link(参考リンク)
- [composer公式](https://getcomposer.org/)
- [laravel公式](http://laravel.com/)
- [Qiita:Composerのインストール](http://qiita.com/u-akihiro/items/d77236631acc34715a20)
