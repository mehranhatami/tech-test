# Scale

- First step to scale the application would be to setup a load-balancer for the API which hosts the shortened urls to the public(`trav.ix`)
- If the technology stack is based on a NOSQL database link MongoDB we could scale the database with [MongoDB Shards](https://www.mongodb.com/mongodb-scale)
- In case of using a relational database like MS SQL Server then we should implement the best known practices like indexing.
