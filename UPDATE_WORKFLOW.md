# 就業規則・各規程の改正施行手順

## 適用範囲

- ファイル名が正規表現 `[0-9]{2}_.+(規則|規程)\.md` をパスするもの

## 改正施行手順

### 改正草案ブランチの用意

`master` ブランチは現行の就業規則・各規程が参照可能な状態を維持するため、 `develop` ブランチを改正草案ブランチとして取り扱います。

1. `master` ブランチに移動し最新の状態にします `git switch master; git pull origin master`
2. もし `develop` ブランチが存在しないのであればブランチを作成します `git switch -c develop`
3. もし `develop` ブランチが存在するのであれば最新のmasterに追従します `git switch develop; git merge master`

### 改正施行に向けての作業

検討事項ごとに作業ブランチを作成し、 `develop` ブランチへ反映します

1. 改正施行に向けての作業ブランチを作成します `git switch develop; git switch -c <任意のブランチ名>`
2. 作業ブランチ上で検討事項を就業規則・各規程に反映します
3. 差分をコミットします `git add <変更した就業規則・各規程>; git commit`
4. 作業ブランチをリモートにプッシュします `git push origin <作業ブランチ>`
5. 作業ブランチをもとに[プルリクエストを作成](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)します
    - ベースブランチを `develop` にします
6. [プルリクエストのレビュー](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)を受けます
7. レビューで承認を得たらプルリクエストの作成者が[プルリクエストをマージ](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)します

### 改正

改正草案を `master` へ反映します。

1. `develop` ブランチをもとに[プルリクエストを作成](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)します
    - ベースブランチを `master` にします
2. [プルリクエストのレビュー](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)を受けます
3. レビューで承認を得たらプルリクエストの作成者が[プルリクエストをマージ](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)します

### 改正日と施行日の設定

改正した就業規則・各規程の附則に改正日と施行日を記します。

1. `master` ブランチに移動し最新の状態にします `git switch master; git pull origin master`
2. 改正日と施行日を記すための作業ブランチを作成します `git switch -c <任意のブランチ名>`
3. 作業ブランチ上で改正した就業規則・各規程の附則に `この規則は、令和＿＿年＿＿月＿＿日に改正し、令和＿＿年＿＿月＿＿日から施行する。` という文言を追加します
    - 改正日は改正のプルリクエストをマージした日にします
    - 施行日は変更を周知するための期間を設けた日にします
4. 作業ブランチをもとに[プルリクエストを作成](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)します
    - ベースブランチを `develop` にします
5. [プルリクエストのレビュー](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)を受けます
6. レビューで承認を得たらプルリクエストの作成者が[プルリクエストをマージ](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)します

### リリースの作成

1. `master` ブランチに移動し最新の状態にします `git switch master; git pull origin master`
2. タグを作成します git tag -a `<施行日>` -m `<施行日>`
    - 施行日はISO 8601の基本形式 `YYYYMMDD` で表記します
3. タグをリモートにプッシュします `git push origin <作成したタグ>`
4. [リリースを作成](https://docs.github.com/ja/repositories/releasing-projects-on-github/managing-releases-in-a-repository#creating-a-release)します
