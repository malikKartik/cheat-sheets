## Setting up postgres in docker for development

- Install docker
- pull image


```docker pull postgres:alpine (or with any other tag)```
- creating and running a container with exposed port


```docker run --name postgres-container-name -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres:alpine```

**OR if you need to persist you data in docker volume**

```docker run --name postgres-container-name -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 -v /Users/UserName/data/pg:/var/lib/postgresql/data postgres:alpine```

in this command above **/Users/UserName/data/pg** is some directory in your local machine and you can change it but **/var/lib/postgresql/data** is a path inside the docker conatiner and is fixed.


This will map the port 5432 of container to the port 5432 of the Local machine

Note - If you stop a container or maybe shutdown your local machine use command ```docker start postgres-container-name``` to restart the container

- Opening container with bash in interactive mode 

```docker exec -it postgres-container-name bash```

- Running postgresql in bash

```psql -U postgres```

### postgres commands

- List all users               - ```\du```
- List all databases           - ```\l```
- Connect to a database        - ```\c database-name```
- List realation               - ```\d```

### NodeJS application to connect to Postgrsql

**Installing dependencies**

```
npm i pg yargs
```

**Code**
```
const { Pool, Client } = require("pg");
const yargs = require('yargs/yargs')
const { hideBin } = require('yargs/helpers')
const argv = yargs(hideBin(process.argv)).argv

const credentials = {
    user: "postgres",
    host: "localhost",
    database: "test",
    password: "password",
    port: 5432,
  };

  async function runSqlQuery(query) {
      const client = new Client(credentials);
      await client.connect();
      const result = await client.query(query);
      await client.end();
      return result;
  }

(async () => {
    const result = await runSqlQuery(argv.query);
    console.log(result)
})();
```

**Using it**
```
node index.js --query="SELECT NOW()"
```
