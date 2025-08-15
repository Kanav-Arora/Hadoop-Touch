# Important Commands

#### -> Compiling Java Files with Hadoop Classpath

```bash
javac -classpath $(hadoop classpath) -d . [filename].java
```

<b>Note:</b>
Replace [filename] in above command

#### -> Package into JAR File

```bash
jar -cvf [filename].jar *.class
```

<b>Note:</b> 
Replace [filename] in above command

#### -> HDFS Remove Folder

```bash
hdfs dfs -rm -r /output/
```

#### -> Job Run on Hadoop

```bash
hadoop jar /jobs/HttpLogAnalysis/HttpLogAnalyzer.jar HttpLogAnalysis /input/HttpLogAnalysis/weblog.csv /output_yarn/HttpLogAnalysis
```

#### -> Get Output from HDFS to Machine

```bash
mkdir -p /output/HttpLogAnalysis && \
hdfs dfs -get /output_yarn/HttpLogAnalysis/part-r-00000 /output/HttpLogAnalysis/HttpLogAnalysis.txt
```

<b>Note:</b> 
Replace input and output directory along with the filename.
