### OpenChai README

The **mllib demo** may be run as follows

- SPARK_HOME=/shared/spark-1.2.1 mvn exec:java  -DskipTests -Dexec.mainClass="org.openchai.demo.mllib.LBFGSRunner" -Dexec.args="local[4] 100000 4"

The output should look something like:

> 15/05/19 19:41:08 INFO optimization.GradientDescent: GradientDescent.runMiniBatchSGD finished. Last 10 stochastic losses 0.38205680002202125, 0.3819317369416647, 0.38181102250841764, 0.381694418966745, 0.38158170649721984, 0.38147268150188696, 0.3813671550864422, 0.38126495171308017, 0.38116590800170264, 0.38106987166060796
Finished test at Tue May 19 19:41:08 PDT 2015: duration=25

Note; there is a bug that the program is not cleaned up completely. So there may be error messages at the bottom:

> [WARNING]
java.lang.InterruptedException: sleep interrupted
	at java.lang.Thread.sleep(Native Method)
	at org.apache.spark.executor.Executor$$anon$1.run(Executor.scala:417)
15/05/19 19:41:08 ERROR spark.ContextCleaner: Error in cleaning thread
java.lang.InterruptedException

These may be safely ignored
