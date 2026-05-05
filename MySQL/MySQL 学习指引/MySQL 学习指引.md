# 背景

后端开发是很经常跟数据库打交道的，因为我们的业务数据是需要保存到数据库的，比如我们实现的读取数据接口是需要从数据库读取所需的数据返回给用户，同时还要把用户更新的数据写到数据库里，所以作为后端开发者，数据库是除了编程语言+计算基础之外，必须重点学习的内容，不管做项目还是面试，都是会涉及到数据库的。



![](<images/MySQL 学习指引-image.png>)

市面上数据库有很多种，常⽤的数据库有 MySQL、Oracle、SQLServer 等，这⼏个数据库，Oracle 性能排名第⼀，服务也是相当到位的，但是人家要收费的，而且价格也不便宜，⾦融公司对数据库稳定性要求⽐较⾼，⼀般会选择 Oracle。



相反，MySQL 是免费的，MySQL 在互联⽹公司使⽤率也是排名第⼀，资料也⾮常完善，社区也⾮常活跃，所以我们**主要学习 MySQL 数据库**。



MySQL 学习分三种阶段：

* 【SQL 基础】：学习 SQL 命令、字段和表结构设计、多表查询，SQL刷题等等；

* 【MySQL 原理】：学习 MySQL 架构、索引、事务、日志、锁、调优等，面试中都是考察 MySQL 原理比较多。

* 【MySQL 高可用】：学习 MySQL 主从复制、分库分表、高可用、分布式等等，校招需要简单了解，社招需要加强学习。



**MySQL学习讨论群：**

# 学习指引

## SQL 基础

SQL 基础主要通过下面这三份资料学习为主，这三份资料是我看过最精炼的，视频、文档、书籍资料可以搭配学习，对于 0 基础的同学，5天时间就能熟悉大部分 MySQL 基本操作了，这个<span style="color: inherit; background-color: rgba(255,246,122,0.8)">学习的过程中需要动手实验，这一点很重要！！！</span>

* 视频资料：[【中字】史上最易懂SQL教程！10小时零基础成长SQL大师！](https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0)

