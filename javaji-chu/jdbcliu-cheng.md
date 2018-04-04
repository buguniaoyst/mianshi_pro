# JDBC开发流程

---

```java
准备工作中导入ojdbc文件，然后右键选中添加路径
    build path-->到oracle安装目录里添加oracle的ojdbc.jar包
    (1).注册驱动
        Class.forName("oracle.jdbc.OracleDriver");
    (2).连接数据库
        String url = "jdbc:oracle:thin:@localhost:1521:xe";//其中xe为sid
        String user = "XXX";
        String password = "XXX";
        Connection conn = DriverManager.getConnection(url,name,password);
    (3).创建搬运工statement
        Statement state = conn.createStatement();
    (4).搬运数据,执行SQL语句
        String sql = "select id,name from s_emp";   //"insert into s_emp(id,name) values(12,'zhangsan')";
        ResultSet rs = state.executeQuery(sql);
    (5).处理结果集
        while(rs.next()){
            int id = rs.getInt("id");
            String name = rs.getString(2);
            System.out.println(id+" "+name);
        }
    (6).关闭连接
        rs.close();
        state.close();
        conn.close();
```



