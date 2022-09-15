### install java
```
sudo apt install openjdk-11-jre-headless -y
```
### download neo4j enterprise
```
wget https://neo4j.com/artifact.php?name=neo4j-enterprise-4.4.10-unix.tar.gz -O neo4j-enterprise-4.4.10-unix.tar.gz
```

### Untar neo4j packages
```
cp 'artifact.php?name=neo4j-enterprise-4.4.10-unix.tar.gz'  neo4j-enterprise-4.4.10-unix.tar.gz && rm 'artifact.php?name=neo4j-enterprise-4.4.10-unix.tar.gz' && tar -xvf neo4j-enterprise-4.4.10-unix.tar.gz
```

### download plugim
```
wget https://github.com/neo4j/graph-data-science/releases/download/2.1.8/neo4j-graph-data-science-2.1.8.jar
```
```
wget https://github.com/neo4j-contrib/neo4j-apoc-procedures/releases/download/4.4.0.8/apoc-4.4.0.8-all.jar
```
```
wget https://neo4j.com/artifact.php?name=neo4j-bloom-2.4.0.zip -O neo4j-bloom-2.4.0.zip
```

### Edit conf
```
dbms.security.procedures.unrestricted=apoc.*,gds.*,bloom.*
dbms.security.procedures.allowlist=apoc.*,gds.*,bloom.*
apoc.import.file.enabled=true
apoc.import.file.use_neo4j_config=true
dbms.default_listen_address=0.0.0.0
dbms.default_advertised_address=<your ip>
```

### Start neo4j
```
./neo4j start
```

