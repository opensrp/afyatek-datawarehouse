# Afya-tek Database Migrations

These database migrations can be used to set up the data warehouse for Afya-tek.

Changes to this data warehouse should be added to this sqitch project as new migrations.

## How to deploy these migrations

### Important Note

These migrations include a postgres variable named `db_user` which is used to set the owner for tables, functions and views created using the migrations.

For testing, the default value of `db_user` is set to "sqitch" but this must be set to the correct value when deploying to production.  The correct value is most likely `dtreedev` which is what is being used in production currently.

You would include this in the sqitch deploy command, like so:

```sh
sqitch deploy --set db_user=dtreedev
```

However, deployments should be codified using [ansible sqitch migrations](https://github.com/onaio/ansible-sqitch-migrations) to avoid the need for running the above command manually.