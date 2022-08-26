# Lucid BigInt problem

Issue https://github.com/adonisjs/lucid/issues/869

```ts
const entities = await Entity.query().where('id', entity.id)
```

Error:

```
[09:30:02.737] ERROR (lucid-bigint/3539): str.replace is not a function
    err: {
      "type": "TypeError",
      "message": "str.replace is not a function",
      "stack":
          TypeError: str.replace is not a function
              at escapeString (/home/filipebraida/lucid-bigint/node_modules/knex/lib/client.js:463:22)
              at escapeFn (/home/filipebraida/lucid-bigint/node_modules/knex/lib/util/string.js:50:12)
              at Client_SQLite3.finalEscape [as _escapeBinding] (/home/filipebraida/lucid-bigint/node_modules/knex/lib/util/string.js:18:12)
              at /home/filipebraida/lucid-bigint/node_modules/knex/lib/execution/internal/query-executioner.js:17:19
              at String.replace (<anonymous>)
              at formatQuery (/home/filipebraida/lucid-bigint/node_modules/knex/lib/execution/internal/query-executioner.js:9:14)
              at /home/filipebraida/lucid-bigint/node_modules/knex/lib/execution/internal/query-executioner.js:39:7
              at Runner.ensureConnection (/home/filipebraida/lucid-bigint/node_modules/knex/lib/execution/runner.js:300:14)
              at Runner.run (/home/filipebraida/lucid-bigint/node_modules/knex/lib/execution/runner.js:30:19)
              at QueryRunner.executeQuery (/home/filipebraida/lucid-bigint/node_modules/@adonisjs/lucid/build/src/QueryRunner/index.js:78:28)
      "status": 500
    }
```