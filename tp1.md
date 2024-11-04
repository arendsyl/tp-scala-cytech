# Scala - TP1

## Part I - Installing Scala 3

Follow the instructions at (https://docs.scala-lang.org/getting-started/install-scala.html#install-scala-on-your-computer)

Don’t do Using the Scala CLI

## Part II - Hello World

Run `sbt new scala/scala3.g8` and follow the prompts, name your project `hello-world`. 

You should obtain something like : 
```
- hello-world
    - project (sbt uses this to install and manage plugins and dependencies)
        - build.properties
    - src
        - main
            - scala (All of your scala code goes here)
                - Main.scala (Entry point of program) <-- this is all we need for now
    - build.sbt (sbt's build definition file)
```

`cd hello-world`
`sbt run`

then delete this file.

## Part III - Setting up an IDE

You can use any IDE that you want.

If you use IntelliJ IDEA you can install the Official Scala extension

If you use any other text editors you can install Metals to transform it into a Scala IDE : 
    https://scalameta.org/metals/

There is many supported IDE and text editors.




