# spec-development

既存のプロジェクトで、機能ごとの仕様を継続して更新しながら開発するための日本語のGitHub Copilot用Skillです。仕様と受入条件を決め、変更範囲と検証方法を計画してから実装します。導入に必要なファイルはすべてMarkdownです。

## 既存リポジトリで使う

1. [`.github/skills/spec-development/`](./.github/skills/spec-development/) を、対象リポジトリの同じパスへフォルダごとコピーします。
2. [Copilot用の指示](./.github/copilot-instructions.md)を対象の `.github/copilot-instructions.md` に追記します。`AGENTS.md` を使う場合は、[その参照例](./AGENTS.md)も既存の指示に追記します。
3. VS Codeで対象リポジトリを開き、Copilot Chatの新しいチャットで以下のように依頼します。Skillを指定して試す場合は `/spec-development` に続けて依頼を書きます。

> 受注CSVの末尾に「部署名」を追加したい。検索条件と閲覧権限は現行どおり。まず仕様の差分と計画まで見せてください。

例えば `docs/spec/orders/csv-export/spec.md` があるなら、そこに「部署名を末尾に出力する」「閲覧権限外の受注はCSVに含まれない」という受入条件を反映し、変更箇所とテスト方法まで示します。部署名が未設定の場合の表記を資料から判断できなければ確認します。実装まで依頼する場合は、同じ仕様を基準に実装・検証を進めます。

## 仕様と計画の管理

機能の現行仕様は原則 `docs/spec/<業務>/<機能>/spec.md` に置きます。小改修も同じ仕様を更新し、差分はGitやPRで確認できます。普段の計画はチャットやPRに短く残し、引き継ぎに必要なときだけ同じフォルダに `plan.md` を置きます。既存の文書配置や開発規約があるプロジェクトでは、そちらを優先します。

[Spec Kitの既存プロジェクト向けガイド](https://github.github.io/spec-kit/guides/existing-projects.html)と[Living Specの運用](https://github.github.io/spec-kit/guides/evolving-specs.html)を参考に、手順を[一つのSkill](./.github/skills/spec-development/SKILL.md)にまとめました。Spec KitのCLI、Python、追加のスクリプトは不要です。
