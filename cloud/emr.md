emr5.10を利用すると、以下のようなエラーが出る。

```
17/12/13 08:25:40 WARN HttpChannel: //ip-10-**-**-**.ml.aws.ckpd.co:4040/api/v1/applications/application_1513149112150_0004/stages/9/0/taskSummary?proxyapproved=true
javax.servlet.ServletException: java.util.NoSuchElementException: None.get
        at org.glassfish.jersey.servlet.WebComponent.serviceImpl(WebComponent.java:489)
        at org.glassfish.jersey.servlet.WebComponent.service(WebComponent.java:427)
        at org.glassfish.jersey.servlet.ServletContainer.service(ServletContainer.java:388
```

プロキシエラー？DNS関連？

