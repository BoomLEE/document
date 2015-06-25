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
- 下記のエラーが出た場合メモリーがないということですので
```
vagrant@vagrant-ubuntu-utopic-64:~$ php composer.phar create-project laravel/laravel project --prefer-dist
Installing laravel/laravel (v5.1.1)
  - Installing laravel/laravel (v5.1.1)
    Loading from cache

Created project in project
Loading composer repositories with package information
Installing dependencies (including require-dev)
Killed
```
Vagrantfileを下記のようにコメントアウトする
```
       config.vm.provider "virtualbox" do |vb|
  #    Display the VirtualBox GUI when booting the machine
  #    vb.gui = true
  
  #    Customize the amount of memory on the VM:
       vb.customize ["modifyvm", :id, "--memory", "1024"]
  #    vb.memory = "1024"
    end

config.vm.provider "virtualbox" do |vb|
vb.customize ["modifyvm", :id, "--memory", "1024"]
```

## composerを利用してlaravelのProjectを作成。
- php composer.phar create-project laravel/laravel your_project --prefer-dist

## Link(参考リンク)
- [composer公式](https://getcomposer.org/)
- [laravel公式](http://laravel.com/)
- [Qiita:Composerのインストール](http://qiita.com/u-akihiro/items/d77236631acc34715a20)
