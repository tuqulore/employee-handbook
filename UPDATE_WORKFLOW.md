# 就業規則・各規程の改正施行手順

## 適用範囲

- ファイル名が正規表現 `[0-9]{2}_.+(規則|規程)\.md` をパスするもの

## 改正施行手順

### 改正施行に向けての作業

検討事項ごとに作業ブランチを作成し、`main` ブランチへ反映します

1. 改正施行に向けての作業ブランチを作成します `git switch main; git switch -c <任意のブランチ名>`
2. 作業ブランチ上で検討事項を就業規則・各規程に反映します
3. 差分をコミットします `git add <変更した就業規則・各規程>; git commit`
4. 作業ブランチをリモートにプッシュします `git push origin <作業ブランチ>`
5. 作業ブランチをもとに[プルリクエストを作成](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)します
    - ベースブランチを `main` にします
6. [プルリクエストのレビュー](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)を受けます
7. レビューで承認を得たらプルリクエストの作成者が[プルリクエストをマージ](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)します

### 改正日と施行日の設定

就業規則・各規程の附則に改正日と施行日を記します。

1. `main` ブランチに移動し最新の状態にします `git switch main; git pull origin main`
2. 改正日と施行日を記すための作業ブランチを作成します `git switch -c <任意のブランチ名>`
3. 作業ブランチ上で変更のある就業規則・各規程の附則に `この規則は、令和＿＿年＿＿月＿＿日に改正し、令和＿＿年＿＿月＿＿日から施行する。` という文言を追加します
    - 改正日は改正の3\.を実施した日にします
    - 施行日は変更を周知するための期間を設けた日にします
    - 前回の改正施行からどの就業規則・各規程を変更したのかは `https://github.com/tuqulore/employee-handbook/compare/develop...<前回のリリース>` で確認してください
4. 作業ブランチをもとに[プルリクエストを作成](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)します
    - ベースブランチを `main` にします
5. [プルリクエストのレビュー](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)を受けます
6. レビューで承認を得たらプルリクエストの作成者が[プルリクエストをマージ](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)します

### 社員の過半数代表者の選出および意見の聴取

社員の過半数代表者の選出および意見の聴取をおこないます（その手順については本文書では取り扱いません）。意見の反映が必要である場合、改正施行に向けての作業から再度おこないます。

### リリースの作成

1. `main` ブランチに移動し最新の状態にします `git switch main; git pull origin main`
2. タグを作成します git tag -a `<施行日>` -m `<施行日>`
    - 施行日はISO 8601の基本形式 `YYYYMMDD` で表記します
3. タグをリモートにプッシュします `git push origin <作成したタグ>`
4. [リリースを作成](https://docs.github.com/ja/repositories/releasing-projects-on-github/managing-releases-in-a-repository#creating-a-release)します
