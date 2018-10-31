
# 通信类

## COM通信

COM通信包括“COM参数”、“COMDriver”、“COM列表”共3个模块。

![系统资源](../image/src1.png)

其中：

- **COM参数**模块

  用来配置串口波特率、数据位、停止位等参数，如下图所示：
  
  ![系统资源](../image/src2.png)
  
  参数从上到下依次是：波特率、数据位、停止位、校验、流控、包间隔时间。
  
  *包间隔时间* 单位是毫秒，表示相隔两个数据包之间的最小间隔时间，用来分包输出。

  左侧是输入数据点，用于从显示界面设置串口参数。
  
  右侧是输出数据点，输出参数对象，格式如下：
  
  ```js
  {
    "baudRate":9600,
    "dataBits":8,
    "stopBits":1,
    "flowControl":false,
    "parity":"none",
    "packageInterval":100
  }
  ```
  
- **COM列表**模块

  用来获取系统串口，将获取到的串口名称用下拉列表形式显示出来，供选择使用。
  
  ![系统资源](../image/src3.png)
  
  数据点输出串口名称字符串

- **comDriver**模块

  是COM口的驱动模块，配置好参数即可实现COM通信。
  
  ![系统资源](../image/src4.png)
  
  左侧输入数据点依次是：COM名称，COM参数，发向COM的数据（数组类型）
  
  右侧输出数据点是：来自COM的数据（数组类型）

  模块用法：
  
  ![系统资源](../image/src5.png)
  
  配置COM名称和参数，接收到COM输出数据后，自定义解析脚本模块，解析出有效数据。


## MQTT通信

系统支持MQTT服务端和客户端两种模式。

![系统资源](../image/src6.png)

- **mqttClient客户端**

如果CAT▪IOT-IDE开发的应用要连接外部平台的mqtt server，只需要拖出mqttClient客户端模块，并配置参数：

![系统资源](../image/src8.png)

<p class="tip">发布运行后，mqttClient会自动连接服务端，并具有断线自动重连能力，连接成功模块右上角指示灯点亮。</p>

**订阅** 数据点

值类型：Array数组，可以向服务端订阅多个主题，

数组格式：[topic1, topic2, topic3]，其中每个topic均为字符串

举例：

```js
[
  "v1/A1B1C1D1/+/cmd",
  "v1/A2B2C2D2/+/cmd",
  "v1/A3B3C3D3/+/cmd"
]
```

**发送** 数据点

值类型：Object对象

对象格式：{topic,payload}

举例：

```js
{
  topic: "v1/A2B2C2D2/1/value",
  payload: 12.3
}
```

**接收** 数据点

值类型：Object对象

对象格式：{topic,payload}

举例：

```js
{
  topic: "v1/A2B2C2D2/1/value",
  payload: 12.3
}
```


- **mqttServer服务端**

拖出mqttServer生成服务实例，接收来自设备或其它mqtt客户端的连接、订阅、数据上传。mqttServer根据订阅分发规则，向客户端实时发送订阅数据。

![系统资源](../image/src7.png)

<p class="tip">mqttServer没有输出数据点，在CAT▪IOT-IDE中只能建立一个mqttClient，通过订阅来获取数据。</p>

![系统资源](../image/src9.png)





