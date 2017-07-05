PreparedStatement
====


## Using PreparedStatement under Hibernate

> Usually we get a Connection to build a PreparedStatement.

In Hibernate, we will get [Session](https://docs.jboss.org/hibernate/orm/3.5/api/org/hibernate/Session.html) from [SessionFactory](https://docs.jboss.org/hibernate/orm/3.5/api/org/hibernate/SessionFactory.html)
to get Connection, however the method Session.connection() has been marked as **Deprecated**

So now we can use Session.doWork() to build a PreparedStatement from Connection, here is an example:


```java
getSession().doWork(new Work() {
      @Override
      public void execute(Connection connection) throws SQLException {
        PreparedStatement ps = connection.prepareStatement("");
        try {
          //...
          //...
        } catch (Exception e) {
          e.printstack();
        } finally {
          if (null != ps) {
            ps.close();
          }
        }
      }
    });
```
