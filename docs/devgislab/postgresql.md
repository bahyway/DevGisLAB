# PostgreSQL

### Question:

How to Connect to the Database in the Container after the Creation of Dev Container finished successfully?

<figure><img src="../.gitbook/assets/01-connect-to-postgresql-database-from-vscode.png" alt=""><figcaption><p>Create Connection to PostgreSQL Database</p></figcaption></figure>

Use `ifconfig` from the terminal on Docker container of the Dev Container to show the Container ip address, use this in the connection screen to PostgreSQL Database

<figure><img src="../.gitbook/assets/04-ifconfig-command-in-docker-container.png" alt=""><figcaption></figcaption></figure>

* Connection Name : PostgresCont01
* Server Type : PostgreSQL
* Host Ip4 : 172.18.0.2
* Password : postgres
* Username : postgres
* Databse name : postgres

<figure><img src="../.gitbook/assets/02-connection-parameters--to-postgresql-database-from-vscode.png" alt=""><figcaption><p>Connect to PostgreSQL Database</p></figcaption></figure>

Press on the **`+Connect`** Button , this will show if the connection succeed or not:

<figure><img src="../.gitbook/assets/03-connection-success--to-postgresql-database-from-vscode.png" alt=""><figcaption><p>Connection with PostgreSQL Succeed from VS Code</p></figcaption></figure>

Now you can work with PostgreSQL from VS Code ( the postgres database is now open in vs code ):

<figure><img src="../.gitbook/assets/05-vscode-connected-to-postgresql.png" alt=""><figcaption><p>Check the Postgres Database</p></figcaption></figure>

Create the First Query just for test:

```sql
SELECT * FROM pg_stat_activity;
```

<figure><img src="../.gitbook/assets/06-create-the-first-query-for-postgresql-database.png" alt=""><figcaption><p>Run first Query</p></figcaption></figure>

* You can also save the query results as **JSON**, **CSV** or **Excel**.
