fluentd的配置文件


tag：为数据流的标记。fluentd中可以具有多个数据源，解析器，过滤器和数据输出。他们之前使用tag来对应。类似于数据流按照tag分组。数据流向下游的时候只会进入tag相匹配的处理器。
time：event产生的时间，该字段通常由日志内的时间字段解析出来。
record：日志的内容，为JSON格式。
fluentd支持多种数据的解析过滤和输出操作。其中常用的有：

tail输入：增量读取日志文件作为数据源，支持日志滚动。
exec输入：定时执行命令，获取输出解析后作为数据源。
syslog输出：解析标准的syslog日志作为输入。
forward输入：接收其他fluentd转发来的数据作为数据源。
dummy：虚拟数据源，可以定时产生假数据，用于测试。
regexp解析器：使用正则表达式命名分组的方式提取出日志内容为JSON字段。
record_transformer过滤器：人为修改record内的字段。
file输出：用于将event落地为日志文件。
stdout：将event输出到stdout。如果fluentd以daemon方式运行，输出到fluentd的运行日志中。
forward：转发event到其他fluentd节点。
copy：多路输出，复制event到多个输出端。
kafka：输出event到Kafka。
webhdfs：输出event到HDFS。
elasticsearch：输出event到HDFS。


demo
https://stackoverflow.com/questions/55581226/fluentd-multi-level-nested-escaped-json-strings-inside-json