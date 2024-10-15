= github rest api を用いてコミットする
= 自動草生成コマンド

```
  curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/contents/PATH
```
のshaを取得
```
curl -L \
  -X PUT \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/contents/PATH \
  -d '{"message":"my commit message","committer":{"name":"Monalisa Octocat","email":"octocat@github.com"},"content":"bXkgbmV3IGZpbGUgY29udGVudHM=" "sha":"<YOUR SHA>"}'
```
でコミット

== python
```
pip install -r requirements.txt
```
envファイルを追加
```
TOKEN = ghp_-
OWNER = owner_name
REPO = your_repogitory_path
PATHs = your_filepath
```
```
python commit.py
```