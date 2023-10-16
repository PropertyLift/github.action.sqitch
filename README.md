# Sqitch migrations

This custom GitHub Action

## Workflow steps

Action designed to use prebuilded Docker image `sqitch/sqitch`  to run migrations

## Future improvements

TBD

## How to use guide

### Basic setup

```yml
env:
  DB_HOST:
  DB_PORT:
  DB_USER:
  DB_PASS:
  DB_NAME:

jobs:
.
.
.
  migration:
    steps:
      - name: Run migrations
        uses: propertylift/github.action.sqitch@main
        with:
          command: "deploy"
          target: "db:pg://${{ env.DB_USER }}:${{ env.DB_PASS }}@${{ env.DB_HOST }}:${{ env.DB_PORT }}/${{ env.DB_NAME}}"
```

## Inputs

| Parameter Name | Required | Default | Description                                  |
| -------------- | -------- | ------- | -------------------------------------------- |
| command        | Yes      | -       | The command which will be passed to sqitch   |
| target         | Yes      | -       | Database URI on Sqitch should run migrations |
