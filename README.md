# Kazuaki Yamamoto Portfolio

山本和明のWebエンジニア向けポートフォリオサイトです。

実務経験、技術スタック、個人開発したWebアプリケーションをまとめています。

## 公開URL

[https://kazyuaki.github.io/portfolio/](https://kazyuaki.github.io/portfolio/)

## 制作目的

これまでの実務経験や個人開発で身につけた技術、開発に対する考え方を、
採用担当者やエンジニアの方へ分かりやすく伝えることを目的に制作しました。

デザインから実装、レスポンシブ対応、GitHub Pagesへの公開まで一貫して取り組んでいます。

## 掲載内容

- **Hero** — 自己紹介と主な技術スタック
- **About** — 経歴と開発で大切にしていること
- **Experience** — 教育系Webアプリケーションにおける実務経験
- **Skills** — 実務・個人開発で使用している技術
- **Projects** — 個人開発したTask Flowの紹介
- **Contact** — GitHubへのリンク

## 主な制作物

### Task Flow

日々のタスクを整理・管理できるWebアプリケーションです。

認証、タスクCRUD、カテゴリ管理、検索・絞り込み、プロフィール編集などを実装し、
Dockerによる開発環境の構築からVPSへのデプロイまで行いました。

- [公開アプリ](https://taskflow-app-kazu.com)
- [GitHubリポジトリ](https://github.com/kazyuaki/task-flow-app-by-vue)

## 使用技術

| 分類 | 技術 |
| --- | --- |
| Frontend | Vue 3, TypeScript, Vite |
| UI | CSS, Lucide Icons |
| Hosting | GitHub Pages |
| CI/CD | GitHub Actions |

## 主な特徴

- コンポーネント単位でセクションを分割
- 半透明やぼかしを取り入れたモダンなUI
- PC・タブレット・スマートフォンへのレスポンシブ対応
- キーボード操作や適切なHTML要素を意識した実装
- GitHub Actionsによる自動ビルド・デプロイ

## ローカルでの起動方法

```bash
git clone git@github.com:kazyuaki/portfolio.git
cd portfolio
npm install
npm run dev
```

本番用ビルドを確認する場合は、以下を実行します。

```bash
npm run build
npm run preview
```

## デプロイ

`main` ブランチへ変更が反映されると、GitHub Actionsが自動でビルドを実行し、
GitHub Pagesへデプロイします。

## 今後の予定

- フリマアプリの公開・掲載
- 勤怠管理アプリの公開・掲載
- Reactを使用した制作物の追加

## Author

**Kazuaki Yamamoto**

- [GitHub](https://github.com/kazyuaki)
