<h1>WordCount MapReduce Program Instructions</h1>
<h2>1. Compile the Java File</h2>
<p>Use the following command to compile the Java file:</p>
<pre><code>javac -classpath $(hadoop classpath) -d . WordCount.java</code></pre>
<p><strong>Example:</strong></p>
<pre><code>javac --release 11 -classpath $(hadoop classpath) -d . WordCount.java</code></pre>
<p><em>Note:</em> Here, <code>--release 11</code> ensures compatibility with Java version 11.</p>

<h2>2. Package the Compiled Classes into a JAR File</h2>
<p>Run the following command to create the JAR file:</p>
<pre><code>jar -cvf wordcount.jar -C . .</code></pre>

<h2>3. Run the WordCount Program</h2>
<p>Execute the program using the command below:</p>
<pre><code>hadoop jar wordcount.jar WordCount &lt;input_path&gt; &lt;output_path&gt;</code></pre>
<p><strong>Example:</strong></p>
<pre><code>hadoop jar wordcount.jar WordCount file:///Users/drpadhaya/desktop/WORD-COUNT/Input.txt file:///Users/drpadhaya/desktop/WORD-COUNT/Output.txt</code></pre>

<h2>4. Check the Output</h2>
<p>To view the results, use this command:</p>
<pre><code>hadoop fs -cat &lt;output_path&gt;/part-r-00000</code></pre>
<p><strong>Example:</strong></p>
<pre><code>cat /Users/drpadhaya/desktop/WORD-COUNT/Output.txt/part-r-00000</code></pre>

<h2>5. Possible Errors and Solutions</h2>
<ul>
<li><strong>Output file already present:</strong>
<p>Delete the output directory:</p>
<pre><code>rm -r /path/to/output</code></pre>
</li>
<li><strong>Incorrect JAVA_HOME:</strong>
<p>Verify the JAVA_HOME environment variable:</p>
<pre><code>echo $JAVA_HOME</code></pre>
<p>If incorrect, set it to the correct Java path:</p>
<pre><code>export JAVA_HOME=/path/to/java</code></pre>
</li>
<li><strong>Incorrect HADOOP_HOME:</strong>
<p>Verify the HADOOP_HOME environment variable:</p>
<pre><code>echo $HADOOP_HOME</code></pre>
<p>If incorrect, set it to the Hadoop installation path:</p>
<pre><code>export HADOOP_HOME=/opt/homebrew/opt/hadoop</code></pre>
<p>Update the system PATH:</p>
<pre><code>export PATH=$PATH:$HADOOP_HOME/bin</code></pre>
<p>Set the Hadoop configuration directory:</p>
<pre><code>export HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop</code></pre>
  </li>
</ul>
<p>For additional details, consult the <code>Hadoop</code> documentation or relevant resources.</p>
</body>
</html>
