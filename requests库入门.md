## requests库入门

### requests库的7个主要方法

| 方法               | 说明                                           |
| ------------------ | ---------------------------------------------- |
| requests.request() | 构造一个请求，支撑以下各方法的基础方法         |
| requests.get()     | 获取HTML网页的主要方法，对应于HTTP的GET        |
| requests.head()    | 获取HTML网页头信息的方法，对应于HTTP的HEAD     |
| requests.post()    | 向HTML网页提交POST请求的方法，对应于HTTP的POST |
| requests.put()     | 向HTML网页提交PUT请求的方法，对应于HTTP的PUT   |
| requests.patch()   | 向HTML网页提交局部修改请求，对应于HTTP的PATCH  |
| requests.delete()  | 向HTML页面提交删除请求，对应于HTTP的DELETE     |



### requests.get()

![requests.png](/Users/ym/Desktop/Notes/Python网络爬虫/resources/requests.get.png)

- 主要格式

  `requests.get(url, params=None, **kwargs)`

  - url : 拟获取页面的url链接
  - params : url中的额外参数， 字典或字节流格式， 可选
  - **kwargs : 12个控制访问的参数

```python
import requests
url = 'https://www.baidu.com'
resp = requests.get(url)
resp.status_code  # 200 for successful
```



### Response 对象的属性

| 属性              | 说明                                                         |
| ----------------- | ------------------------------------------------------------ |
| status_code       | HTTP请求的返回状态, 200表示链接成功，404表示没有url指定的页面 |
| text              | HTTP响应内容的字符串格式，即，url对应的页面内容              |
| encoding          | 从HTTP header中猜测的响应内容的编码方式                      |
| apparent_encoding | 从内容中分析出的响应内容的编码方式（备选编码方式）           |
| content           | HTTP响应内容的二进制形式                                     |



### 理解Requests库的异常

| 异常               | 说明                                        |
| ------------------ | ------------------------------------------- |
| ConnectionError    | 网络连接错误异常，如DNS查询失败，拒绝连接等 |
| HTTPError          | HTTP错误异常                                |
| URLRequired        | URL缺失异常                                 |
| TooManyRedirects   | 超过最大重定向次数，产生重定向异常          |
| ConnectTimeout     | 连接远程服务器超时异常                      |
| Timeout            | 请求URL超时，产生超时异常                   |
| raise_for_status() | 如果不是200，产生异常requests.HTTPError     |



```python
import requests
url = 'https://www.baidu.co'   # 一个错误的url地址
try:
  r = requests.get(url, timeout=30)
  r.raise_for_status()  # 如果返回的status code不是200， 会raise一个HTTPError的异常
  r.encoding = r.apparent_encoding
  print(r.text)
except:
  print('发生异常')
```



### HTTP协议对资源的操作

| 方法   | 说明                                                      |
| ------ | --------------------------------------------------------- |
| GET    | 请求获取URL位置的资源                                     |
| HEAD   | 请求获取URL位置资源的响应消息报告，即获得该资源的头部信息 |
| POST   | 请求向URL位置的资源后附加新的数据                         |
| PUT    | 请求向URL位置存储一个资源，覆盖原URL位置的资源            |
| PATCH  | 请求局部更新URL位置的资源，即改变该处资源的部分内容       |
| DELETE | 请求删除URL位置存储的资源                                 |

![http协议对资源的操作](/Users/ym/Desktop/Notes/Python网络爬虫/resources/http协议对资源的操作.png)

注：HTTP协议方法和Requests库提供的库方法，功能上完全一致

```python
import python
r = requests.head('http://httpbin.org/get')  # http://httpbin.org提供测试
```



