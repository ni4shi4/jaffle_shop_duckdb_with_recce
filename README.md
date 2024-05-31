# `jaffle_shop` with Recce

初期設定はオリジナルの[README](https://github.com/dbt-labs/jaffle_shop_duckdb?tab=readme-ov-file#running-this-project)を参照

やり方の一部を抜粋すると以下のようになる(Python >= 3.5が必要となる)

```
git clone https://github.com/ni4shi4/jaffle_shop_duckdb_with_recce.git
cd jaffle_shop_duckdb_with_recce
python3 -m venv venv
source venv/bin/activate
python3 -m pip install --upgrade pip
python3 -m pip install -r requirements.txt
source venv/bin/activate
dbt build
dbt docs generate
dbt docs serve
```

# オリジナルの`jaffle_shop`との違い

- `dbt-core`のバージョン
- `Recce`パッケージ
- 追加のdbtパッケージ
- `PROD`環境の追加
- プロジェクトの構成([best practices](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview)に似せた)
- raw_payments.csvにresult列を追加

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
