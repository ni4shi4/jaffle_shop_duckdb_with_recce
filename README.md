# `jaffle_shop` with Recee

設定等はオリジナルの[README](https://github.com/dbt-labs/jaffle_shop_duckdb?tab=readme-ov-file#testing-dbt-project-jaffle_shop)を参照

# オリジナルの`jaffle_shop`との違い

- `dbt-core`のバージョン
- `Recce`パッケージ
- 追加のdbtパッケージ
- `PROD`環境の追加
- プロジェクトの構成([best practices](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview)に似せた)

# `Recee`の使い方

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

# レビューモードでの`Recee`の起動

```
git switch feature/add_intermediate
recce server --review recce-state-example.json
```
