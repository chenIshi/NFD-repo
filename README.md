NFD
===
*A Language Design for Network Function Development*

NFD, an NF development framework, which decouples the NF functional logic from
environmental adaptation logic. NFD consists of a domain specific language and a compiler; the NFD language is platform - independent and used to develop NFs, namely NF models; the compiler has open interfaces to integrate various en-
vironmental features, namely environmental plugins.


## Run with *nix

1. install required tools

    1. `$ (sudo) apt-get update && (sudo) apt-get upgrade`

    2. install java sdk `$ (sudo) apt-get default-jdk`

    3. install [antlr](https://github.com/antlr/antlr4/blob/master/doc/getting-started.md) tool

        `$ cd /usr/local/lib`

        `$ curl -O https://www.antlr.org/download/antlr-4.7.1-complete.jar`

        `$ export CLASSPATH=".:/usr/local/lib/antlr-4.7.1-complete.jar:$CLASSPATH"`

        `$ alias antlr4='java -Xmx500M -cp "/usr/local/lib/antlr-4.7.1-complete.jar:$CLASSPATH" org.antlr.v4.Tool'`

        `$ alias grun='java -Xmx500M -cp "/usr/local/lib/antlr-4.7.1-complete.jar:$CLASSPATH" org.antlr.v4.gui.TestRig'`

    4. compile with antlr and javac

        `cd compiler/src`

        *we use [vister mode](https://abcdabcd987.com/notes-on-antlr4/) to traverse syntax tree*

        `antlr4 NFCompiler.g4 -visitor -o nflanguage/` 

        `javac main/Interpreter.java`