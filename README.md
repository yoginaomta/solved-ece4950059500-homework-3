Download Link: https://assignmentchef.com/product/solved-ece49500_59500-homework-3
<br>
<strong>Task 1 </strong><strong>. </strong>You <strong><u>must have</u></strong> to add screenshots in the report for the output of <u>underlined</u> <u>text in orange color</u> to get full score for the task.<strong> Part A [5 points]</strong>: Flume installation and set-up.

<ol>

 <li>Download Apache Flume from <a href="https://www.apache.org/dyn/closer.lua/flume/1.9.0/apache-flume-1.9.0-bin.tar.gz">http://www.apache.org/dyn/closer.lua/flume/1.9.0/apache</a><a href="https://www.apache.org/dyn/closer.lua/flume/1.9.0/apache-flume-1.9.0-bin.tar.gz">flume-1.9.0-bin.tar.gz</a></li>

 <li>Extract the setup file in the downloaded folder using command: tar xvfz apache-flume-1.9.0-bin.tar.gz</li>

 <li>Move the extracted folder to /usr/local/flume using command sudo mv apache-flume-1.9.0-bin /usr/local/flume</li>

 <li>Change the ownership of /usr/local/flume using command sudo chown -R bigdata:bigdata /usr/local/flume</li>

</ol>

<strong>Note:</strong> here bigdata is user name. In your case it may be different. You can get the user name by executing command whoami

<ol start="5">

 <li>Update .bashrc file in your home directory using command: gedit ~/.bashrc  Add following lines in .bashrc file at the end:</li>

</ol>

export FLUME_HOME=/usr/local/flume     export PATH=$PATH:$FLUME_HOME/bin/

Close .bashrc file and execute source .bashrc command

<ol start="6">

 <li>Start Hadoop service (if not running) using <strong>start-all.sh</strong> command and execute flume-ng –help. <u>If you see any output with command options, it means Flume has</u> <u>installed in your system.</u></li>

</ol>

<strong>Part B </strong>: Create a Flume agent to copy data files flume1.txt and flume2.txt (uploaded with the assignment) from /tmp/flume directory to /user/flume directory in HDFS cluster. You have to copy each file in /tmp/flume folder one by one and Flume should copy them in HDFS. Finally verify that files have been copied into the cluster. <u>Show the files content in</u> <u>HDFS cluster</u>. You need to write and save the agent file in /usr/local/flume/conf folder.




<strong>Task 2</strong><strong>. </strong>You <strong><u>must have</u></strong> to add screenshots in the report for the output of <u>underlined</u> <u>text in orange color</u> to get full score for the task.

<strong>Part A [10 points]</strong>: Hive installation and set-up

<ol>

 <li>Download Hive from <a href="https://mirrors.sonic.net/apache/hive/hive-2.3.7/apache-hive-2.3.7-bin.tar.gz">https://mirrors.sonic.net/apache/hive/hive-2.3.7/apache-hive-2.3.7</a><a href="https://mirrors.sonic.net/apache/hive/hive-2.3.7/apache-hive-2.3.7-bin.tar.gz">tar.gz</a></li>

 <li>Extract the setup file in the downloaded folder using command: tar xvfz apachehive-2.3.7-bin.tar.gz</li>

 <li>Move the extracted folder to /usr/local/hive using command: sudo mv apachehive-2.3.7-bin /usr/local/hive</li>

 <li>Change the ownership of /usr/local/hive using command: sudo chown -R bigdata:bigdata /usr/local/hive</li>

 <li>Update .bashrc file in your home directory using command: gedit ~/.bashrc Add following lines in .bashrc file at the end: export HIVE_HOME=/usr/local/hive  export PATH=$PATH:$HIVE_HOME/bin/  export HIVE_CONF_DIR=$HIVE_HOME/conf</li>

</ol>

Close .bashrc file and execute source .bashrc command

<ol start="6">

 <li>Copy /usr/local/hive/conf/hive-env.sh.template file to</li>

</ol>

/usr/local/hive/conf/hive-env.sh and open it using gedit

/usr/local/hive/conf/hive-env.sh command          Add HADOOP_HOME=/usr/local/hadoop in the file

<ol start="7">

 <li>Create hive-site.xml inside /usr/local/hive/conf folder using command touch hive-site.xml</li>

</ol>

Open it using gedit /usr/local/hive/conf/hive-site.xml

Add following lines in the file

&lt;configuration&gt;

&lt;property&gt;

&lt;name&gt;system:java.io.tmpdir&lt;/name&gt;

&lt;value&gt;/tmp/hive/java&lt;/value&gt;

&lt;/property&gt;

&lt;property&gt;

