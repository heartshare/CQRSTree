# CQRSTree
读写分离架构技术研究

![](https://i.imgur.com/rbPum2Y.png)

<pre>
CQRS(Command Query Responsibility Segregation)模式是一种架构体系模式，能够使改变模型
的状态的命令和模型状态的查询实现分离。
</pre>

<pre>
     在客户端就将数据的新增，修改，删除等动作和查询进行分离，
</pre>

![](https://i.imgur.com/a2AuCdA.png)


![](https://i.imgur.com/SZuaP75.png)

<pre>
          主数据库处理CUD,从库处理R,从库的结构和主库的结构完全一致，也可以不一样，从库主
      要用来进行只读的查询操作。在数量上从库的个数可以根据查询规模进行扩展，在业务逻辑上，
      也可以根据专题从主库中划分出不同的库，根据查询的业务逻辑，从主库中抽取一些必要的数据
      生成一系列查询报表来存储。

          ReportingDataBase的数据结构可以针对常用的查询请求进行优化设计。
          ReportingDataBase的数据库通常去正规化，存储一些冗余而减少必要的Join查询操作，
               使得业务查询简化和高效。
</pre>