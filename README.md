# CQC Vietnam Weekly — 公開サイト（GitHub Pages）

Capital Quest Corporation, Ltd. 投資調査部「ベトナムウィークリー（Sales版）」の公開用フォルダ。
このフォルダ＝公開リポジトリ `cqc-vn-weekly` の中身。

## 構成

```
web/  (= リポジトリ cqc-vn-weekly)
├── index.html            ← 号一覧（最新号＋バックナンバー）
├── assets/               ← ランディング用ロゴ
├── 2026-05-22/           ← 各号（自己完結：html＋assets＋vn_photos同梱）
│   ├── index.html        ← Sales版レポート
│   ├── assets/
│   └── vn_photos/
└── 2026-05-15/ …
```

- 公開URL（push後）: `https://yumiba924-a11y.github.io/cqc-vn-weekly/`
- 各号: `https://yumiba924-a11y.github.io/cqc-vn-weekly/2026-05-22/`

## 🔒 公開リポに入れてはいけないもの（重要）

このリポジトリは**公開（public）**。以下は絶対にコミットしない：
- ❌ 運用チーム版（`VNI_Internal_Dashboard_*.html`）— VietSeicho等ファンド情報
- ❌ 社内限り写真（高市会談 `photo04.avif` 等）
- ❌ LSEG 元データ（`*.xlsx`）
- ✅ 入れてよいのは Sales版HTML・街並み写真・ロゴのみ

## 初回セットアップ（1回だけ）

```bash
cd "C:\Users\Shogo.Yumiba\Desktop\ベトナムウィークリー\web"
git init
git add .
git commit -m "Initial: Vietnam Weekly public site (5/15, 5/22)"
gh repo create cqc-vn-weekly --public --source=. --remote=origin --push
# ↑ gh CLI がなければ GitHub で空リポ作成 → git remote add origin <URL> → git push -u origin main
```
GitHub → リポジトリ Settings → Pages → Source: `main` / `(root)` → Save。数分で公開。

## 毎週の更新

1. 新しい号フォルダを作成（例 `2026-05-29/`）— Sales版html＋assets＋vn_photosを入れる
2. `index.html` に最新号と新しいバックナンバー行を追加
3. コミット＆プッシュ：
   ```bash
   git add .
   git commit -m "Add 2026-05-29 issue"
   git push
   ```
4. 数十秒で `…/2026-05-29/` が公開 → メールにURLを貼る

## メモ
- 個人アカウント運用。最低限 **2FA有効化／復旧用メール設定／ローカルクローン保持** を推奨
- 将来 Organization へ移す場合は GitHub のリポジトリ移管機能で丸ごと移動可能
- 独自ドメイン（例 `weekly.capital-qc.co.jp`）は Pages 設定の Custom domain で後付け可能
