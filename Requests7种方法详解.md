## Requests 7种方法详解

### requests.request(method, url, **kwargs)

![requests.request()方法](/Users/ym/Desktop/Notes/Python网络爬虫/resources/request方法.png)

- **kwargs : 控制访问参数，均为可选项

  - params : 字典或字节序列，作为参数增加到url中

    ```python
    kv = {'key1':'value1', 'key2':'value2'}
    r = requests.request('GET', 'http://python123.io/ws', params=kv)
    print(r.url) # 输出 http://python123.io/ws?key1=value1&key2=value2
    ```

  - data : 字典、字节序列或文件对象，作为request的内容

  - json : JSON格式的数据，作为request的内容

  - headers : 字典，HTTP定制头

  - cookies : 字典或CookieJar，Request中的cookie

  - auth : 元组，支持HTTP认证功能

  - files : 字典类型，传输文件

  - timeout :  设置超时时间，以秒为单位

  - proxies : 字典类型，设定访问代理服务器，可以增加登录认证

    ```python
    pxs = {'http': 'http://user:pass@10.10.10.1:1234',
          'https': 'https://10.10.10.1:4321'}
    r = requests.request('GET', 'http://www.baidu.com', proxies=pxs) # 使用代理服务器访问baidu 
    ```

  - allow_redirects : True / False，默认为True, 重定向开关

  - stream : True / False，默认为True，获取内容立即下载开关

  - verify : True / False，默认为True，认证SSL证书开关

  - cert : 本地SSL证书路径

  

