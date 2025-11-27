# turbo-pnpm

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![ESLint](https://img.shields.io/badge/ESLint-9.39.1-4B32C3?logo=eslint&logoColor=white)](https://eslint.org/)
[![Jest](https://img.shields.io/badge/Jest-30.2.0-C21325?logo=jest&logoColor=white)](https://jestjs.io/)
[![NestJS](https://img.shields.io/badge/NestJS-11.1.9-E0234E?logo=nestjs&logoColor=white)](https://nestjs.com/)
[![Node.js](https://img.shields.io/badge/Node.js-24.11.1-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![pnpm](https://img.shields.io/badge/pnpm-10.24.0-F69220?logo=pnpm&logoColor=white)](https://pnpm.io/)
[![Prettier](https://img.shields.io/badge/Prettier-3.7.1-F7B93E?logo=prettier&logoColor=white)](https://prettier.io/)
[![Turborepo](https://img.shields.io/badge/Turborepo-2.6.1-EF4444?logo=turborepo&logoColor=white)](https://turbo.build/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.9.3-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)

Turborepo + pnpm を使用したモダンなモノレポのテンプレートリポジトリです。

## 特徴

- **Turborepo** - 高速なビルドシステムとキャッシング
- **pnpm Catalogs** - 依存関係のバージョンを一元管理
- **ESLint Flat Config** - 最新の ESLint 設定形式
- **共有設定パッケージ** - ESLint・TypeScript 設定を共通化
- **GitHub Actions CI** - 自動テスト・ビルド

## プロジェクト構成

```
turbo-pnpm/
├── apps/
│   └── server/             # NestJS サーバー
├── packages/
│   ├── eslint-config/      # 共有 ESLint 設定
│   └── typescript-config/  # 共有 TypeScript 設定
├── turbo.json              # Turborepo 設定
└── pnpm-workspace.yaml     # pnpm ワークスペース設定
```

## セットアップ

```bash
# リポジトリをクローン
git clone https://github.com/your-username/turbo-pnpm.git
cd turbo-pnpm

# 依存関係をインストール
pnpm install

# すべてのチェックを実行
pnpm check-all
```

## コマンド一覧

| コマンド             | 説明                            |
| -------------------- | ------------------------------- |
| `pnpm build`         | すべてのパッケージをビルド      |
| `pnpm start`         | 開発サーバーを起動              |
| `pnpm check-all`     | lint, format, tsc, test を実行  |
| `pnpm lint`          | ESLint を実行                   |
| `pnpm lint:fix`      | ESLint で自動修正               |
| `pnpm format`        | Prettier でフォーマットチェック |
| `pnpm format:fix`    | Prettier で自動フォーマット     |
| `pnpm tsc`           | TypeScript 型チェック           |
| `pnpm test`          | テストを実行                    |
| `pnpm test:coverage` | カバレッジ付きテスト            |
| `pnpm clean`         | ビルド成果物を削除              |

## 注意事項

### pnpm-workspace.yaml の YAML アンカー名

`pnpm-workspace.yaml` で YAML アンカーを使用する場合、アンカー名に `@` 記号を含めると Turborepo が正しく動作しません。

```yaml
# ❌ ダメ
versions:
  '@types/jest': &@types/jest 30.0.0

# ✅ OK
versions:
  '@types/jest': &types-jest 30.0.0
```

## ライセンス

[MIT](LICENSE)
