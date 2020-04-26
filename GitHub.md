
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
# git clone でアカウントを設定する場合

* 新規フォルダにおいて、git clone を行うとき、以下のようにする

```
git clone https://github.com/user_a/aprojectX
 ↓
git clone https://user_a@github.com/user_a/aprojectX
```

---
# GitHub ssh接続  
* ssh key の生成  
> ssh-keygen -t rsa -b 4096 -C "test@test.com" -f github  

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
# git config
```
# git config --list
# git config --list --show-origin

# git config --local user.name "John Doe"
# git config --local user.email johndoe@example.com

認証情報のキャッシュ
# git config --local credential.helper 'cache --timeout=86400'
```
