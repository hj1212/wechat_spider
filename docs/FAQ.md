FAQ

------------------------------------------------------------------------

## 对比其他微信爬虫, 这个有什么优势?

- 开源的一些微信爬虫比较常见的是 抓取搜狗微信,清博指数,清榜等网站的内容, 属于二次爬虫,局限性大,并且要突破验证码或者模拟登陆, 不能获取公众号所有文章,比较受限制


- 这个爬虫数据源直接来源于微信,抓取的是微信请求中返回的数据,对比前者,比较灵活

## 你这个爬虫稳定吗, 会不会被微信封掉吗,效率怎么样?

- 爬虫是稳定的,  基于中间人攻击,完全模拟人的行为, 目前测试来看,一个测试号1s可以爬完一个公众号的内容,频率可以自定义控制.

## 不太明白设置代理是什么含义？具体应怎样设置？
- 这个问题说明你可能还不清楚 中间人攻击的原理, 可以查看相关资料了解下
    中间人攻击: http://baike.baidu.com/link?url=H5NTIRV0Ga78D4X_3asVNUzZCjqtgdNahvZk8xDjlkB5SDO3eG14k0PPFBNwVHp043RarDoxi-3Y91qee9ePT_
    windows设置全局代理: http://jingyan.baidu.com/article/a378c960843744b32928307e.html
    android设置全局代理: https://www.zhihu.com/question/21474174

## 我不会go语言,如何使用你的爬虫框架?
- 首先这个代码是面向开发者开源的,开发想简单使用的话,可以装个go环境,跑一下示例程序,其实核心代码不过200行, 这个框架只是核心组件的实现, 没有做到工程化, 需要工程定制请稍微学习下Go语言即可

## 爬虫可以输出到队列,数据库,文件等吗?
- 可以自定义输出,请参考 https://github.com/sundy-li/wechat_spider/blob/master/examples/custom_output_server.go

## 批量爬虫的bizs如何获取到? NextBiz方法如何实现?

- biz就是公众号的唯一id, 你可以从公众号任意一篇文章的url参数中获取, 可以从历史文章列表的链接获取 也可以从清博,微信sogou中自动获取
  NextBiz可以读取队列,数据库,作为发号器来轮询实现批量化 



##  通过pyautogui.position() 瞄点设置 first_ret, rel_link 坐标。这里也不是很明白需要如何操作。

- 先参考代码: https://github.com/sundy-li/wechat_spider/blob/master/examples/win_client.py 这个是windows客户端批量请求公众号历史文章链接的代码的逻辑,原理是通过win32的api获取对应的句柄,来发送url给微信,操作鼠标移动坐标模拟点击url,服务端进行报文截取. 理清这个逻辑之后, 这个pyautogui.position() 其实就是  pyautogui 的瞄点api,具体可以看pyautogui文档



##  这个爬虫还有什么缺陷
- ~~暂时不能获取阅读点赞数~~ ← Complete!
- 还不能做到很智能的自动关注公众号,目前是基于adbshell来做,存在不稳定因素,暂未开源, 有好的实现思路的请和我沟通

## 有任何bug或者错误欢迎各位提出宝贵意见,也欢迎各位加我qq沟通交流(为节约大家时间,请务必先阅读文档,提些有建设性的问题)

截止到目前(2016年12月21日, 我们基于这个框架开发的微信公众号爬虫 单机器已经爬取100w+公众号文章数据,还没出现不稳定的情况, 如果您想支持我们持续维护此项目, 那就请我喝一杯咖啡吧~

![支持一下](donate.png)


## 打赏赞助者列表 (已经支持的朋友请加qq群联系,我定期更新此赞助者列表)
```
$6.6   匿名用户
$8.88   569242547@qq.com
$5    匿名用户
$168  2569088250@qq.com
$88    84801236@qq.com
$8.88   31558614@qq.com
$9.99 匿名用户
$66    167772566@qq.com
$16.8    730541396@qq.com
$50   kangkangv5(github)
$8.88  275849175@qq.com
$6.60  308276729@qq.com
$2.80 857299693@qq.com
$10.00 258513813(github)
$18.80   匿名用户
$9.99   匿名用户
```



