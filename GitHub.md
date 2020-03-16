
# GitHub 新規リポジトリ  

```
> git init  
> git status  
> git add -A  
> git status  
> git commit -m "first commit"

* GitHub でリポジトリを作成  
https://github.com/login  

> git remote add origin https://github.com/kn201905/SHA1.git  
> git push -u origin master  
```

---
# GitHub ssh接続  
* ssh key の生成  
> ssh-keygen -t rsa -C "temp2019@knmail.jpn.org" -f github  
> ssh-keygen -l -f github.pub（生成された鍵の確認）  

* 上記で -f でファイル名を指定している場合、\~/.ssh に config ファイルを作成する必要がある。  
（デフォルトでは、ssh接続の際「\~/.ssh/id_rsa」、「\~/.ssh/id_dsa」、「\~/.ssh/identity」しか見にいかないため）  
>  vi ~/.ssh/config  

Host github github.com  
　HostName github.com  
　IdentityFile ~/.ssh/github  
　User git  

* 以下の URL より、GitHub に公開鍵を登録  
https://github.com/settings/ssh  

* 接続の確認  
> ssh -T github  

* 「~/.ssh/config」で設定を行っている場合、remote に登録が必要となる  
> git remote set-url origin github:[ユーザ名]/[リポジトリ名]  
（例）git remote set-url origin github:kn201905/chatsvr_cpp.git  

* git push の確認  
> git push  

---
# Windows で複数のアカウントを利用する場合

* 新規フォルダにおいて、git clone を行うとき、以下のようにする

```
git clone https://github.com/user_a/aprojectX
 ↓
git clone https://user_a@github.com/user_a/aprojectX
```

