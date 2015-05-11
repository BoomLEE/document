# Windows上でVirtualBox+Vagrant+Ubuntuによる仮想環境構築 
- windowsでのvagrantインストール
- 環境構築
- Ubuntuの起動・接続・停止

## windowsでのvagrantインストール
1.VirtualBoxのインストール
https://www.virtualbox.org/wiki/Downloads

2.Vagrantのインストール
https://www.vagrantup.com/downloads.html

3.UbuntuのVirtualBoxへの登録
```
C:\Users\psinc> vagrant box add Ubuntu14.04 https://cloud-images.ubuntu.com/vagrant/utopic/current/utopic-server-cloudimg-amd64-vagrant-disk1.box
※最新のboxファイルURLは http://www.vagrantbox.es を参照
```

## 環境構築
4. Vagrant初期設定
```
C:\Users\psinc> mkdir rc_abroad_dev
C:\Users\psinc> cd rc_abroad_dev
C:\Users\psinc\rc_abroad_dev> vagrant init Ubuntu14.04
```

## Ubuntuの起動・接続・停止
1.Ubuntuの起動
```
C:\Users\psinc\rc_abroad_dev> vagrant up
```

2.Ubuntuへの接続
```
C:\Users\psinc\rc_abroad_dev> vagrant ssh

実行したらエラー！ssh loginできるソフトでログインしましょう。
`ssh` executable not found in any directories in the %PATH% variable. Is an
SSH client installed? Try installing Cygwin, MinGW or Git, all of which
contain an SSH client. Or use your favorite SSH client with the following
authentication information shown below:

Host: 127.0.0.1
Port: 2222
Username: vagrant
Private key: C:/Users/psinc/rc_abroad_dev/.vagrant/machines/default/virtualbox/private_key
```

3.ssh loginできるソフト(RLoginなど)
C:\Users\psinc\rc_abroad_dev>フォルダーにある「Vagrantfile」を修正。
```
config.vm.network "private_network", ip: "192.168.33.10"
//コメントアウトを外す。
```

4.サーバー停止
```
//vagrantコマンドで停止する
C:\Users\psinc\rc_abroad_dev> vagrant halt 
```

## サーバーにgitのインストール(Ubuntu)
```
vagrant@vagrant-ubuntu-utopic-64:~$ sudo apt-get install git
vagrant@vagrant-ubuntu-utopic-64:~$ git --version
その他はこっちらを確認してください。
http://git-scm.com/download 
```





参考：
========================================
http://qiita.com/hiroyasu55/items/11a4c996b0c62450940f

