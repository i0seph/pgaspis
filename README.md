# pgaspis
Column base crypto suite for PostgreSQL

```
client ----  (request author) ----->  keyserver
        <---- (response session key)+
       -------------------(request connect) -------------> PostgreSQL
       <-------- (response session established)---------+
       --------- (request en/decrypt key with session key) -> PostgreSQL 
       
PostgreSQL --- (request with session key for load en/decrypt key on session memory) ---> key server
          <---- (session process load crypt key on self memory) <-----------------------
          
client ---- (send query encrypt function) -------------------> PostgreSQL session ->
       <----- (en/decrypt data using key in session memory) -+ 
```

## Suite
1. aspisd (key server) - python flask
2. aspis-admin - (key generator and access control) - python flask + javascript
3. aspis-client-samples (java, php, python, psql)
4. pgaspis - PostgreSQL extension module, wrapper on pgcrypto for using en/decrypt - C 

Let's coding!