&lt;name&gt;system:user.name&lt;/name&gt;

&lt;value&gt;${user.name}&lt;/value&gt;

&lt;/property&gt;

&lt;property&gt;

&lt;name&gt;javax.jdo.option.ConnectionURL&lt;/name&gt;




&lt;value&gt;jdbc:derby:;databaseName=metastore_db;create=true&lt;/value&gt;

&lt;/property&gt;

&lt;/configuration&gt;

<ol start="8">

 <li>Copy hive-default.xml.template to hive-default.xml inside</li>

</ol>

/usr/local/hive/conf folder

<ol start="9">

 <li>Execute command schematool -initSchema -dbType derby</li>

 <li>Start Hadoop service (if not running) using start-all.sh and then execute hive command. <u>If you see </u><u>hive</u><u> prompt, it means Hive has installed in your system</u>.</li>

</ol>

<strong>Part B </strong>: Upload students.txt (uploaded in with the assignment) file into HDFS cluster. <u>Find the average score for each subject by creating a Hive table for the file and execute</u> <u>query on it</u>.
















<strong>Task 3</strong><strong>. </strong>You <strong><u>must have</u></strong> to add screenshots in the report for the output of <u>underlined</u> <u>text in orange color</u> to get full score for the task. <strong>Part A [10 points]</strong>: Spark installation and set-up

<ol>

 <li>Download Apache Spark from <a href="https://mirrors.ocf.berkeley.edu/apache/spark/spark-3.0.1/spark-3.0.1-bin-hadoop2.7.tgz">https://mirrors.ocf.berkeley.edu/apache/spark/spark-</a></li>

</ol>

<a href="https://mirrors.ocf.berkeley.edu/apache/spark/spark-3.0.1/spark-3.0.1-bin-hadoop2.7.tgz">3.0.1/spark-3.0.1-bin-hadoop2.7.tgz</a>

<ol start="2">

 <li>Extract setup file in the downloaded folder using command: tar xvfz spark-3.0.1-bin-hadoop2.7.tgz</li>

 <li>Move extracted folder to /usr/local/spark using command:</li>

</ol>

sudo mv spark-3.0.1-bin-hadoop2.7 /usr/local/spark

<ol start="4">

 <li>Change ownership of /usr/local/spark using command: sudo chown -R bigdata:bigdata /usr/local/spark</li>

</ol>

Note: here bigdata is user name. In your case, it may be different. You can get the user name by executing command whoami

<ol start="5">

 <li>Update .bashrc file in your home directory using command: gedit ~/.bashrc</li>

</ol>

Add following lines in .bashrc file at the end:

export SPARK_HOME=/usr/local/spark export PATH=$PATH:$SPARK_HOME/bin/ export PYSPARK_PYTHON=python3

Close .bashrc file and execute source .bashrc command

<ol start="6">

 <li>Copy /usr/local/spark/conf/spark-env.sh.template file to /usr/local/spark/conf/spark-env.sh. Then, add the following line in /usr/local/spark/conf/spark-env.sh:</li>

</ol>

export SPARK_DIST_CLASSPATH=$(hadoop classpath)

<ol start="7">

 <li>Start Hadoop (if not running) using start-all.sh command and execute pyspark. <u>If</u> <u>you see Spark banner in the output, it means Spark has installed in your system.</u> You may exit from pyspark</li>

</ol>

<strong>Part B</strong>: Write Spark application that reads “<strong>words.txt</strong>” file from HDFS cluster and finds top 10 most frequent words and their frequencies. In the text file, a few words may appear in different forms, e.g. The, the, you have to treat them same. In addition, some words may have double quote, single quote or other non-alphabet character in the prefix or suffix, your program should be able to remove them and then consider the remaining characters as word. Implement this program through RDD transformation and action operation. You may start with uploaded skeleton code spark_wc.py for word count program. To run your spark application, execute spark-submit &lt;<em>your Spark Python file name</em>&gt;. Please use firstname_lastname_task3b.py format for naming the program file.




<strong>Part C [25 points]</strong>: (<em>Optional for ECE 49500 students</em>) Write Spark application that reads “sales.txt” file from HDFS cluster and finds average and standard deviation of stores’ sales in each city. Implement this program through Spark Dataframe and Spark SQL. You may start with the uploaded skeleton code spark_std.py. To run your spark application, execute spark-submit <em>&lt;your Spark Python file name&gt;</em>. Please use firstname_lastname_task3c.py format for naming the program file.  You may refer slides and following link: <a href="https://www.analyticsvidhya.com/blog/2016/10/spark-dataframe-and-operations/">https://www.analyticsvidhya.com/blog/2016/10/spark-dataframe-and-operations/</a>