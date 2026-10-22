# Opvelのブログ — 閉鎖のお知らせ

`opvel.com` の運営終了を案内する、GitHub Pages用の静的ページです。
記事やバックアップは含めません。

## ファイル

- `index.html`：トップページ。
- `404.html`：古い記事URLなど、存在しないパスへの案内。HTTPステータスは404になります。
- `.nojekyll`：Jekyllによる変換を行わず、ファイルをそのまま配信します。

HTMLにはCSSを内包しているため、深い階層の旧URLでも表示が崩れません。
JavaScript・外部フォント・外部ライブラリは使用していません。
ページを更新するときは `index.html` と `404.html` の内容を揃えてください。

## GitHub Pagesでの公開

1. GitHubで公開リポジトリ `opvel-closed` を作り、このフォルダのファイルを `main` ブランチのルートにアップロードします。
2. リポジトリの **Settings → Pages → Build and deployment** で **Deploy from a branch**、`main`、`/ (root)` を選びます。
3. デプロイ完了後、`https://opvelll.github.io/opvel-closed/` で表示を確認します。
4. 存在しないパス（例：`https://opvelll.github.io/opvel-closed/old-post/`）でも閉鎖のお知らせが表示されることを確認します。

## opvel.comへの切り替え

1. GitHubアカウントの **Settings → Pages** でドメイン所有権を検証します。
2. リポジトリの **Settings → Pages → Custom domain** に `opvel.com` を設定します。ブランチからの公開では、GitHubが `CNAME` ファイルを追加します。追加後はローカルにも取り込みます。
3. その後にRoute 53のWeb用DNSレコードをGitHub Pages向けに変更します。値は下記の公式手順で確認してください。メール用のMX・TXTなどは維持します。
4. GitHub Pagesで **Enforce HTTPS** を有効にし、トップと古い記事URLをHTTPSで確認します。利用していた場合は `www.opvel.com` も確認します。
5. バックアップがローカルと非公開GitHubリポジトリで読めることを確認したうえで、不要なLightsailリソースを削除します。

DNS切り替えとLightsailの削除は、ページファイルの作成だけでは実行されません。

## 公式ドキュメント

- [GitHub Pagesの公開元設定](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [カスタム404ページ](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-custom-404-page-for-your-github-pages-site)
- [独自ドメインの設定](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [ドメイン所有権の検証](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)
