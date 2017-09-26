# Dockerized Spark (Windows)

Initial steps to install docker:

 * Download docker from its [Offcial website](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install), or just [here](https://download.docker.com/win/stable/Docker%20for%20Windows%20Installer.exe)
 * Please note that Docker for Windows requires Microsoft Hyper-V to run. The Docker for Windows installer will enable Hyper-V for you, if needed, and restart your machine. After Hyper-V is enabled, VirtualBox will no longer work, but any VirtualBox VM images will remain.
 * [kitematic](https://kitematic.com/) could provide a graphic interface for docker management.(Optional)
 * Restart your computer and hack in any command-line terminal.(PowerShell or CMD)


The spark running environment is already built. What you need to do is just pull them to the local machine and start to use it:

 * Pull the image from docker hub:
    ```bash
    docker pull zzz1990771/kafka_spark:v1
    ```
 * Run the image locally:
     ```bash
    docker run --name spark -it zzz1990771/kafka_spark:v1 /bin/bash
    ```
 * Start Spark-shell default:
     ```bash
    ./bin/spark-shell
    ```
    Note that the default programming language of Spark is Scala.
    
 * Or Python interactive interface of Spark:
     ```bash
    ./bin/pyspark
    ```
 * If you want to run a script over Spark, you can use:
     ```bash
    ./bin/spark-submit {your file}
    #for example
    ./bin/spark-submit examples/src/main/python/pi.py 10
    ./bin/spark-submit examples/src/main/r/dataframe.R
    ```
 * Exit Spark with CTRL + D

Whenever you want to exit this running environment without ending it, press CTRL + Q + P at the same time.

Some more you can do with docker:

* get the list of containers:
    ```bash
    docker ps -a
    ```

* get the list of docker images:
    ```bash
    docker images
    ```

* re-enter the runing container:
    ```bash
    docker exec -it spark /bin/bash
    ```

* restart a stoped container:
    ```bash
    docker start -i spark
    ```

This image has other built-in features to be update.


This is [on GitHub](https://github.com/zzz1990771/spark_workshop/blob/master/README.md).

