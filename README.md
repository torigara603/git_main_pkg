# git main pkg

git+python の練習用のメインパッケージ  
サブモージュルをお試しする  

- リファレンス
  - https://git-scm.com/book/ja/v2/Git-%E3%81%AE%E3%81%95%E3%81%BE%E3%81%96%E3%81%BE%E3%81%AA%E3%83%84%E3%83%BC%E3%83%AB-%E3%82%B5%E3%83%96%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB
  - https://shunsvineyard.info/2019/12/23/using-git-submodule-and-develop-mode-to-manage-python-projects/#1-what-is-development-mode

## 追加

```bash
git submodule add REPO_URL # include clone
```

## 変更

```bash
cd sub_repo
git add ./
git commit 
git push
cd ../
git add ./sub_repo
git commit -m "[Update] update submodules. sub_repo"
git push
```

## 変更の取り入れ

```bash
cd sub_repo
git pull
cd ../
git add ./sub_repo
git commit -m "[Update] update submodules. sub_repo"
git push
```

## poetry 関連

### 開発モード

poetryに開発モードで行いたい場合(pip -e)がやりたい場合 pyproject.toml に developオプションを加えて`poetry update`を行う

```toml
git-sub-pkg = {path="path", develop=true}
```

