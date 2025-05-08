## 愚かなるGitHubのHistoryの消し方
https://qiita.com/studio_meowtoon/items/9ba34ef567a089fb484e  
1. `git clone https://github.com/リポジトリ名`
2. `cd リポジトリ名`
3. `git checkout --orphan orphan_branch`
4. `git commit -am "Initial commit"`
5. `git branch -D main`
6. `git branch -m main`
7. `git push -f origin main`
