# datastack

docker compose setups for local database development.

## services

| service | image | port |
|---|---|---|
| mysql 9.7 | `mysql:9.7` | 3306 |
| sql server 2022 | `mcr.microsoft.com/mssql/server:2022-CU25-ubuntu-22.04` | 1433 |

## usage

```sh
# copy env files and set your passwords
cp mysql/.env.example mysql/.env
cp sqlserver/.env.example sqlserver/.env

# start a database
docker compose -f mysql/compose.yml up -d
docker compose -f sqlserver/compose.yml up -d

# check status
docker ps
```

## connecting

**mysql**
```sh
mysql -h 127.0.0.1 -P 3306 -u appuser -p
```

**sql server**
```sh
sqlcmd -S 127.0.0.1,1433 -U sa -P "your_password" -C
```

## license

MIT License, see [LICENSE](LICENSE).
