
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
```
https://help.github.com/ja/github/authenticating-to-github/connecting-to-github-with-ssh
```

* メールアドレスをラベルとして SSH キーを作成する
```
$ ssh-keygen -t rsa -b 4096 -C "test@test.com" -f github  
```

* ssh-agent をバックグラウンドで起動する
```
$ eval $(ssh-agent -s)
```

* SSH 秘密鍵を ssh-agent に追加する
```
$ ssh-add ~/.ssh/id_rsa
```

* クリップボードに SSH公開鍵をコピーする
```
$ clip < ~/.ssh/id_rsa.pub
```

* GitHub の HP で、Setting を表示し、左側のメニューの「SSH and GPG keys」をクリック
```
https://github.com/settings/profile
```

* 「New SSH key」をクリック  
　Title は適宜設定し、Key に公開鍵をペーストする  
　「Add SSH key」をクリックして、SSH 公開鍵の登録を終了

* 接続の確認
```
$ ssh -T git@github.com
```

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
