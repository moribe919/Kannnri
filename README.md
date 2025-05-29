# # 在庫管理システム (Inventory Management System)

iPhone最適化された在庫・使用量管理システムです。介護施設や個人での消耗品管理に特化して設計されています。

## 🌟 特徴

- **📱 iPhone最適化**: タッチ操作に特化したUI/UX
- **👥 複数利用者対応**: 最大60名まで管理可能
- **📊 詳細統計**: 月別分析・使用傾向の可視化
- **🔄 リアルタイム更新**: 在庫変動の即座反映
- **⚠️ アラート機能**: 在庫僅少時の自動通知
- **💾 データ永続化**: ブラウザ内でのデータ保存

## 🚀 クイックスタート

### 必要要件
- Node.js 16.0.0以上
- npm または yarn

### インストール

```bash
# リポジトリのクローン
git clone https://github.com/yourusername/inventory-management.git
cd inventory-management

# 依存関係のインストール
npm install

# 開発サーバーの起動
npm start
```

ブラウザで `http://localhost:3000` を開いてアプリケーションにアクセスできます。

## 📦 プロジェクト構成

```
inventory-management/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── components/
│   │   └── InventoryManager.js
│   ├── App.js
│   ├── index.js
│   └── index.css
├── package.json
├── tailwind.config.js
├── postcss.config.js
├── README.md
└── .gitignore
```

## 🎯 主要機能

### 在庫管理
- ✅ 商品の追加・削除・編集
- ✅ 在庫数量の調整（増減操作）
- ✅ 使用量の記録と履歴管理
- ✅ 仕入れ情報の登録（数量・金額）
- ✅ 最小在庫数設定とアラート

### 利用者管理
- ✅ 利用者の追加・削除・名前変更
- ✅ 利用者別在庫の個別管理
- ✅ 利用者間でのデータ分離

### 統計・分析
- ✅ 月別使用量・仕入れ量の分析
- ✅ 利用者別統計の表示
- ✅ 前月比トレンド分析
- ✅ コスト分析（単価計算など）

## 📱 iPhone最適化

- **タッチフレンドリー**: 48px以上のタップ領域
- **レスポンシブ**: 縦画面・横画面対応
- **直感的操作**: スワイプ・タップジェスチャー対応
- **高速表示**: 軽量設計による快適な動作

## 🛠️ 技術スタック

- **フロントエンド**: React 18, Tailwind CSS
- **アイコン**: Lucide React
- **状態管理**: React Hooks (useState, useEffect)
- **データ永続化**: ブラウザのlocalStorage
- **ビルドツール**: Create React App

## 💡 使用方法

### 1. 利用者の登録
1. 「👥 利用者」タブをクリック
2. 利用者名を入力して「追加」ボタンをタップ
3. 必要に応じて利用者名を編集

### 2. 在庫の追加
1. 「📦 在庫管理」タブで利用者を選択
2. 商品名、初期数量、最小在庫数を入力
3. 「追加」ボタンで在庫を登録

### 3. 日常的な操作
- **使用時**: 青い「使用」ボタンの「+」をタップ
- **在庫補充**: 灰色の「在庫調整」ボタンで調整
- **仕入れ記録**: 数量と金額を入力してトラックアイコンをタップ

### 4. 統計の確認
- **📊 統計**: 利用者別の詳細統計
- **📅 月別**: 月別の使用傾向とコスト分析

## 🔧 カスタマイズ

### 商品タイプの追加
`src/components/InventoryManager.js`の`DIAPER_TYPES`配列を編集：

```javascript
const DIAPER_TYPES = [
  ‘Mテープ’, ‘Lテープ’, ‘LLテープ’,
  ‘Mパンツ’, ‘Lパンツ’,
  ‘尿取りパッド小’, ‘尿取りパッド大’,
  ‘おしりふき’, ‘防水シーツ’,
  ‘新しい商品タイプ’, // ← 追加
  ‘その他’
];
```

### 最大利用者数の変更
```javascript
const MAX_RESIDENTS = 60; // ← この数値を変更
```

## 📋 データ形式

アプリケーションは以下のデータ構造を使用します：

```javascript
{
  residents: [
    {
      id: “1”,
      name: “利用者1”
    }
  ],
  items: [
    {
      id: “1”,
      residentId: “1”,
      name: “商品名”,
      quantity: 10,
      used: 5,
      min: 3,
      source: “購入”,
      purchases: [
        {
          date: “2025-01-15”,
          qty: 20,
          price: 1500
        }
      ],
      usageHistory: [
        {
          date: “2025-01-16”,
          qty: 2
        }
      ]
    }
  ]
}
```

## 🚀 デプロイ

### Vercel
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm run build
# buildフォルダをNetlifyにドラッグ&ドロップ
```

### GitHub Pages
```bash
npm install —save-dev gh-pages

# package.jsonに追加:
“homepage”: “https://yourusername.github.io/inventory-management”,
“scripts”: {
  “predeploy”: “npm run build”,
  “deploy”: “gh-pages -d build”
}

npm run deploy
```

## 🤝 コントリビューション

1. このリポジトリをフォーク
2. 機能ブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m ‘Add some amazing feature’`)
4. ブランチにプッシュ (`git push origin feature/amazing-feature`)
5. プルリクエストを作成

## 📄 ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細は[LICENSE](LICENSE)ファイルを参照してください。

## 🙏 謝辞

- [Lucide](https://lucide.dev/) - 美しいアイコンセット
- [Tailwind CSS](https://tailwindcss.com/) - ユーティリティファーストCSSフレームワーク
- [React](https://reactjs.org/) - ユーザーインターフェース構築ライブラリ

## 📞 サポート

問題や質問がある場合は、[Issues](https://github.com/yourusername/inventory-management/issues)で報告してください。

—

**iPhone Safari で最適な体験をお楽しみください！** 📱✨

## 📸 スクリーンショット

### 在庫管理画面
在庫の追加、使用記録、仕入れ管理を一つの画面で操作できます。

### 利用者管理画面  
複数の利用者を効率的に管理し、それぞれの在庫状況を把握できます。

### 統計画面
月別の使用傾向やコスト分析により、効率的な在庫管理をサポートします。

### 月別分析画面
詳細な月別データと前月比較により、使用パターンを可視化します。