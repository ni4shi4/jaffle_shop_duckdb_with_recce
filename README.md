# `jaffle_shop` with Recee

See the original [README](https://github.com/dbt-labs/jaffle_shop_duckdb?tab=readme-ov-file#testing-dbt-project-jaffle_shop) for startup

# Main Differences with the original `jaffle_shop`

- `dbt-core` version
- `Recce` package
- Add the environment `PROD`
- project structure (following to the [best practices](https://docs.getdbt.com/best-practices/how-we-structure/1-guide-overview))

# How to use `Recee`

```
dbt build -t prod
dbt docs generate -t prod --target-path target-base
```

```
git switch
dbt build -t qa
dbt docs generate -t qa
```

```
recce server
```



```
Error: Compilation Error in sql_operation generated_750ccfefb64c4d92a3ef905e4a236b77 (from remote system.sql) 'audit_helper' is undefined. This can happen when calling a macro that does not exist. Check for typos and/or install package dependencies with "dbt deps".
```
dbt_profiler
