[![verify](https://github.com/bootique-examples/bootique-jdbc-demo/actions/workflows/verify.yml/badge.svg)](https://github.com/bootique-examples/bootique-jdbc-demo/actions/workflows/verify.yml)
# bootique-jdbc-demo

How to work with JDBC data stores integrated for [Bootique](http://bootique.io) app. 
   
*For additional help/questions about this example send a message to
[Bootique forum](https://groups.google.com/forum/#!forum/bootique-user).*
   
## Prerequisites
      
    * Java 1.8 or newer.
    * Apache Maven.
    * Docker
      
## Build the Demo
      
Here is how to build it:
```bash           
git clone git@github.com:bootique-examples/bootique-jdbc-demo.git
cd bootique-jdbc-demo
mvn package
```
      
## Run the Bootique-jdbc Demo

Now you can check the options available in your app:
```bash  
java -jar bootique-jdbc/target/bootique-jdbc-2.0-SNAPSHOT.jar
```
```  
OPTIONS
      -c yaml_location, --config=yaml_location
           Specifies YAML config location, which can be a file path or a URL.

      -h, --help
           Prints this message.

      -H, --help-config
           Prints information about application modules and their configuration options.

      -i, --insert
           Demo command to insert data.

      -s, --select
           Demo command to select data.

```

Provide required configuration via *config.yml*:
```yaml  
jdbc:
  DerbyDatabase:
    jdbcUrl: jdbc:derby:target/derby/DerbyDatabase;create=true
```

Run custom command *--insert* to create a table:
```bash
java -jar bootique-jdbc/target/bootique-jdbc-2.0-SNAPSHOT.jar -c classpath:config.yml -i
```    
Check data via *--select* command:
```bash    
java -jar bootique-jdbc/target/bootique-jdbc-2.0-SNAPSHOT.jar  -c classpath:config.yml -s
```

New table "TEST" data is successfully created:   
```    
...
   The table TEST is successfully created
...
```