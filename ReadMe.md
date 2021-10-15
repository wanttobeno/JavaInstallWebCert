


##### 访问网址，JAVA报错

```
javax.net.ssl.SSLHandshakeException: sun.security.validator.ValidatorException: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
	at sun.security.ssl.Alerts.getSSLException(Alerts.java:192)
	at sun.security.ssl.SSLSocketImpl.fatal(SSLSocketImpl.java:1949)
	at sun.security.ssl.Handshaker.fatalSE(Handshaker.java:302)
```

##### 解决方法,添加证书

```
java -jar  com.wow.InstallCert-1.0.jar host

java -jar  com.wow.InstallCert-1.0.jar www.github.com
```

执行报错，请使用管理员/root权限运行。


##### 自动证书路径

设置JAVA环境变量后，可自动识别证书路径,添加正式，并创建备份

Mac
```
Mac$ sudo java -jar com.wow.InstallCert-1.0.jar www.github.com
Loading KeyStore /Library/Java/JavaVirtualMachines/jdk1.8.0_74.jdk/Contents/Home/jre/lib/security/jssecacerts
```

Windows
```
D:\>java -jar D:\com.wow.InstallCert-1.0.jar www.github.com
Loading KeyStore D:\Program Files\Java\jre1.8.0_74\lib\security\cacerts...
Opening connection to  www.github.com:443...
Starting SSL handshake...
```

Linux
```
[root@wow]# java -jar com.wow.InstallCert-1.0.jar  www.github.com
Loading KeyStore /usr/java/jdk1.8.0_211/jre/lib/security/jssecacerts...
Opening connection to  www.github.com:443...
Starting SSL handshake...
```