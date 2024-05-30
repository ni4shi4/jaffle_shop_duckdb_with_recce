# `jaffle_shop` with Recce

設定等はオリジナルの[README](https://github.com/dbt-labs/jaffle_shop_duckdb?tab=readme-ov-file#testing-dbt-project-jaffle_shop)を参照

# オリジナルの`jaffle_shop`との違い

- `dbt-core`のバージョン
- `Recce`パッケージ
- 追加のdbtパッケージ
- `PROD`環境の追加
- プロジェクトの構成([best practices](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview)に似せた)

# `Recce`の使い方

- 依存パッケージをインストールする
  ```
  dbt deps
  ```
- `PROD`環境向けにdbtを実行する
  ```
  dbt build -t prod
  dbt docs generate -t prod --target-path target-base
  ```
- `DEV`環境向けにdbtを実行する
  ```
  git switch feature/add_intermediate
  dbt build
  dbt docs generate
  ```
- Recceサーバーを起動する
  ```
  recce server
  ```

# レビューモードでの`Recce`の起動

```
git switch feature/add_intermediate
recce server --review recce-state-example.json
```

# `Recce summary`の使用

```
git switch feature/add_intermediate
recce summary recce-state-example.json
```
