## Http结构

根据结构可以分为：

- 报文头：一些固有属性

- 报文体：实际内容



根据报文类型可以分为：

- 请求报文
- 响应报文



### 请求报文

请求报文的报文头结构如下：

- 请求行：
    - 请求方法
    - 请求资源
    - 请求使用的协议（1.0、1.1等）
- 首部字段：
    - **通用字段（响应报文和请求报文都有的字段）**：
        - Date
        - Connection
        - Transfer-Encoding
    - 请求字段（请求报文独有的字段）：
        - Host：请求资源所在服务器
        - Accept-Charset：可接收的字符集
        - Accept-Encoding：可接受的内容编码
    - 实体字段（**请求报文与响应报文的的实体部分使用的首部字段**）：
        - Content-Type：实体主类的类型
        - Content-Encoding：实体主体适用的编码方式



响应报文的报文头结构如下：

- 状态行：
    - 响应的状态码（以及对应的信息说明）
    - http协议号
- 首部字段：
    - 响应字段
        - Location：令客户端重新定向到的URI
        - Server：HTTP服务器的安装信息
    - 通用字段：
    - 实体字段：





## 常用请求方法

POST：数据在报文体里，且无大小限制。

GET：数据跟在URL后的？后，有1kb限制。

PUT：文件传输

HEAD：获得报文首部（可用于验证URL有效）





## 常用状态码

200：正确处理



301：永久重定向

302：临时重定向



403：资源禁止

404：找不到资源



500：内部错误

503：服务器正忙



### [HTTP常见面试题](https://mp.weixin.qq.com/s?__biz=MzI4Njg5MDA5NA==&mid=2247484979&idx=3&sn=37528f67d16315e5d49ad48ebf6bd53d&chksm=ebd74732dca0ce2446aa4a66e22f082d48b49f63301be748e61ce652b3a00de53d4f15cef3a7###rd)


