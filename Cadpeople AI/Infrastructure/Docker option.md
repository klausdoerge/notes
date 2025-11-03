
Der skal laves en samlet docker-fil som spinner de 4 services op

1) AnythingLLM
2) MSSQL
3) WebAPI
4) Frontend


`Anything LLM`
`$env:STORAGE_LOCATION="$HOME\Documents\anythingllm"; If(!(Test-Path $env:STORAGE_LOCATION)) {New-Item $env:STORAGE_LOCATION -ItemType Directory}; If(!(Test-Path "$env:STORAGE_LOCATION\.env")) {New-Item "$env:STORAGE_LOCATION\.env" -ItemType File}; docker run -d -p 3001:3001 --cap-add SYS_ADMIN -v "$env:STORAGE_LOCATION:/app/server/storage" -v "$env:STORAGE_LOCATION\.env:/app/server/.env" -e STORAGE_DIR="/app/server/storage" mintplexlabs/anythingllm;`


Run SQL Server
`docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=FedeBaller12! -p 1433:1433 -v sqlvolume:/var/opt/mssql -d mcr.microsoft.com/mssql/server:2019-latest`