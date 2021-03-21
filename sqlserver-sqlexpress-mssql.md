# MS SQL DB

## Expose SQLEXPRESS using tcp

- Run C:\Windows\SysWOW64\SQLServerManager($version).msc
- Enable TCP/IP properties and set properties/IP Addresses/IPAll/port to 1433
- Restart the SQL Server (SQLEXPRESS) service

<http://support.webecs.com/kb/a868/how-do-i-configure-sql-server-express-to-allow-remote-tcp-ip-connections-on-port-1433.aspx>

**NOTE:** once this is done, ensure that there is a login user

## Use a docker image

<https://hub.docker.com/_/microsoft-mssql-server>

```console
$ docker pull mcr.microsoft.com/mssql/server

$ # password must be 8 letters long
$ docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=saP4ssw0rd!' -p 1433:1433 -it mcr.microsoft.com/mssql/server:2017-latest

$ docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=saP4ssw0rd!' -e 'MSSQL_PID=Express' -p 1433:1433 -it mcr.microsoft.com/mssql/server:2017-latest
```

connect using Azure Data Studio (note the server string)

```console
Server                  localhost, 1433
Authentication type     SQL Login
User Name               sa
Password                saP4ssw0rd!
```

## Links

<https://www.sqlservercentral.com/blogs/running-sql-server-with-docker-on-the-mac>
