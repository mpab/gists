# Apache Spark Toolchain Setup

## Install JDK 8

<https://adoptopenjdk.net/upstream.html>

Windows x64

Unzip to a suitable location: e.g. C:\Apps\openjdk-8u242-b08

add JAVA_HOME as a system environment variable

JAVA_HOME=C:\Apps\openjdk-8u242-b08

add %JAVA_HOME%\bin to the system path

## Install Spark

<https://spark.apache.org/downloads.html>

Select version 2.4.5

add SPARK_HOME as a system environment variable

SPARK_HOME=C:\Apps\spark-2.4.5-bin-hadoop2.7

add %SPARK_HOME%\bin to the system path

## Hadoop pseudo-dependency: Install WinUtil.exe

Clone to a suitable folder - C:\Apps\

```shell
$ cd /c/Apps
$ git clone https://github.com/steveloughran/winutils
...
```

add HADOOP_HOME as a system environment variable

HADOOP_HOME=C:\Apps\winutils\hadoop-2.6.0

add %HADOOP_HOME%\bin to the system path

## Install SBT

<https://www.scala-sbt.org/download.html?_ga=2.116844481.61443651.1582829212-2076652388.1582554858>

copy to a suitable folder:

C:\Apps\sbt-1.3.8\sbt

add SBT_HOME as a system environment variable

SBT_HOME=C:\Apps\C:\Apps\sbt-1.3.8\sbt

add %SBT_HOME%\bin to the system path

check SBT

```shell
$ sbt
sbt:> console
scala> :q
sbt:> exit
$ _
```

## Install Scala (If your SBT installer has not already done this)

Check compatibility : https://spark.apache.org/docs/latest/

"Spark runs on Java 8, Python 2.7+/3.4+ and R 3.1+. For the Scala API, Spark 2.4.5 uses Scala 2.12. You will need to use a compatible Scala version (2.12.x)."

https://www.scala-lang.org/download/2.12.10.html

add SCALA_HOME as a system environment variable

SCALA_HOME=C:\Apps\scala-2.12.10

add %SCALA_HOME%\bin to the system path

check scala

```shell
$ scala
Welcome to Scala 2.12.10 (OpenJDK 64-Bit Server VM, Java 1.8.0_242).
Type in expressions for evaluation. Or try :help.

scala> :quit
```

## Spark Configuration

Fix the configuration file:
Copy %SPARK_HOME%/conf/spark-defaults.config.template => %SPARK_HOME%/conf/spark-defaults.config

Edit the contents e.g.

Minimal spark-defaults.config file

```config
spark.ssl.ui.port       51837
spark.driver.port       51836
spark.driver.memory     32g
spark.sql.warehouse.dir C:///spark-warehouse
```

Create the folder C:\spark-warehouse according to the configuration
