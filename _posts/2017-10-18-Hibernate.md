---
layout: post
title:  Hibernate
date:  2017-10-18 09:29:52 +0800
categories: [Tech]
excerpt: 学习Hibernate方法
tags:
  - CN
  - java
  - 框架
---
![enter description here][1]

![enter description here][2]

![enter description here][3]

![enter description here][4]

![enter description here][5]

![enter description here][6]

![enter description here][7]

![enter description here][8]

![enter description here][9]

![enter description here][10]

![enter description here][11]
### 测试框架
```java
public class studentTest {

	private SessionFactory sessionFactory;
	private Session session;
	private Transaction transaction;

	@Before
	public void init() {
		// 创建配置对象
		Configuration config = new Configuration().configure();
		// 获得服务注册对象
		ServiceRegistry serviceRegistry = new ServiceRegistryBuilder().applySettings(config.getProperties())
				.buildServiceRegistry();
		// 创建工厂对象
		sessionFactory = config.buildSessionFactory(serviceRegistry);
		// 会话对象
		session = sessionFactory.openSession();
		// 开启事物
		transaction = session.beginTransaction();
	}

	@After
	public void destory() {
		// 提交事物
		transaction.commit();
		// 关闭Session
		session.close();
		// 关闭工厂对象
		sessionFactory.close();
	}

	@Test
	public void testSaveStudent() {
		// 生成学生对象
		student s = new student(1, "张三丰", "男", new Date(), "武当山");
		// 保存对象到数据库
		session.save(s);
	}
}
```
![enter description here][12]

### 配置文档常用配置
![enter description here][13]
创建表时加前缀
![enter description here][14]

### session

![enter description here][15]

![enter description here][16]

![enter description here][17]

getCurrentSession用的时候需要配置xml文档

![enter description here][18]

### 事物transaction

![enter description here][19]

![enter description here][20]

自动提交

![enter description here][21]

### hbm配置文档
![enter description here][22]

![enter description here][23]

![enter description here][24]

### 主键

![enter description here][25]

### 映射

![enter description here][26]

![enter description here][27]

![enter description here][28]

### 对象类型

![enter description here][29]

![enter description here][30]

![enter description here][31]

![enter description here][32]

![enter description here][33]

### 组件属性
对象里面包含对象

![enter description here][34]

![enter description here][35]

![enter description here][36]

![enter description here][37]

### 一对多映射
![enter description here][38]


  [1]: ./images/1504168041446.jpg "1504168041446.jpg"
  [2]: ./images/1504168241011.jpg "1504168241011.jpg"
  [3]: ./images/1504168359457.jpg "1504168359457.jpg"
  [4]: ./images/1504168446581.jpg "1504168446581.jpg"
  [5]: ./images/1504168480314.jpg "1504168480314.jpg"
  [6]: ./images/1504168582139.jpg "1504168582139.jpg"
  [7]: ./images/1504512041919.jpg "1504512041919.jpg"
  [8]: ./images/1504512065548.jpg "1504512065548.jpg"
  [9]: ./images/1504512376179.jpg "1504512376179.jpg"
  [10]: ./images/1504512931030.jpg "1504512931030.jpg"
  [11]: ./images/1504513105880.jpg "1504513105880.jpg"
  [12]: ./images/1504513757023.jpg "1504513757023.jpg"
  [13]: ./images/1504515087826.jpg "1504515087826.jpg"
  [14]: ./images/1504515494907.jpg "1504515494907.jpg"
  [15]: ./images/1504515607099.jpg "1504515607099.jpg"
  [16]: ./images/1504515764648.jpg "1504515764648.jpg"
  [17]: ./images/1504516274839.jpg "1504516274839.jpg"
  [18]: ./images/1504516697655.jpg "1504516697655.jpg"
  [19]: ./images/1504515812422.jpg "1504515812422.jpg"
  [20]: ./images/1504515835216.jpg "1504515835216.jpg"
  [21]: ./images/1504516137305.jpg "1504516137305.jpg"
  [22]: ./images/1504517263018.jpg "1504517263018.jpg"
  [23]: ./images/1504517474765.jpg "1504517474765.jpg"
  [24]: ./images/1504517516134.jpg "1504517516134.jpg"
  [25]: ./images/1504678873030.jpg "1504678873030.jpg"
  [26]: ./images/1504686422240.jpg "1504686422240.jpg"
  [27]: ./images/1504686484327.jpg "1504686484327.jpg"
  [28]: ./images/1504686753420.jpg "1504686753420.jpg"
  [29]: ./images/1504687229188.jpg "1504687229188.jpg"
  [30]: ./images/1504687274471.jpg "1504687274471.jpg"
  [31]: ./images/1504688489842.jpg "1504688489842.jpg"
  [32]: ./images/1504688725136.jpg "1504688725136.jpg"
  [33]: ./images/1504690129418.jpg "1504690129418.jpg"
  [34]: ./images/1504690237299.jpg "1504690237299.jpg"
  [35]: ./images/1504690558286.jpg "1504690558286.jpg"
  [36]: ./images/1507712280434.jpg "1507712280434.jpg"
  [37]: ./images/1507712364509.jpg "1507712364509.jpg"
  [38]: ./images/1507712655122.jpg "1507712655122.jpg"