# JDBC

![image-20220810132246621](JDBC连接池.assets/image-20220810132246621.png)

## 获取数据库连接方式

![image-20220810133751967](JDBC连接池.assets/image-20220810133751967.png)

![image-20220810133848354](JDBC连接池.assets/image-20220810133848354.png)

![image-20220810133957140](JDBC连接池.assets/image-20220810133957140.png)

![image-20220810134007863](JDBC连接池.assets/image-20220810134007863.png)

![image-20220810134056288](JDBC连接池.assets/image-20220810134056288.png)

## resultset

![image-20220810135032933](JDBC连接池.assets/image-20220810135032933.png)

![image-20220810135735444](JDBC连接池.assets/image-20220810135735444.png)

## statement

![image-20220810140050638](JDBC连接池.assets/image-20220810140050638.png)

## 预处理

![image-20220810142006084](JDBC连接池.assets/image-20220810142006084.png)

![image-20220810142045658](JDBC连接池.assets/image-20220810142045658.png)

## JDBC API

![image-20220811081022223](JDBC连接池.assets/image-20220811081022223.png)

![image-20220811081528014](JDBC连接池.assets/image-20220811081528014.png)

### DriverManager

```text

2.获取连接
static Connection
getconnection(string url,string user,string password)
参数
1.url:连接路径
语法：jdbc:mysql://ip地址（域名）端口号/数据库名称?参数键值对1&参数键值对2.
示例：jdbc:mysql://127.0.0.1:3306/db1

细节：
如果连接的是本机mysql服务器，并且mysgl服务默认端口是3306，则url可以简写为：jdbc:mysql::/数据库名称？参数键值对
配置useSSL=false参数，禁用安全连接方式，解决警告提示
2.user:用户名
3.password:密码
```

```java
//先导入mysql-connector-java包
package com.lqx.jdbc;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class JDBCDemo {
    public static void main(String[] args) throws Exception {

        //1.注册驱动
        Class.forName("com.mysql.jdbc.Driver");
        //2.获取连接
        String url="jdbc:mysql://localhost:3306/fruitdb?useSSL=false";
        String username="root";
        String password="lqx";

        Connection conn = DriverManager.getConnection(url, username, password);
        //3.定义sq1
        String sql ="update t_fruit set price =2000 where fid = 1";
        //4.获取执行sgl的对象Statement
        Statement stmt =conn.createStatement();

        //5.执行sq1
        int count =stmt.executeUpdate(sql);
        System.out.println(count);
        stmt.close();
        conn.close();
    }
}

```



## 事务（具体在MYSQL）

![image-20220811084819397](JDBC连接池.assets/image-20220811084819397.png)

## 批处理

![image-20220811085506747](JDBC连接池.assets/image-20220811085506747.png)

![image-20220811085553062](JDBC连接池.assets/image-20220811085553062.png)

# 连接池

![image-20220811102742762](JDBC连接池.assets/image-20220811102742762.png)

![image-20220811153531288](JDBC连接池.assets/image-20220811153531288.png)

## 种类

![image-20220811153815865](JDBC连接池.assets/image-20220811153815865.png)

### C3P0

![image-20220811154228470](JDBC连接池.assets/image-20220811154228470.png)

### 德鲁伊

![image-20220811155906796](JDBC连接池.assets/image-20220811155906796.png)

```java
package com.lqx.druid;

import com.alibaba.druid.pool.DruidDataSource;
import com.alibaba.druid.pool.DruidDataSourceFactory;

import javax.sql.DataSource;
import java.io.FileInputStream;
import java.sql.Connection;
import java.util.Properties;

public class DruidDemo {
    public static void main(String[] args) throws Exception {

                //1.导入jar包
                //2.定义配置文件
                //3.加截配置文件
        Properties properties = new Properties();
//        当前系统根目录
//        System.out.println(System.getProperty("user.dir"));
        properties.load(new FileInputStream("jdbc-demo/src/druid.properties"));
//                //4.获取连接池对象
        DataSource dataSource = DruidDataSourceFactory.createDataSource(properties);
        Connection connection = dataSource.getConnection();
        System.out.println(connection);

    }
}

```

配置文件(根据自己的数据库更改url)

```properties
driverClassname=com.mysql.jdbc.Driver
url=jdbc:mysql://localhost:3306/fruitdb?useSSL=false&useServerPrepStmts=true
username=root
password=lqx
#初始化连接数量
initialSize=5
#最大连接数
maxActive=10
#最大等待时间
maxWait=3000
```



## Apache-DBUtils

![image-20220811162438757](JDBC连接池.assets/image-20220811162438757.png)

![image-20220811163623539](JDBC连接池.assets/image-20220811163623539.png)

![image-20220812161831029](JDBC连接池.assets/image-20220812161831029.png)

## basicDAO

![image-20220812164618006](JDBC连接池.assets/image-20220812164618006.png)

![image-20220812164634728](JDBC连接池.assets/image-20220812164634728.png)