* 文档资料：[MySQL 教程](https://www.sjkjc.com/mysql/what-is-mysql/)&#x20;

* 书籍资料：《[MySQL必知必会](https://awesome-programming-books.github.io/mysql/MySQL%E5%BF%85%E7%9F%A5%E5%BF%85%E4%BC%9A.pdf)》



### SQL 语法

小林哥也把比较重要的知识列出了表格，让大家知道哪些是重点（<span style="color: inherit; background-color: rgb(255,233,40)">黄色标注的内容是需要重点学习的内容</span>），同时对于重点知识点会穿插一些辅助学习的资料。

<table><colgroup><col width="143"><col width="355"><col width="299"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>准备工作</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P1-P6）<br />文档资料：<a href="https://www.sjkjc.com/mysql/what-is-mysql/">MySql 简介</a>(MySQL起步章节)</td>
<td>在自己的电脑上安装 MySQL 和 MySQL 工作台，为后面的 SQL 学习和练习做准备。</td>
</tr>
<tr>
<td rowspan="2">查询语句<br /></td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P7-P17）
<br />文档资料：<a href="https://www.sjkjc.com/mysql/select/">MySQL SELECT 语句</a> (看SELECT到DISTINCT部分)<br /></td>
<td><ul>
<li>掌握查询语句涉及到的操作符： AND, OR, IN, NOT IN, BETWEEN, LIKE, IS NULL, EXISTS, DISTINCT</li>
<li>掌握查询语句涉及到的子句：WHERE, ORDER BY, LIMIT 子句</li>
</ul></td>
</tr>
<tr>
<td>order by工作原理：<ul>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%9845%E8%AE%B2/16%20%20%E2%80%9Corder%20by%E2%80%9D%E6%98%AF%E6%80%8E%E4%B9%88%E5%B7%A5%E4%BD%9C%E7%9A%84%EF%BC%9F.md"> “order by”是怎么工作的?.md</a></li>
</ul></td>
<td>了解order by的底层原理（没时间可以跳过，有时间再学）</td>
</tr>
<tr>
<td rowspan="2">多表查询<br /></td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P18-P30）<br />文档资料：<a href="https://www.sjkjc.com/mysql/join/">MySQL JOIN</a> 、<a href="https://www.sjkjc.com/mysql/union/">MySQL UNION</a><br />书籍资料：《<a href="https://awesome-programming-books.github.io/mysql/MySQL%E5%BF%85%E7%9F%A5%E5%BF%85%E4%BC%9A.pdf">MySQL必知必会</a>》（看第15章-17章节）<br /></td>
<td>掌握多表查询：JOIN（内连接、左连接、外连接）<br /><br />掌握组合查询：UNION</td>
</tr>
<tr>
<td>join工作原理（可以整个sql学完，再回来看）：<ul>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/11-%E4%B8%A4%E4%B8%AA%E8%A1%A8%E7%9A%84%E4%BA%B2%E5%AF%86%E6%8E%A5%E8%A7%A6-%E8%BF%9E%E6%8E%A5%E7%9A%84%E5%8E%9F%E7%90%86">第11章 两个表的亲密接触-连接的原理</a>（看第11章）</li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/12%20%20JOIN%20%E8%BF%9E%E6%8E%A5%EF%BC%9A%E5%88%B0%E5%BA%95%E8%83%BD%E4%B8%8D%E8%83%BD%E5%86%99%20JOIN%EF%BC%9F.md">JOIN 连接:到底能不能写 JOIN?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%9845%E8%AE%B2/34%20%20%E5%88%B0%E5%BA%95%E5%8F%AF%E4%B8%8D%E5%8F%AF%E4%BB%A5%E4%BD%BF%E7%94%A8join%EF%BC%9F.md">到底可不可以使用join?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%9845%E8%AE%B2/35%20%20join%E8%AF%AD%E5%8F%A5%E6%80%8E%E4%B9%88%E4%BC%98%E5%8C%96%EF%BC%9F.md">join语句怎么优化?.md</a></li>
</ul></td>
<td>了解 join 的底层原理（没时间可以跳过，有时间再学）<br /></td>
</tr>
<tr>
<td>增删改语句</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P31-P40）<br />文档资料：<a href="https://www.sjkjc.com/mysql/insert/">MySQL INSERT 用法与实例</a>、<a href="https://www.sjkjc.com/mysql/delete/">MySQL DELETE 用法与实例</a>、<a href="https://www.sjkjc.com/mysql/update/">MySQL UPDATE 用法与实例</a></td>
<td>掌握 INSERT、DELETE、UPDATE 语句的用法<br /></td>
</tr>
<tr>
<td rowspan="2">汇总、分组数据<br /></td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P41-P43）
<br />书籍资料：《<a href="https://awesome-programming-books.github.io/mysql/MySQL%E5%BF%85%E7%9F%A5%E5%BF%85%E4%BC%9A.pdf">MySQL必知必会</a>》（看第12章-第13章）<br /><br />count的工作原理<ul>
<li><a href="https://xiaolincoding.com/mysql/index/count.html">count(*) 和 count(1) 有什么区别？哪个性能最好？</a></li>
</ul></td>
<td><ul>
<li>掌握常用的聚合函数：COUNT, MAX, MIN, SUM, AVG</li>
<li>掌握 GROUP BY 和 HAVING 子句的用法</li>
<li>掌握 Where 和 HAVING 的区别

</li>
</ul>count(1)、count(<code>*</code>)、count(字段) 到底哪种效率是最好的？<br /></td>
</tr>
<tr>
<td>group by的工作原理：<ul>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%9845%E8%AE%B2/37%20%20%E4%BB%80%E4%B9%88%E6%97%B6%E5%80%99%E4%BC%9A%E4%BD%BF%E7%94%A8%E5%86%85%E9%83%A8%E4%B8%B4%E6%97%B6%E8%A1%A8%EF%BC%9F.md">什么时候会使用内部临时表?</a></li>
</ul></td>
<td>了解group by 的 sql怎么优化？（没时间可以跳过，有时间再学）</td>
</tr>
<tr>
<td rowspan="2">子查询<br /></td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P45-P54）<br />文档资料：<a href="https://www.sjkjc.com/mysql/subquery/">MySQL 子查询</a><br />书籍资料：《<a href="https://awesome-programming-books.github.io/mysql/MySQL%E5%BF%85%E7%9F%A5%E5%BF%85%E4%BC%9A.pdf">MySQL必知必会</a>》（看第14章）</td>
<td>掌握子查询的用法和原理<br /></td>
</tr>
<tr>
<td>子查询原理：<ul>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/14-%E4%B8%8D%E5%A5%BD%E7%9C%8B%E5%B0%B1%E8%A6%81%E5%A4%9A%E6%95%B4%E5%AE%B9-MySQL%E5%9F%BA%E4%BA%8E%E8%A7%84%E5%88%99%E7%9A%84%E4%BC%98%E5%8C%96%EF%BC%88%E5%86%85%E5%90%AB%E5%85%B3%E4%BA%8E%E5%AD%90%E6%9F%A5%E8%AF%A2%E4%BC%98%E5%8C%96%E4%BA%8C%E4%B8%89%E4%BA%8B%E5%84%BF%EF%BC%89">第14章 不好看就要多整容-MySQL基于规则的优化(内含关于子查询优化二三事儿</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/13%20%20%E5%AD%90%E6%9F%A5%E8%AF%A2%EF%BC%9A%E6%94%BE%E5%BF%83%E5%9C%B0%E4%BD%BF%E7%94%A8%E5%AD%90%E6%9F%A5%E8%AF%A2%E5%8A%9F%E8%83%BD%E5%90%A7%EF%BC%81.md">子查询:放心地使用子查询功能吧!.md</a></li>
</ul></td>
<td>了解子查询的原理（没时间可以跳过，有时间再学，不是面试重点）<br /></td>
</tr>
<tr>
<td>SQL 执行顺序<br /></td>
<td><a href="https://blog.csdn.net/weixin_44141495/article/details/108744720">一篇明白SQL的执行顺序</a><br /></td>
<td>join,select,where,order by,group by的执行顺序</td>
</tr>
<tr>
<td>函数、视图、存储过程、触发器</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>：<ul>
<li>函数：看P55-P62</li>
<li>视图：看P63-P67</li>
<li>存储：看P68-P78</li>
<li>触发器：看P79-P84</li>
</ul></td>
<td>这一部分过一遍就行，了解就行，不用太深入学。南邮通信<br /></td>
</tr>
<tr>
<td>事务</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P85-P94）</td>
<td>事务的用法：启动事务、回滚事务、提交事务</td>
</tr>
<tr>
<td>数据类型<br /></td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P95-P103）<br />文档资料：<a href="https://www.sjkjc.com/mysql/varchar/">MySQL 数据类型</a>（看完MySQL数据类型整个部分）<br />补充资料：<ul>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/01%20%20%E6%95%B0%E5%AD%97%E7%B1%BB%E5%9E%8B%EF%BC%9A%E9%81%BF%E5%85%8D%E8%87%AA%E5%A2%9E%E8%B8%A9%E5%9D%91.md">01 数字类型:避免自增踩坑.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/02%20%20%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%B1%BB%E5%9E%8B%EF%BC%9A%E4%B8%8D%E8%83%BD%E5%BF%BD%E7%95%A5%E7%9A%84%20COLLATION.md">02 字符串类型:不能忽略的 COLLATION.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/03%20%20%E6%97%A5%E6%9C%9F%E7%B1%BB%E5%9E%8B%EF%BC%9ATIMESTAMP%20%E5%8F%AF%E8%83%BD%E6%98%AF%E5%B7%A8%E5%9D%91.md">03 日期类型:TIMESTAMP 可能是巨坑.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/04%20%20%E9%9D%9E%E7%BB%93%E6%9E%84%E5%AD%98%E5%82%A8%EF%BC%9A%E7%94%A8%E5%A5%BD%20JSON%20%E8%BF%99%E5%BC%A0%E7%89%8C.md">04 非结构存储:用好 JSON 这张牌.md</a></li>
</ul></td>
<td>通过视频+文档资料认识 MySQL 常用的数据类型<br /><br /><br />通过补充资料，了解实际业务过程中，数据类型适合的业务场景。<br /></td>
</tr>
<tr>
<td>主键和外键</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P109-P111）</td>
<td>理解主键、外键的作用</td>
</tr>
<tr>
<td>      六大约束<br /></td>
<td>文档：<ul>
<li><a href="https://www.begtut.com/mysql/mysql-primary-key.html">MySQL 主键约束 | 新手教程</a></li>
<li><a href="https://www.begtut.com/mysql/mysql-foreign-key.html">MySQL 外键约束 | 新手教程</a></li>
<li><a href="https://www.begtut.com/mysql/mysql-unique-constraint.html">MySQL UNIQUE 约束 | 新手教程</a></li>
<li><a href="https://www.begtut.com/mysql/mysql-unique-constraint.html">MySQL UNIQUE 约束 | 新手教程</a></li>
<li><a href="https://www.begtut.com/mysql/mysql-check-constraint.html">MySQL CHECK 约束模拟 | 新手教程</a></li>
</ul></td>
<td> mysql的约束有哪些?<br /></td>
</tr>
<tr>
<td>三大范式</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P112-P117）
<br />博客资料：<ul>
<li><a href="https://segmentfault.com/a/1190000013695030">数据库逻辑设计之三大范式通俗理解</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/05%20%20%E8%A1%A8%E7%BB%93%E6%9E%84%E8%AE%BE%E8%AE%A1%EF%BC%9A%E5%BF%98%E8%AE%B0%E8%8C%83%E5%BC%8F%E5%87%86%E5%88%99.md">表结构设计:忘记范式准则.md</a>
</li>
</ul>书籍资料：<a href="https://juejin.cn/post/6976290766876311559">《高性能mysql第三版》</a>（4.3 MySQL 范式和反范式）</td>
<td>理解什么是三范式<br />实际开发中，反范式也不罕见。<br /></td>
</tr>
<tr>
<td>数据库表设计</td>
<td><ul>
<li>博客：<a href="https://www.cnblogs.com/better-farther-world2099/articles/17212891.html">21个设计MySQL数据库表的经验准则 </a></li>
</ul></td>
<td>简单了解一下数据库表设计经验</td>
</tr>
<tr>
<td>创建表</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P128-P134）</td>
<td>了解如何创建一张数据库表</td>
</tr>
<tr>
<td>索引</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P134-P146）<br />文档资料：<a href="https://www.sjkjc.com/mysql/create-index/">MySQL 索引</a>（看完MySQL索引整个部分）</td>
<td>掌握索引的作用，创建索引的方法，索引的类型。</td>
</tr>
<tr>
<td>数据库管理</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1UE41147KC/?vd_source=894a223b85ae44e61e16dcd1a7356db0">SQL视频教程</a>（看P147-P155）<br />文档资料：<a href="https://www.sjkjc.com/mysql/start-stop-mysql/">MySQL 数据库管理</a>（简单过一下MySQL数据管理部分就行）</td>
<td>了解 MySQL 基本的运维命令：<ul>
<li>如何启动和停止 MySQL 进程</li>
<li>如何管理 MySQL 用户</li>
</ul></td>
</tr>
<tr>
<td>SQL 注入</td>
<td>文档资料：<a href="https://www.cloudflare-cn.com/learning/security/threats/sql-injection/">SQL 注入 | 什么是 SQL 注入？</a></td>
<td><ul>
<li>了解 SQL 安全，SQL 注入基本感念，常见的防范措施</li>
</ul></td>
</tr>
</tbody>
</table>



### SQL 面试题

面试过程中，面试官有时候会让你根据他提出的场景写一个 SQL 语句或者针对 xxx 场景设计数据库表，可通过下面这两个资料加强练习。

| 内容          | 资料                                                                              | 说明                                                                           |
| ----------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
|       SQL题库 | [ SQL面试题题库](https://ls8sck0zrg.feishu.cn/wiki/MaRiwPFqMiaBCvkJfYVcmM8JnLc)      | SQL 题目通常根据业务需求编写一条比较复杂的**查询语句**，所以是在考察你对 JOIN、GROUB BY、ORDER BY 理解程度，不会特别复杂。 |
| 数据表设计       | [新零售数据结构设计 ](https://zq99299.github.io/mysql-tutorial/ali-new-retail/04/)<br /> | 很多同学面试过程中，被到某个场景怎么设计数据库表，可以通过电商平台的案例来学习数据库表的设计思路。                            |



## MySQL 原理

掌握完 SQL 语法后，我们就可以深入学习  MySQL 原理了，主要有这几大块内容：



针对比较重要的知识列出了表格，让大家知道哪些是重点（<span style="color: inherit; background-color: rgb(255,233,40)">黄色标注的内容是需要重点学习的内容</span>）。

### 逻辑架构

| 内容               | 资料                                                                                                                                                                                                                                                                                                                                                                                                    | 说明                                                   |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| MySQL 架构         | 书籍资料：[《高性能mysql第三版》](https://juejin.cn/post/6976290766876311559)（1.1 MySQL 逻辑架构）<br />视频资料：[109-配置文件、系统变量与MySQL逻辑架构](https://www.bilibili.com/video/BV1iq4y1u7vj?p=109\&vd_source=894a223b85ae44e61e16dcd1a7356db0)                                                                                                                                                                                   | 对 MySQL 架构 有个整体上的认识<br />                            |
| 一条SQL的执行过程<br /> | 自产资料：[执行一条 select 语句，期间发生了什么？](https://xiaolincoding.com/mysql/base/how_select.html)<br />视频资料：[110-SQL执行流程](https://www.bilibili.com/video/BV1iq4y1u7vj?p=110\&vd_source=894a223b85ae44e61e16dcd1a7356db0)                                                                                                                                                                                           | 整体的结构，有哪些模块，做什么，要理解，后面需要能讲出来<br />                   |
| 引擎分类<br />       | 视频资料：[113-设置表的存储引擎、InnoDB与MyISAM的对比](https://www.bilibili.com/video/BV1iq4y1u7vj?p=113\&vd_source=894a223b85ae44e61e16dcd1a7356db0)<br />书籍资料：[《高性能mysql第三版》](https://juejin.cn/post/6976290766876311559)（1.5 MySQL 存储引擎）<br />博客资料：[MySQL引擎篇:半道出家的InnoDB为何能替换官方的MyISAM? ](https://juejin.cn/post/7160557698642083847)<br />官方资料：[引擎分类](https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html) | MySQL 存储引擎有哪些？<br />Innodb 和 MyISAM 存储引擎有什么区别？<br /> |

### InnoDB存储引擎

<table><colgroup><col width="157"><col width="310"><col width="332"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>一行记录的存储格式<br /></td>
<td>自产资料：<a href="https://xiaolincoding.com/mysql/base/row_format.html">MySQL 一行记录是怎么存储的？</a><br />书籍资料：<a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/04-%E4%BB%8E%E4%B8%80%E6%9D%A1%E8%AE%B0%E5%BD%95%E8%AF%B4%E8%B5%B7-InnoDB%E8%AE%B0%E5%BD%95%E7%BB%93%E6%9E%84">第4章 从一条记录说起-InnoDB记录结构</a><br /></td>
<td>数据库表的数据存放在哪？<br />InnoDB 表空间结构有哪些组成？<br />varchar 是怎么保存长度的？<br />Null 值是如何保存的？</td>
</tr>
<tr>
<td>char和varchar</td>
<td>文档资料：<ul>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/02%20%20%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%B1%BB%E5%9E%8B%EF%BC%9A%E4%B8%8D%E8%83%BD%E5%BF%BD%E7%95%A5%E7%9A%84%20COLLATION.md">字符串类型:不能忽略的 COLLATION.md</a></li>
<li><a href="https://blog.csdn.net/yunhua_lee/article/details/7038780">MySQL Innodb数据库性能实践——VARCHAR vs CHAR</a></li>
</ul>书籍资料：<a href="https://juejin.cn/post/6976290766876311559">《高性能mysql第三版》</a>（看第 4.1.3 小节）</td>
<td>char和varcahr的区别要清楚，两者性能差异也要清楚。<br />varchar(10)和varchar(100)，如果只使用了5字节，内存和文件分别占用多少字节？<br /></td>
</tr>
<tr>
<td>数据页<br /></td>
<td>文档资料：<a href="https://xiaolincoding.com/mysql/index/page.html">从数据页的角度看 B+ 树</a><br />书籍资料：<ul>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/05-%E7%9B%9B%E6%94%BE%E8%AE%B0%E5%BD%95%E7%9A%84%E5%A4%A7%E7%9B%92%E5%AD%90-InnoDB%E6%95%B0%E6%8D%AE%E9%A1%B5%E7%BB%93%E6%9E%84">第5章 盛放记录的大盒子-InnoDB数据页结构</a></li>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/06-%E5%BF%AB%E9%80%9F%E6%9F%A5%E8%AF%A2%E7%9A%84%E7%A7%98%E7%B1%8D-B+%E6%A0%91%E7%B4%A2%E5%BC%95">第6章 快速查询的秘籍-B+树索引</a></li>
</ul></td>
<td>聚簇索引和非聚簇索引的 B+ 树结构有什么区别？<br /></td>
</tr>
<tr>
<td>Buffer Pool</td>
<td>自产资料：<a href="https://xiaolincoding.com/mysql/buffer_pool/buffer_pool.html">揭开 Buffer Pool  的面纱</a></td>
<td>InnoDB 对 LRU 做了哪些优化？</td>
</tr>
<tr>
<td> Change Buffer<br /></td>
<td>文档资料：<a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%9845%E8%AE%B2/09%20%20%E6%99%AE%E9%80%9A%E7%B4%A2%E5%BC%95%E5%92%8C%E5%94%AF%E4%B8%80%E7%B4%A2%E5%BC%95%EF%BC%8C%E5%BA%94%E8%AF%A5%E6%80%8E%E4%B9%88%E9%80%89%E6%8B%A9%EF%BC%9F.md">普通索引和唯一索引，应该怎么选择?.md</a></td>
<td>普通索引和唯一索引有什么区别？
哪个更新性能更好？</td>
</tr>
</tbody>
</table>

### 索引（重点）

<table><colgroup><col width="157"><col width="310"><col width="332"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>索引数据结构<br /></td>
<td><br />文档资料：<ul>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/08%20%20%E7%B4%A2%E5%BC%95%EF%BC%9A%E6%8E%92%E5%BA%8F%E7%9A%84%E8%89%BA%E6%9C%AF.md">索引:排序的艺术.md</a></li>
<li><a href="https://xiaolincoding.com/mysql/index/why_index_chose_bpuls_tree.html">为什么 MySQL 采用 B+ 树作为索引？</a></li>
</ul>视频资料：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=115&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">115-为什么使用索引及索引的优缺点</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=118&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">118-聚簇索引、二级索引与联合索引的概念</a></li>
</ul></td>
<td>什么是索引？为什么索引能加快查询？<br />索引的数据结构是什么？<br />B+ 树和（B 树和红黑树）有什么区别？为什么选择用 B+ 树 作为索引数据结构？<br /></td>
</tr>
<tr>
<td>索引存储</td>
<td>文档资料：<a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/09%20%20%E7%B4%A2%E5%BC%95%E7%BB%84%E7%BB%87%E8%A1%A8%EF%BC%9A%E4%B8%87%E7%89%A9%E7%9A%86%E7%B4%A2%E5%BC%95.md">索引组织表:万物皆索引.md</a><br /></td>
<td>堆表和索引组织表有什么区别？分别应用场景是什么？</td>
</tr>
<tr>
<td>联合索引<br /></td>
<td>文档资料：<a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/10%20%20%E7%BB%84%E5%90%88%E7%B4%A2%E5%BC%95%EF%BC%9A%E7%94%A8%E5%A5%BD%EF%BC%8C%E6%80%A7%E8%83%BD%E6%8F%90%E5%8D%87%2010%20%E5%80%8D%EF%BC%81.md">组合索引:用好，性能提升 10 倍!.md</a><br />会议资料：<a href="https://ls8sck0zrg.feishu.cn/wiki/CgAqwymqXiSxYikP0Mac273fnkb"> MySQL夜市8月25日（联合索引）</a> <br /></td>
<td>联合索引的结构是怎样的？<br />如何利用联合索引提升查询性能？<br /></td>
</tr>
<tr>
<td>索引失效<br /></td>
<td>自产资料：<a href="https://xiaolincoding.com/mysql/index/index_lose.html#%E7%B4%A2%E5%BC%95%E5%AD%98%E5%82%A8%E7%BB%93%E6%9E%84%E9%95%BF%E4%BB%80%E4%B9%88%E6%A0%B7">索引失效有哪些？</a><br />视频资料：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=141&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">141-数据准备与索引失效的11种情况1</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=142&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">142-索引失效的11种情况2</a></li>
</ul></td>
<td>有哪些索引失效的场景？为什么会失效？<br /></td>
</tr>
<tr>
<td>索引选择</td>
<td>文档资料：<a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/11%20%20%E7%B4%A2%E5%BC%95%E5%87%BA%E9%94%99%EF%BC%9A%E8%AF%B7%E7%90%86%E8%A7%A3%20CBO%20%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86.md">索引出错:请理解 CBO 的工作原理.md</a></td>
<td>MySQL 数据库中的优化器是怎么执行的？根据什么标准选择索引的？</td>
</tr>
<tr>
<td>索引应用</td>
<td>博客资料：<a href="https://juejin.cn/post/7149074488649318431">MySQL索引应用篇:建立索引的正确姿势与使用索引的最佳指南! </a><br />书籍资料：<a href="https://juejin.cn/post/6976290766876311559">《高性能mysql第三版》</a> （第五章节）<br />视频资料：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=131&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">131-适合创建索引的11种情况1</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=132&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">132-适合创建索引的11种情况2</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=133&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">133-不适合创建索引的7种情况</a></li>
</ul></td>
<td>建立索引有什么优点和缺点？<br />如何正确的使用索引？<br />哪些场景下适合建立索引？<br />哪些场景下不适合建立索引？</td>
</tr>
<tr>
<td>索引面试题</td>
<td>自产资料：<a href="https://xiaolincoding.com/mysql/index/index_interview.html">索引常见面试题</a></td>
<td>面试重点，要吃透</td>
</tr>
</tbody>
</table>

### 事务（重点）

<table><colgroup><col width="157"><col width="310"><col width="332"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>事务ACID<br /></td>
<td>书籍资料：<ul>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/19-%E4%BB%8E%E7%8C%AB%E7%88%B7%E8%A2%AB%E6%9D%80%E8%AF%B4%E8%B5%B7-%E4%BA%8B%E5%8A%A1%E7%AE%80%E4%BB%8B">第19章 从猫爷被杀说起-事务简介</a>
</li>
</ul>视频资料：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=161&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">161-事务的ACID特性与事务的状态</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=162&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">162-显式事务与隐式事务</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=163&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">163-事务的使用举例</a></li>
</ul></td>
<td>理解ACID是什么，分别怎么实现的<br /></td>
</tr>
<tr>
<td>事务隔离级别<br /></td>
<td>自产资料：<ul>
<li><a href="https://xiaolincoding.com/mysql/transaction/mvcc.html">事务隔离级别是怎么实现的？</a></li>
<li><a href="https://xiaolincoding.com/mysql/transaction/phantom.html#%E4%BB%80%E4%B9%88%E6%98%AF%E5%B9%BB%E8%AF%BB">MySQL 可重复读隔离级别，完全解决幻读了吗？</a></li>
<li>视频：<a href="https://ls8sck0zrg.feishu.cn/wiki/Kh9Lwq4mXix9oMk8hNNcCwRknqd"> MySQL夜市9月16日（ 事务-MVCC）</a> </li>
</ul><br />书籍资料：<ul>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/24-%E4%B8%80%E6%9D%A1%E8%AE%B0%E5%BD%95%E7%9A%84%E5%A4%9A%E5%B9%85%E9%9D%A2%E5%AD%94-%E4%BA%8B%E5%8A%A1%E7%9A%84%E9%9A%94%E7%A6%BB%E7%BA%A7%E5%88%AB%E4%B8%8EMVCC">第24章 一条记录的多幅面孔-事务的隔离级别与MVCC</a>
</li>
</ul>视频资料（事务应用）：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=164&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">164-数据并发问题与4种隔离级别</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=166&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">166-读未提交隔离性下的演示</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=167&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">167-读已提交和可重复读的隔离性下的演示</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=168&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">168-幻读的演示与解决方案</a></li>
</ul>视频资料（mvcc）：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=183&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">183-MVCC解决读写问题</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=184&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">184-MVCC三剑客：隐藏字段、UndoLog版本链、ReadView规则</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=185&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">185-MVCC在读已提交和可重复读隔离级别下的操作流程</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=186&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">186-MVCC在可重复读下解决幻读的流程</a></li>
</ul></td>
<td>事务并发会产生什么问题？<br />事务隔离级别有哪些？怎么实现的？<br />读已提交和可重复读有什么区别？<br />MVCC 是什么？解决了什么问题？实现原理？<br />可重复读隔离级别彻底解决幻读了吗？<br /></td>
</tr>
</tbody>
</table>

### 锁

<table><colgroup><col width="157"><col width="310"><col width="332"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>锁类型</td>
<td>自产资料：<ul>
<li><a href="https://xiaolincoding.com/mysql/lock/mysql_lock.html">MySQL 有哪些锁？</a></li>
<li><a href="https://www.cnblogs.com/chanshuyi/p/diff-trans-level-lock.html">MySQL 不同隔离级别，都使用了什么锁？</a></li>
</ul></td>
<td>MySQL 有哪些锁？对表结构进行修改会加什么锁？<br /></td>
</tr>
<tr>
<td rowspan="4">行级锁<br /></td>
<td rowspan="4">自产资料：<ul>
<li><a href="https://xiaolincoding.com/mysql/lock/how_to_lock.html">MySQL 是怎么加锁的？</a><span style="color: inherit; background-color: rgb(247,105,100)">（</span> <span style="color: inherit; background-color: rgb(247,105,100)">校招不用花太多时间研究）</span></li>
</ul><br />视频资料：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=173&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">锁的概述_读写的并发问题</a>（P173~P180）</li>
</ul><br />书籍资料：<ul>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/25-%E5%B7%A5%E4%BD%9C%E9%9D%A2%E8%AF%95%E8%80%81%E5%A4%A7%E9%9A%BE-%E9%94%81">第25章 工作面试老大难-锁</a></li>
</ul></td>
<td rowspan="4">MyISAM 存储引擎有行级锁吗？<br />行级锁有哪些？<br />Innodb 是怎么样加行级锁的？<br /></td>
</tr>
<tr>
</tr>
<tr>
</tr>
<tr>
</tr>
<tr>
<td><br />MDL锁</td>
<td><ul>
<li><a href="https://juejin.cn/post/6844904193531052040#heading-12">加索引可能引发的事故，我们要心中有数 </a>（事故排查和解决）</li>
<li><a href="https://zq99299.github.io/mysql-tutorial/ali-new-retail/05/02.html">如何在线修改表结构？</a></li>
</ul></td>
<td>在线上增加索引，会发生什么？<br />如何安全的在线上给表增加索引？<br /></td>
</tr>
<tr>
<td>死锁<br /></td>
<td>自产资料：<ul>
<li><a href="https://xiaolincoding.com/mysql/lock/deadlock.html">MySQL 死锁了，怎么办？</a>（分析死锁）</li>
<li><a href="https://xiaolincoding.com/mysql/lock/show_lock.html">字节面试：加了什么锁，导致死锁的？</a>（分析死锁）</li>
</ul><br />博客资料：<ul>
<li><a href="https://www.toberoot.com/database/mysql/dba_mysql/tec/mysql_5.7_%E6%AD%BB%E9%94%81%E5%88%86%E6%9E%90.html">MySQL 5.7 排查死锁</a>（死锁排查）</li>
<li><a href="https://www.aneasystone.com/archives/2018/04/solving-dead-locks-four.html">解决死锁之路(终结篇) - 再见死锁 - aneasystone's blog</a>（避免死锁）</li>
</ul></td>
<td>死锁是怎么发生的？<br />发生死锁的条件有哪些？<br />怎么排查死锁问题？<br />怎么避免死锁问题？<br /></td>
</tr>
<tr>
<td>悲观锁与乐观锁</td>
<td><ul>
<li><a href="https://xie.infoq.cn/article/2085a95ad6b486d3905adc7d6">悲观锁与乐观锁的实现(详情图解)</a></li>
<li><a href="https://www.cnblogs.com/kyoner/p/11318979.html">数据库中的乐观锁与悲观锁</a></li>
</ul></td>
<td>mysql怎么实现乐观锁？</td>
</tr>
</tbody>
</table>

### 日志

<table><colgroup><col width="157"><col width="310"><col width="332"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>慢查询日志<br /></td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=135&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">慢查询日志分析、SHOW PROFILE查看SQL执行成本</a></td>
<td>慢查询日志用来找到慢 sql。</td>
</tr>
<tr>
<td> undolog 日志</td>
<td>视频资料：<a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=172&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">Undo日志的概述与写入过程</a></td>
<td>事务的原子性是怎么实现的？</td>
</tr>
<tr>
<td>binlog日志</td>
<td>视频资料：
<a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=189&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">binlog日志的参数</a><br /><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=193&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">binlog的format设置说明</a>（三种日志格式）</td>
<td>binlog 日志格式有哪些？有什么区别？<br />应用场景是什么？</td>
</tr>
<tr>
<td>redolog日志<br /></td>
<td>视频资料：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=169&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">为什么需要Redo日志</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=170&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">Redo日志的刷盘策略与过程剖析</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=171&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">写入Redo Log Buffer和Redo Log File的写入策略</a></li>
</ul></td>
<td>事务持久性是怎么实现？<br />为什么需要 redo log？<br /></td>
</tr>
<tr>
<td>三种日志分析<br /></td>
<td>自产资料：<a href="https://xiaolincoding.com/mysql/log/how_update.html">MySQL 日志：undo log、redo log、binlog 有什么用？</a><br /><br />博客资料：<ul>
<li><a href="https://juejin.cn/post/7157956679932313608">MySQL日志篇之undo-log、redo-log、bin-log.....傻傻分不清! </a></li>
</ul></td>
<td>binlog 和 redo log 有什么区别？ <br />为什么需要两阶段提交？<br />两阶段提交过程是怎么样？<br /></td>
</tr>
<tr>
<td>备份</td>
<td><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/21%20%20%E6%95%B0%E6%8D%AE%E5%BA%93%E5%A4%87%E4%BB%BD%EF%BC%9A%E5%A4%87%E4%BB%BD%E6%96%87%E4%BB%B6%E4%B9%9F%E8%A6%81%E6%A3%80%E6%9F%A5%EF%BC%81.md">数据库备份:备份文件也要检查!.md</a></td>
<td>了解数据库备份的方法</td>
</tr>
</tbody>
</table>

### 性能调优（重点）

<table><colgroup><col width="157"><col width="310"><col width="332"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>mysql 单机性能<br /></td>
<td><a href="https://support.huaweicloud.com/pwp-rds-mysql/rds_swp_mysql_09.html">MySQL 5.7 性能测试结果</a><br /></td>
<td> 4c8g 服务器，mysql 承载<ul>
<li>500 TPS （数据库每秒执行的事务数，以 COMMIT 成功次数为准）。</li>
<li>10000 QPS（数据库每秒执行的 SQL 数）</li>
</ul></td>
</tr>
<tr>
<td>explain 执行计划<br /></td>
<td>书籍资料：<ul>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/15-%E6%9F%A5%E8%AF%A2%E4%BC%98%E5%8C%96%E7%9A%84%E7%99%BE%E7%A7%91%E5%85%A8%E4%B9%A6-Explain%E8%AF%A6%E8%A7%A3%EF%BC%88%E4%B8%8A%EF%BC%89">查询优化的百科全书-Explain详解（上）</a></li>
<li><a href="https://relph1119.github.io/mysql-learning-notes/#/mysql/16-%E6%9F%A5%E8%AF%A2%E4%BC%98%E5%8C%96%E7%9A%84%E7%99%BE%E7%A7%91%E5%85%A8%E4%B9%A6-Explain%E8%AF%A6%E8%A7%A3%EF%BC%88%E4%B8%8B%EF%BC%89">第16章 查询优化的百科全书-Explain详解(下)</a></li>
</ul>
视频资料：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=136&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">136-EXPLAIN的概述与table、id字段剖析</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=137&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">137-EXPLAIN中select_type、partitions、type、possible_keys、key、key_len剖析</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=138">138-EXPLAIN中ref、rows、filtered、extra剖析</a>
</li>
</ul>官方资料：<a href="https://dev.mysql.com/doc/refman/8.0/en/explain.html">使用explain</a></td>
<td>explain 是调优常用命令，需要掌握如何分析一条 SQL 语句是否走了索引？<br />type、key、extra 这三个字段，并理解其输出字段的含义。<br /></td>
</tr>
<tr>
<td>索引调优</td>
<td><ul>
<li>书籍资料：<a href="https://juejin.cn/post/6976290766876311559">《高性能mysql第三版》</a>（看第五章）</li>
<li>博客资料：<a href="https://xiaolincoding.com/mysql/index/index_interview.html#%E4%BB%80%E4%B9%88%E6%98%AF%E7%B4%A2%E5%BC%95">索引常见面试题</a>（有什么优化索引的方法？）</li>
</ul></td>
<td>索引优化常见且重要</td>
</tr>
<tr>
<td>SQL 优化<br /></td>
<td>书籍资料：<a href="https://juejin.cn/post/6976290766876311559">《高性能mysql第三版》</a>（看第六章）<br /><br />博客资料：<ul>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/PrewwWYZuim5fmku88jcNFOTnyh"> MySQL夜市12月 23 日（SQL优化）</a> </li>
<li><a href="https://learn.lianglianglee.com/%e4%b8%93%e6%a0%8f/%e8%af%b4%e9%80%8f%e6%80%a7%e8%83%bd%e6%b5%8b%e8%af%95/19%20%20%e5%a6%82%e4%bd%95%e6%a0%b9%e6%b2%bb%e6%85%a2%20SQL%ef%bc%9f.md"> 如何根治慢 SQL?</a></li>
<li><a href="https://juejin.cn/post/7164652941159170078">SQL优化篇:如何成为一位写优质SQL语句的绝顶高手!</a></li>
<li><a href="https://mp.weixin.qq.com/s?__biz=Mzg5ODU2ODczMQ==&#x26;mid=2247499167&#x26;idx=1&#x26;sn=f6510663e93d0c7e5154ea6f6bde0fde&#x26;chksm=c0623aebf715b3fd057755f1062d4a2656160f2beaf890db6b8228dc11837d2bd17e26c42666&#x26;token=1429342161&#x26;lang=zh_CN#rd">分页性能瓶颈分析</a>（网上答案很多都是没说完的，高性能MySQL也没分析透彻）</li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E9%AB%98%E6%A5%BC%E7%9A%84%E6%80%A7%E8%83%BD%E5%B7%A5%E7%A8%8B%E5%AE%9E%E6%88%98%E8%AF%BE/16%20%E5%95%86%E5%93%81%E5%8A%A0%E5%85%A5%E8%B4%AD%E7%89%A9%E8%BD%A6%EF%BC%9ASQL%E4%BC%98%E5%8C%96%E5%92%8C%E5%8E%8B%E5%8A%9B%E5%B7%A5%E5%85%B7%E4%B8%AD%E7%9A%84%E5%8F%82%E6%95%B0%E5%88%86%E6%9E%90.md">SQL优化和压力工具中的参数分析</a></li>
</ul><br />视频资料：<ul>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=143&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">143-外连接与内连接的查询优化</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=145&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">145-子查询优化与排序优化</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=146&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">146-GROUP BY优化、分页查询优化</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=147&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">147-覆盖索引的使用</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=148&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">148-索引条件下推(ICP)</a></li>
<li><a href="https://www.bilibili.com/video/BV1iq4y1u7vj?p=149&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">149-其他查询优化策略</a>
</li>
</ul></td>
<td>如何定位一条查询慢 SQL 语句？<br />如何对慢查询 SQL 语句进行优化？<br />分页场景如何优化？<br /></td>
</tr>
<tr>
<td>连接池</td>
<td><ul>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/NGxMwuRy2iFsb3kfGACcWSzinud"> 连接池优化</a>（文档+视频）</li>
<li><a href="https://dunwu.github.io/java-tutorial/pages/be5227/#%E4%BB%80%E4%B9%88%E6%98%AF%E6%95%B0%E6%8D%AE%E5%BA%93%E8%BF%9E%E6%8E%A5%E6%B1%A0">数据库连接池</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/Java%20%E4%B8%9A%E5%8A%A1%E5%BC%80%E5%8F%91%E5%B8%B8%E8%A7%81%E9%94%99%E8%AF%AF%20100%20%E4%BE%8B/04%20%E8%BF%9E%E6%8E%A5%E6%B1%A0%EF%BC%9A%E5%88%AB%E8%AE%A9%E8%BF%9E%E6%8E%A5%E6%B1%A0%E5%B8%AE%E4%BA%86%E5%80%92%E5%BF%99.md">连接池：别让连接池帮了倒忙</a></li>
</ul><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/Java%20%E4%B8%9A%E5%8A%A1%E5%BC%80%E5%8F%91%E5%B8%B8%E8%A7%81%E9%94%99%E8%AF%AF%20100%20%E4%BE%8B/04%20%E8%BF%9E%E6%8E%A5%E6%B1%A0%EF%BC%9A%E5%88%AB%E8%AE%A9%E8%BF%9E%E6%8E%A5%E6%B1%A0%E5%B8%AE%E4%BA%86%E5%80%92%E5%BF%99.md"> </a></td>
<td>理解连接池是什么即可。假设连接池大小是100，核心思想：
- 100以内的请求过来，就复用已有的连接
- 假设100个连接都有事儿要做了，那多出来的新请求，就是短链接（go 框架短连接，Java 则是阻塞等待）</td>
</tr>
<tr>
<td>MySQL 性能优化</td>
<td><ul>
<li><a href="https://juejin.cn/post/7163894728201601060#heading-12">MySQL调优篇:单机数据库如何在高并发场景下健步如飞?</a></li>
<li><a href="https://learn.lianglianglee.com/%e4%b8%93%e6%a0%8f/%e8%af%b4%e9%80%8f%e6%80%a7%e8%83%bd%e6%b5%8b%e8%af%95/18%20%20%e5%a6%82%e4%bd%95%e6%89%8d%e8%83%bd%e4%bc%98%e5%8c%96%20MySQL%20%e6%80%a7%e8%83%bd%ef%bc%9f.md">如何才能优化 MySQL 性能?</a></li>
<li><a href="https://www.ifanatic.cn/interviews/21%E6%95%B0%E6%8D%AE%E5%BA%93%E7%BB%BC%E5%90%88%E5%BA%94%E7%94%A8%E6%80%8E%E4%B9%88%E4%BF%9D%E8%AF%81%E6%95%B0%E6%8D%AE%E5%BA%93%E7%9A%84%E9%AB%98%E5%8F%AF%E7%94%A8%E9%AB%98%E6%80%A7%E8%83%BD/">数据库综合应用：怎么保证数据库的高可用、高性能？</a></li>
</ul></td>
<td>对 MySQL 性能调优有整体的认识，而不局限于 SQL 调优。<br /></td>
</tr>
</tbody>
</table>

### 面试题

| 基础 | [MySQL基础](https://mp.weixin.qq.com/s?__biz=Mzg5ODU2ODczMQ==\&mid=2247486128\&idx=1\&sn=afbd3ca37f4727db9d32460f98e73d5a\&chksm=c061cdc4f71644d228cad54d6a8395e27a46a9540f219a4f3776e5aa023608d131f9ec70b687#rd)（牛哥自产）                                              | 一般用于初步摸底          |
| -- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| 原理 | [MySQL原理](https://mp.weixin.qq.com/s?__biz=Mzg5ODU2ODczMQ==\&mid=2247487888\&idx=1\&sn=973635eeaf7d1916e62bbceda72d27bd\&chksm=c061d6e4f7165ff271ee4bfc71de630c6538802b1d49c747bc0eb0be9264ae7619ed0648c47c#rd)（牛哥自产）                                              | 面试重点，会扣得比较细       |
| 性能 | [MySQL性能](https://mp.weixin.qq.com/s?__biz=Mzg5ODU2ODczMQ==\&mid=2247494731\&idx=1\&sn=e1bb64dd33c008cf46d5995044589228\&chksm=c0622b3ff715a229ef1831b468eb47b07aabd1edfb87637bf5c45408418dd37e3cf4ee9eca2e\&scene=178\&cur_album_id=2225658380164055048#rd)（牛哥自产） | 面试重点，特别是索引调优、分页调优 |



## MySQL 高可用

这一部分，主要学习 MySQL 主从复制、分库分表、高可用、分布式等等，校招需要简单了解（了解主从复制和分库分表就差不多了），社招需要加强学习。

<table><colgroup><col width="110"><col width="372"><col width="361"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>读写分离<br /></td>
<td><ul>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E6%9E%B6%E6%9E%84%E8%AE%BE%E8%AE%A1%E9%9D%A2%E8%AF%95%E7%B2%BE%E8%AE%B2/11%20%20%E8%AF%BB%E5%A4%9A%E5%86%99%E5%B0%91%EF%BC%9AMySQL%20%E5%A6%82%E4%BD%95%E4%BC%98%E5%8C%96%E6%95%B0%E6%8D%AE%E6%9F%A5%E8%AF%A2%E6%96%B9%E6%A1%88%EF%BC%9F.md">读多写少:MySQL 如何优化数据查询方案?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E5%88%86%E5%B8%83%E5%BC%8F%E6%8A%80%E6%9C%AF%E5%8E%9F%E7%90%86%E4%B8%8E%E5%AE%9E%E6%88%9845%E8%AE%B2-%E5%AE%8C/23%20%E8%AF%BB%E5%86%99%E5%88%86%E7%A6%BB%E5%A6%82%E4%BD%95%E5%9C%A8%E4%B8%9A%E5%8A%A1%E4%B8%AD%E8%90%BD%E5%9C%B0%EF%BC%9F.md">读写分离如何在业务中落地?.md</a></li>
<li><a href="https://juejin.cn/post/7269953746851266620">MySQL 主从复制 —— 全同步复制、异步复制、半同步复制 </a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/15%20%20MySQL%20%E5%A4%8D%E5%88%B6%EF%BC%9A%E6%9C%80%E7%AE%80%E5%8D%95%E4%B9%9F%E6%9C%80%E5%AE%B9%E6%98%93%E9%85%8D%E7%BD%AE%E5%87%BA%E9%94%99.md">MySQL 复制:最简单也最容易配置出错.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/16%20%20%E8%AF%BB%E5%86%99%E5%88%86%E7%A6%BB%E8%AE%BE%E8%AE%A1%EF%BC%9A%E5%A4%8D%E5%88%B6%E5%BB%B6%E8%BF%9F%EF%BC%9F%E5%85%B6%E5%AE%9E%E6%98%AF%E4%BD%A0%E7%94%A8%E9%94%99%E4%BA%86.md">读写分离设计:复制延迟?其实是你用错了.md</a></li>
</ul></td>
<td>读写分离是什么?什么场景下需要读写分离？<br />Mysql 提供了哪些复制模式？分别对应的应用场景是什么？<br />怎么避免主从复制延迟？<br />怎么进行读写分离？</td>
</tr>
<tr>
<td>分库分表<br /></td>
<td>分库分表常见解决方案：<ul>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/FCnewo2nLiOUMNkXY5pcUCa4n7c"> 分库分表</a>（训练营视频会议：第一期）</li>
<li><a href="https://zq99299.github.io/note-book/back-end-storage/03/01.html">MySQL 存储海量数据的最后一招：分库分表 </a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E6%9E%B6%E6%9E%84%E8%AE%BE%E8%AE%A1%E9%9D%A2%E8%AF%95%E7%B2%BE%E8%AE%B2/12%20%20%E5%86%99%E5%A4%9A%E8%AF%BB%E5%B0%91%EF%BC%9AMySQL%20%E5%A6%82%E4%BD%95%E4%BC%98%E5%8C%96%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%96%B9%E6%A1%88%EF%BC%9F.md">写多读少:MySQL 如何优化数据存储方案?.md</a></li>
<li><a href="https://www.51cto.com/article/709614.html">再有人问你什么是分库分表，直接把这篇文章发给他-分库分表的规则</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/23%20%20%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93%E8%A1%A8%E7%BB%93%E6%9E%84%E8%AE%BE%E8%AE%A1%EF%BC%9A%E5%A6%82%E4%BD%95%E6%AD%A3%E7%A1%AE%E5%9C%B0%E5%B0%86%E6%95%B0%E6%8D%AE%E5%88%86%E7%89%87%EF%BC%9F.md">分布式数据库表结构设计:如何正确地将数据分片?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/24%20%20%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93%E7%B4%A2%E5%BC%95%E8%AE%BE%E8%AE%A1%EF%BC%9A%E4%BA%8C%E7%BA%A7%E7%B4%A2%E5%BC%95%E3%80%81%E5%85%A8%E5%B1%80%E7%B4%A2%E5%BC%95%E7%9A%84%E6%9C%80%E4%BD%B3%E8%AE%BE%E8%AE%A1%E5%AE%9E%E8%B7%B5.md">分布式数据库索引设计:二级索引、全局索引的最佳设计实践.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/25%20%20%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93%E6%9E%B6%E6%9E%84%E9%80%89%E5%9E%8B%EF%BC%9A%E5%88%86%E5%BA%93%E5%88%86%E8%A1%A8%20or%20%E4%B8%AD%E9%97%B4%E4%BB%B6%20%EF%BC%9F.md">分布式数据库架构选型:分库分表 or 中间件 ?.md</a></li>
</ul>分库分表带来的问题：<ul>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/FCnewo2nLiOUMNkXY5pcUCa4n7c"> 分库分表</a>（训练营视频会议：第二期）</li>
<li><a href="https://freegeektime.com/100028001/118384/">什么时候需要分表分库?.md</a></li>
</ul>实际案例：<ul>
<li><a href="https://tech.meituan.com/2016/11/18/dianping-order-db-sharding.html">大众点评订单系统分库分表实践</a></li>
<li><a href="https://www.bilibili.com/video/BV1zM4m1m7gk/?spm_id_from=333.999.list.card_archive.click">美团订单存储VS淘宝订单存储-第一集美团</a></li>
<li><a href="https://www.bilibili.com/video/BV19E421P7Nd/?spm_id_from=333.999.list.card_archive.click">美团订单存储VS淘宝订单存储-第二集淘宝篇</a></li>
<li><a href="https://www.bilibili.com/video/BV1pZ421M7Xo?spm_id_from=333.788.recommend_more_video.-1&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">架构设计-美团订单存储VS淘宝订单存储-第三集-事务篇</a></li>
<li><a href="https://www.bilibili.com/video/BV1U4421Q77M?spm_id_from=333.788.recommend_more_video.-1&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">架构设计-美团订单存储VS淘宝订单存储-第四集-水平扩容</a></li>
<li><a href="https://www.bilibili.com/video/BV1tf421q7so?spm_id_from=333.788.recommend_more_video.-1&#x26;vd_source=894a223b85ae44e61e16dcd1a7356db0">架构设计-美团订单存储VS淘宝订单存储-大结局-对我有啥用</a></li>
</ul></td>
<td>MySQL作为单机数据库，随着请求量和数据量的增加一定会走向分库分表之路。<br />什么场景需要分库分表？<br />分库解决什么问题？分表解决什么问题？<br />分库分表后会产生什么问题？<br />分库分表有什么样的分表方式？分片键怎么选择？<br /><br /></td>
</tr>
<tr>
<td>分布式 ID<br /></td>
<td><ul>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/ACdSwKIQ1iae6tkUQlkcY4T4nug"> 分布式ID优化</a>（训练营专项夜市）</li>
<li><a href="https://zhuanlan.zhihu.com/p/534893180">分布式唯一 ID 生成方案浅谈</a></li>
<li><a href="https://learn.lianglianglee.com/%e4%b8%93%e6%a0%8f/%e9%ab%98%e5%b9%b6%e5%8f%91%e7%b3%bb%e7%bb%9f%e8%ae%be%e8%ae%a140%e9%97%ae/10%20%20%e5%8f%91%e5%8f%b7%e5%99%a8%ef%bc%9a%e5%a6%82%e4%bd%95%e4%bf%9d%e8%af%81%e5%88%86%e5%ba%93%e5%88%86%e8%a1%a8%e5%90%8eID%e7%9a%84%e5%85%a8%e5%b1%80%e5%94%af%e4%b8%80%e6%80%a7%ef%bc%9f.md">发号器:如何保证分库分表后ID的全局唯一性?</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E5%88%86%E5%B8%83%E5%BC%8F%E6%8A%80%E6%9C%AF%E5%8E%9F%E7%90%86%E4%B8%8E%E5%AE%9E%E6%88%9845%E8%AE%B2-%E5%AE%8C/25%20%E5%AD%98%E5%82%A8%E6%8B%86%E5%88%86%E5%90%8E%EF%BC%8C%E5%A6%82%E4%BD%95%E8%A7%A3%E5%86%B3%E5%94%AF%E4%B8%80%E4%B8%BB%E9%94%AE%E9%97%AE%E9%A2%98%EF%BC%9F.md">存储拆分后，如何解决唯一主键问题?.md</a></li>
<li><a href="https://tech.meituan.com/2017/04/21/mt-leaf.html">Leaf——美团点评分布式ID生成系统</a></li>
</ul></td>
<td>分库分表后，如何保证记录id全局唯一？<br />发生时间回拨，怎么办？<br /></td>
</tr>
<tr>
<td>分布式锁<br /></td>
<td><ul>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/HOrdwMqsTi67ujkZFICcdRpwnCG"> 分布式锁优化</a>（训练营专项夜市：mysql、redis、zk、etcd 分布式锁对比）</li>
<li><a href="https://learn.lianglianglee.com/%e4%b8%93%e6%a0%8f/%e5%88%86%e5%b8%83%e5%bc%8f%e6%8a%80%e6%9c%af%e5%8e%9f%e7%90%86%e4%b8%8e%e7%ae%97%e6%b3%95%e8%a7%a3%e6%9e%90/07%20%e5%88%86%e5%b8%83%e5%bc%8f%e9%94%81%ef%bc%9a%e5%85%b3%e9%94%ae%e9%87%8d%e5%9c%b0%ef%bc%8c%e9%9d%9e%e8%af%b7%e5%8b%bf%e5%85%a5.md">分布式锁:关键重地，非请勿入</a></li>
<li><a href="https://freegeektime.com/100028001/125983/">如何设计更优的分布式锁?</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E6%9E%B6%E6%9E%84%E8%AE%BE%E8%AE%A1%E9%9D%A2%E8%AF%95%E7%B2%BE%E8%AE%B2/06%20%20%E5%88%86%E5%B8%83%E5%BC%8F%E7%B3%BB%E7%BB%9F%E4%B8%AD%EF%BC%8C%E5%A6%82%E4%BD%95%E5%9B%9E%E7%AD%94%E9%94%81%E7%9A%84%E5%AE%9E%E7%8E%B0%E5%8E%9F%E7%90%86%EF%BC%9F.md">分布式系统中，如何回答锁的实现原理?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/ZooKeeper%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90%E4%B8%8E%E5%AE%9E%E6%88%98-%E5%AE%8C/21%20ZooKeeper%20%E5%88%86%E5%B8%83%E5%BC%8F%E9%94%81%EF%BC%9A%E5%AE%9E%E7%8E%B0%E5%92%8C%E5%8E%9F%E7%90%86%E8%A7%A3%E6%9E%90.md">ZooKeeper 分布式锁:实现和原理解析</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/etcd%E5%AE%9E%E6%88%98%E8%AF%BE/21%20%E5%88%86%E5%B8%83%E5%BC%8F%E9%94%81%EF%BC%9A%E4%B8%BA%E4%BB%80%E4%B9%88%E5%9F%BA%E4%BA%8Eetcd%E5%AE%9E%E7%8E%B0%E5%88%86%E5%B8%83%E5%BC%8F%E9%94%81%E6%AF%94Redis%E9%94%81%E6%9B%B4%E5%AE%89%E5%85%A8%EF%BC%9F.md">分布式锁:为什么基于etcd实现分布式锁比Redis锁更安全?</a></li>
</ul></td>
<td>jvm 锁和分布式锁有什么区别？<br />什么时候需要用到分布式锁？<br />怎么用 redis 实现分布式锁？<br />Redis实现分布式锁有哪些缺陷？<br />除了redis实现分布式锁，还有什么其他方式也能实现？<br />redis 和zookeeper实现分布式锁的区别？<br />如何用MySQL实现分布式锁？有什么优缺点？</td>
</tr>
<tr>
<td>数据迁移<br /></td>
<td><ul>
<li><a href="https://zq99299.github.io/note-book/back-end-storage/03/06.html">如何在不停机的情况下，安全地更换数据库？</a></li>
<li><a href="http://121.43.36.222:5244/%E8%B5%84%E6%BA%90/14-%E6%9E%81%E5%AE%A2%E6%97%B6%E9%97%B4/%E4%B8%93%E6%A0%8F%E8%AF%BE/2024/230%E5%90%8E%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%9A%84%E9%AB%98%E9%98%B6%E9%9D%A2%E7%BB%8F/15%EF%BD%9C%E6%95%B0%E6%8D%AE%E8%BF%81%E7%A7%BB%EF%BC%9A%E5%A6%82%E4%BD%95%E5%9C%A8%E4%B8%8D%E5%81%9C%E6%9C%BA%E7%9A%84%E6%83%85%E5%86%B5%E4%B8%8B%E4%BF%9D%E8%AF%81%E8%BF%81%E7%A7%BB%E6%95%B0%E6%8D%AE%E7%9A%84%E4%B8%80%E8%87%B4%E6%80%A7%EF%BC%9F.md">数据迁移：如何在不停机的情况下保证迁移数据的一致性？</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E9%AB%98%E5%B9%B6%E5%8F%91%E7%B3%BB%E7%BB%9F%E8%AE%BE%E8%AE%A140%E9%97%AE/%E5%8A%A0%E9%A4%90%20%20%E6%95%B0%E6%8D%AE%E7%9A%84%E8%BF%81%E7%A7%BB%E5%BA%94%E8%AF%A5%E5%A6%82%E4%BD%95%E5%81%9A%EF%BC%9F.md">加餐 数据的迁移应该如何做?</a></li>
<li><a href="https://dbaplus.cn/news-73-5230-1.html">手把手实例教学，原来数据平滑迁移这么简单 - 大数据 </a></li>
</ul></td>
<td>如何在线上不影响业务的情况下，进行数据迁移？<br /></td>
</tr>
<tr>
<td>分布式事务<br /></td>
<td><ul>
<li><a href="https://learn.lianglianglee.com/%e4%b8%93%e6%a0%8f/%e5%88%86%e5%b8%83%e5%bc%8f%e6%8a%80%e6%9c%af%e5%8e%9f%e7%90%86%e4%b8%8e%e7%ae%97%e6%b3%95%e8%a7%a3%e6%9e%90/06%20%e5%88%86%e5%b8%83%e5%bc%8f%e4%ba%8b%e5%8a%a1%ef%bc%9aAll%20or%20nothing.md">分布式事务:All or nothing</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E9%AB%98%E5%B9%B6%E5%8F%91%E7%B3%BB%E7%BB%9F%E5%AE%9E%E6%88%98%E8%AF%BE/09%20%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1%EF%BC%9A%E5%A4%9A%E6%9C%8D%E5%8A%A1%E7%9A%842PC%E3%80%81TCC%E9%83%BD%E6%98%AF%E6%80%8E%E4%B9%88%E5%AE%9E%E7%8E%B0%E7%9A%84%EF%BC%9F.md">分布式事务:多服务的2PC、TCC都是怎么实现的?</a></li>
<li><a href="https://zq99299.github.io/note-book/back-end-storage/01/05.html">分布式事务：如何保证多个系统间的数据是一致的？</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E5%88%86%E5%B8%83%E5%BC%8F%E6%8A%80%E6%9C%AF%E5%8E%9F%E7%90%86%E4%B8%8E%E5%AE%9E%E6%88%9845%E8%AE%B2-%E5%AE%8C/07%20%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1%E6%9C%89%E5%93%AA%E4%BA%9B%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88%EF%BC%9F.md">分布式事务有哪些解决方案?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E5%88%86%E5%B8%83%E5%BC%8F%E6%8A%80%E6%9C%AF%E5%8E%9F%E7%90%86%E4%B8%8E%E5%AE%9E%E6%88%9845%E8%AE%B2-%E5%AE%8C/08%20%E5%AF%B9%E6%AF%94%E4%B8%A4%E9%98%B6%E6%AE%B5%E6%8F%90%E4%BA%A4%EF%BC%8C%E4%B8%89%E9%98%B6%E6%AE%B5%E5%8D%8F%E8%AE%AE%E6%9C%89%E5%93%AA%E4%BA%9B%E6%94%B9%E8%BF%9B%EF%BC%9F.md">对比两阶段提交，三阶段协议有哪些改进?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E5%88%86%E5%B8%83%E5%BC%8F%E6%8A%80%E6%9C%AF%E5%8E%9F%E7%90%86%E4%B8%8E%E5%AE%9E%E6%88%9845%E8%AE%B2-%E5%AE%8C/09%20MySQL%20%E6%95%B0%E6%8D%AE%E5%BA%93%E5%A6%82%E4%BD%95%E5%AE%9E%E7%8E%B0%20XA%20%E8%A7%84%E8%8C%83%EF%BC%9F.md">MySQL 数据库如何实现 XA 规范?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E5%88%86%E5%B8%83%E5%BC%8F%E6%8A%80%E6%9C%AF%E5%8E%9F%E7%90%86%E4%B8%8E%E5%AE%9E%E6%88%9845%E8%AE%B2-%E5%AE%8C/10%20%E5%A6%82%E4%BD%95%E5%9C%A8%E4%B8%9A%E5%8A%A1%E4%B8%AD%E4%BD%93%E7%8E%B0%20TCC%20%E4%BA%8B%E5%8A%A1%E6%A8%A1%E5%9E%8B%EF%BC%9F.md">如何在业务中体现 TCC 事务模型?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E5%91%A8%E5%BF%97%E6%98%8E%E7%9A%84%E6%9E%B6%E6%9E%84%E8%AF%BE/15%20_%20%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1%E4%B9%8BTCC%E4%B8%8ESAGA.md">分布式事务之TCC与SAGA</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/%E6%9E%B6%E6%9E%84%E8%AE%BE%E8%AE%A1%E9%9D%A2%E8%AF%95%E7%B2%BE%E8%AE%B2/05%20%20%E6%B5%B7%E9%87%8F%E5%B9%B6%E5%8F%91%E5%9C%BA%E6%99%AF%E4%B8%8B%EF%BC%8C%E5%A6%82%E4%BD%95%E5%9B%9E%E7%AD%94%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1%E4%B8%80%E8%87%B4%E6%80%A7%E9%97%AE%E9%A2%98%EF%BC%9F.md">海量并发场景下，如何回答分布式事务一致性问题?.md</a></li>
<li><a href="https://segmentfault.com/a/1190000040321750">分布式事务最经典的七种解决方案</a>（方案汇总）</li>
</ul></td>
<td>了解什么是分布式事务？<br />有哪些分布式解决方案？<br />MySQL 怎么实现分布式事务？<br />哪个方案比较容易落地？<br /></td>
</tr>
<tr>
<td>高可用<br /></td>
<td><ul>
<li><a href="https://www.cnblogs.com/ricklz/p/17335755.html">MySQL 中常见的几种高可用架构部署方案</a></li>
<li><a href="https://zq99299.github.io/note-book/back-end-storage/01/07.html">MySQL HA：如何将「删库跑路」的损失降到最低？</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/17%20%20%E9%AB%98%E5%8F%AF%E7%94%A8%E8%AE%BE%E8%AE%A1%EF%BC%9A%E4%BD%A0%E6%80%8E%E4%B9%88%E6%B4%BB%E7%94%A8%E4%B8%89%E5%A4%A7%E6%9E%B6%E6%9E%84%E6%96%B9%E6%A1%88%EF%BC%9F.md">高可用设计:你怎么活用三大架构方案?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/19%20%20%E9%AB%98%E5%8F%AF%E7%94%A8%E5%A5%97%E4%BB%B6%EF%BC%9A%E9%80%89%E6%8B%A9%E8%BF%99%E4%B9%88%E5%A4%9A%EF%BC%8C%E4%BD%A0%E8%AF%A5%E5%A6%82%E4%BD%95%E9%80%89%EF%BC%9F.md">高可用套件:选择这么多，你该如何选?.md</a>
<a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/20%20%20InnoDB%20Cluster%EF%BC%9A%E6%94%B9%E5%8F%98%E5%8E%86%E5%8F%B2%E7%9A%84%E6%96%B0%E4%BA%A7%E5%93%81.md">InnoDB Cluster:改变历史的新产品.md</a>（MySQL多主架构）</li>
</ul></td>
<td>怎么保证mysql高可用?<br />主从复制架构中，主库挂了怎么办？<br /></td>
</tr>
<tr>
<td>分布式数据库<br /></td>
<td><ul>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/22%20%20%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93%E6%9E%B6%E6%9E%84%EF%BC%9A%E5%BD%BB%E5%BA%95%E7%90%86%E8%A7%A3%E4%BB%80%E4%B9%88%E5%8F%AB%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93.md">分布式数据库架构:彻底理解什么叫分布式数据库.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/23%20%20%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93%E8%A1%A8%E7%BB%93%E6%9E%84%E8%AE%BE%E8%AE%A1%EF%BC%9A%E5%A6%82%E4%BD%95%E6%AD%A3%E7%A1%AE%E5%9C%B0%E5%B0%86%E6%95%B0%E6%8D%AE%E5%88%86%E7%89%87%EF%BC%9F.md">分布式数据库表结构设计:如何正确地将数据分片?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/24%20%20%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93%E7%B4%A2%E5%BC%95%E8%AE%BE%E8%AE%A1%EF%BC%9A%E4%BA%8C%E7%BA%A7%E7%B4%A2%E5%BC%95%E3%80%81%E5%85%A8%E5%B1%80%E7%B4%A2%E5%BC%95%E7%9A%84%E6%9C%80%E4%BD%B3%E8%AE%BE%E8%AE%A1%E5%AE%9E%E8%B7%B5.md">分布式数据库索引设计:二级索引、全局索引的最佳设计实践.md</a></li>
<li><a href="https://learn.lianglianglee.com/%E4%B8%93%E6%A0%8F/MySQL%E5%AE%9E%E6%88%98%E5%AE%9D%E5%85%B8/25%20%20%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93%E6%9E%B6%E6%9E%84%E9%80%89%E5%9E%8B%EF%BC%9A%E5%88%86%E5%BA%93%E5%88%86%E8%A1%A8%20or%20%E4%B8%AD%E9%97%B4%E4%BB%B6%20%EF%BC%9F.md">分布式数据库架构选型:分库分表 or 中间件 ?.md</a></li>
<li><a href="https://learn.lianglianglee.com/%e4%b8%93%e6%a0%8f/MySQL%e5%ae%9e%e6%88%98%e5%ae%9d%e5%85%b8/26%20%20%e5%88%86%e5%b8%83%e5%bc%8f%e8%ae%be%e8%ae%a1%e4%b9%8b%e7%a6%85%ef%bc%9a%e5%85%a8%e9%93%be%e8%b7%af%e7%9a%84%e6%9d%a1%e5%b8%a6%e5%8c%96%e8%ae%be%e8%ae%a1.md">分布式设计之禅:全链路的条带化设计</a></li>
<li><a href="https://learn.lianglianglee.com/%e4%b8%93%e6%a0%8f/MySQL%e5%ae%9e%e6%88%98%e5%ae%9d%e5%85%b8/27%20%20%e5%88%86%e5%b8%83%e5%bc%8f%e4%ba%8b%e5%8a%a1%ef%bc%9a%e6%88%91%e4%bb%ac%e5%88%b0%e5%ba%95%e8%a6%81%e4%b8%8d%e8%a6%81%e4%bd%bf%e7%94%a8%202PC%ef%bc%9f.md">分布式事务:我们到底要不要使用 2PC?</a></li>
</ul></td>
<td>什么是分布式数据库？<br />选择什么字段进行分片？<br />如何保证唯一键全局唯一？<br />了解有哪些开源的分布式数据库中间件？<br /></td>
</tr>
<tr>
<td>面试题</td>
<td><a href="https://mp.weixin.qq.com/s?__biz=Mzg5ODU2ODczMQ==&#x26;mid=2247488871&#x26;idx=1&#x26;sn=92e3da01594a987cb78b24332101c464&#x26;chksm=c061d213f7165b052ed42e0f67cc4c852a10d533a880d24d1bbcaff4adc5f21805f998707415#rd">MySQL容灾</a>（牛哥自产，这块对校招同学而言，只需要理解基础概念，考察较少）</td>
<td>主从复制是面试重点，其它更高级的容灾是拔高项</td>
</tr>
</tbody>
</table>

## 数据库表设计

<table><colgroup><col width="100"><col width="382"><col width="363"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>设计规范<br /></td>
<td><ul>
<li><a href="https://pdai.tech/md/db/sql/sql-db-theory-design.html">关系型数据库设计流程</a></li>
<li><a href="https://www.cnblogs.com/ahu-lichang/p/10899747.html">数据库范式</a></li>
</ul></td>
<td>了解数据库设计原则，设计流程，设计范式<br /></td>
</tr>
<tr>
<td>设计原则</td>
<td><ul>
<li><a href="https://www.cnblogs.com/better-farther-world2099/articles/17212891.html">21个设计MySQL数据库表的经验准则 </a></li>
<li><a href="https://mp.weixin.qq.com/s/WOf2scX0u2XNYAhEncha5g">看了我常用的数据库设计技巧，同事们都开始悄悄模仿……</a></li>
</ul></td>
<td>常见的数据库设计原则</td>
</tr>
<tr>
<td>反范式设计</td>
<td><ul>
<li><a href="https://cloud.tencent.com/developer/article/1605512">何谓“反范式化”？</a></li>
<li><a href="https://segmentfault.com/a/1190000040889773">反范式设计实践</a></li>
</ul></td>
<td>了解反范式设计</td>
</tr>
</tbody>
</table>

# 面试题（重要）

<table><colgroup><col width="176"><col width="306"><col width="329"></colgroup>
<thead>
<tr>
<th>内容</th>
<th>资料</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>专项题库练习题<br /></td>
<td><ul>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/wikcnuH4jbuv6TaHcCl7RCbuPtc"> MySQL 专项题库（无答案）</a> </li>
</ul></td>
<td>学完mysql学习指引后，可以做一下题库，检验学习效果</td>
</tr>
<tr>
<td>面试题</td>
<td><ul>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/wikcnGHC6ySX9qYhlCvEXKWvMyb"> MySQL面试题库</a> （答案版本）</li>
<li><a href="https://ls8sck0zrg.feishu.cn/wiki/MaRiwPFqMiaBCvkJfYVcmM8JnLc"> SQL面试题题库</a> </li>
</ul></td>
<td>短期有面试需要突击mysql的，可以刷这个面试题<br /></td>
</tr>
</tbody>
</table>

