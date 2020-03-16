1、如果出现fake_useragent.errors.FakeUserAgentError: Maximum amount of retries reached
【解决办法】
* 使用命令 pip install -U fake-useragent 更新fake-useragent
* 禁用服务器缓存： ua = UserAgent(use_cache_server=False)
* 无效，不缓存数据：ua = UserAgent(cache=False)
* 无效，忽略ssl验证：ua = UserAgent(verify_ssl=False)
* 下载： https://fake-useragent.herokuapp.com/browsers/0.1.11  到本地 另存为  fake_useragent.json
~~~
def get_header():
    location = os.getcwd() + '/fake_useragent.json'
    ua = fake_useragent.UserAgent(path=location)
    return ua.random
~~~
[参考链接](https://www.cnblogs.com/kermitjam/p/11287883.html)

# tickets
