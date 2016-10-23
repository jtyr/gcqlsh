# gcqlsh

Cassandra command line shell written in Golang

![](screenshots/gcqlsh_rec.gif?raw=true)


Motivation
----

Having a cassandra command line shell utility in one binary distributable.

Where it comes in hand?
----

 * Building docker images for cassandra from Alpine with no Python.
 * Running cql shell on all platforms.
 * Automating cassandra schema creation without need to install python dependencies.

Building
----

``` 
go get github.com/npenkov/gcqlsh

go build -o gocqlsh src/github.com/npenkov/gcqlsh/gcqlsh.go
```

Fatures
----
 * Running script files from command line
 * Support for Cassandra 2.1+/ScyllaDB
 * CQL Support
 * `desc` command with
   * `keyspaces`
   * `keyspace`
   * `tables`
 * Auto completition for commands:
   * `use`
   * `desc`
   * `select`
   * `update`
   * `delete`
   * `insert`

Command line help
----
```
gcqlsh -h
Usage of gcqlsh:
  -f string
        Execute file containing cql statements instead of having interacive session
  -fail-on-error
        Stop execution if statement from file fails.
  -host string
        Cassandra host to connect to (default "127.0.0.1")
  -k string
        Default keyspace to connect to (default "system")
  -no-color
        Console without colors
  -port int
        Cassandra RPC port (default 9042)
  -print-confirmation
        Print 'ok' on successfuly executed cql statement from the file
  -print-cql
        Print Statements that are executed from a file
```

Planned features
----
 * `desc` for table
 * Column code assistance for 
   * `select`
   * `update`
   * `delete` 
   * `insert` 

Package dependencies
----

 * [Readline](https://github.com/chzyer/readline)
 * [Color](https://github.com/fatih/color)
 * [Gocql](https://github.com/gocql/gocql)

----

Written with [vim-go](https://github.com/fatih/vim-go)
