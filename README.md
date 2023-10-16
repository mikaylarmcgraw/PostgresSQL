# PostgreSQL

## Troubleshooting

### Port in use

If you are running into an error of port 5432 in use please do the following:

This will list what is currently running on port 5432 which could often be postgres already

`sudo lsof -i :5432`

This command will kill a PostgreSQL processL

`sudo pkill -u postgres`
