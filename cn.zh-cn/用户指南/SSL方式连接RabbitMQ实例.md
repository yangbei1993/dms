# SSL方式连接RabbitMQ实例<a name="dms-ug-180801004"></a>

创建实例时开启SSL访问，则数据加密传输，安全性更高。

本节介绍VPC内访问开启SSL的RabbitMQ实例的方法。

## 前提条件<a name="section17830048113810"></a>

-   参考[购买实例](购买实例.md)章节创建RabbitMQ实例，并记录创建时输入的用户名和密码。
-   创建完成后，单击实例名称，查看并记录实例详情中的“连接地址”。
-   已创建弹性云服务器，并且弹性云服务器的VPC、子网、安全组与RabbitMQ实例的VPC、子网、安全组保持一致。

## 命令行模式连接实例<a name="section0505194112013"></a>

1.  登录弹性云服务器，如开启公网访问，则直接登录执行主机。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >弹性云服务器必须与RabbitMQ实例处于相同VPC、子网与安全组。  

2.  安装Java JDK或JRE，并配置JAVA\_HOME与PATH环境变量，使用执行用户在用户家目录下修改.bash\_profile，添加如下行，路径以实际为准。

    ```
    export JAVA_HOME=/opt/java/jdk1.8.0_151 
    export PATH=$JAVA_HOME/bin:$PATH
    ```

    执行source .bash\_profile命令使修改生效。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >ECS虚拟机默认自带的JDK可能不符合要求，例如OpenJDK，需要配置为Oracle的JDK，可至[Oracle官方下载页面](http://www.oracle.com/technetwork/java/javase/downloads/index.html)下载Java Development Kit 1.8.111及以上版本。  

3.  下载RabbitMQ-Tutorial-SSL.zip示例工程代码。

    ```
    $ wget https://dms-demo.obs.myhwclouds.com/RabbitMQ-Tutorial-SSL.zip
    ```

4.  解压RabbitMQ-Tutorial-SSL.zip压缩包。

    ```
    $ unzip RabbitMQ-Tutorial-SSL.zip
    ```

5.  进入RabbitMQ-Tutorial-SSL目录，该目录下包含预编译好的jar文件。

    ```
    $ cd RabbitMQ-Tutorial-SSL
    ```

6.  运行生产消息示例。

    ```
    $ java –cp .:rabbitmq-tutorial-sll.jar Send host port user password
    ```

    **图 1**  生产消息示例<a name="fig17886288296"></a>  
    ![](figures/生产消息示例.png "生产消息示例")

    使用Ctrl+C命令退出。

7.  运行消费消息示例。

    ```
    $ java –cp .:rabbitmq-tutorial-sll.jar Recv host port user password
    ```

    **图 2**  消费消息示例<a name="fig38681436182911"></a>  
    ![](figures/消费消息示例.png "消费消息示例")

    如需停止消费使用Ctrl+C命令退出。


## 示例代码（Java）<a name="section79327586818"></a>

连接实例并生产消息

```
ConnectionFactory factory = new ConnectionFactory();
 factory.setHost(host);
 factory.setPort(port);

 factory.setUsername(user);
 factory.setPassword(password);
 factory.useSslProtocol();
 Connection connection = factory.newConnection();
 Channel channel = connection.createChannel();

 channel.queueDeclare(QUEUE_NAME, false, false, false, null);

 String message = "Hello World!";
 channel.basicPublish("", QUEUE_NAME, null, message.getBytes("UTF-8"));
 System.out.println(" [x] Sent '" + message + "'");

 channel.close();
 connection.close();
```

连接实例并消费消息

```
ConnectionFactory factory = new ConnectionFactory();
 factory.setHost(host);
 factory.setPort(port);
 factory.setUsername(user);
 factory.setPassword(password);
 factory.useSslProtocol();
 Connection connection = factory.newConnection();
 Channel channel = connection.createChannel();

 channel.queueDeclare(QUEUE_NAME, false, false, false, null);
 System.out.println(" [*] Waiting for messages. To exit press CTRL+C");

 Consumer consumer = new DefaultConsumer(channel)
 {
     @Override
     public void handleDelivery(String consumerTag, Envelope envelope, AMQP.BasicProperties properties,
             byte[] body)
             throws IOException
     {
         String message = new String(body, "UTF-8");
         System.out.println(" [x] Received '" + message + "'");
     }
 };
 channel.basicConsume(QUEUE_NAME, true, consumer);
```

