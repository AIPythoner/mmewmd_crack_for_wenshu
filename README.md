# 文书网反反爬虫SDK
## 前言
一月份的时候中国裁判文书网更新了据说是瑞数安全的js混淆动态加密。 <br>
特征1：params:MmEwMd <br>
特征2：html:9DhefwqGPrzGxEp9hPaoag <br>
特征3：cookies：FSSBBIl1UgzbN7N80T

## 项目
本项目为学习Js加密和向反爬虫工程师前辈们学习而立，请勿用于违法用途，用于违法用途产生的后果与本人无关，本版本仅供学习参考所用，所有下载者应于24小时内学习完毕后删除。
由于本次项目需求的朋友来自使用各个开发语言，本次sdk将会js的方式提供，各开发者可以根据自己开发语言考虑采用v8引擎执行或语言自带的执行js的函数或者是第三方包。

## 调用思路
[请严格按照此思路调用，否则会出现大量remindkey或者202]

###定义:
####完整生命周期
第一步:
必须至少进行一次二次跳转:

①第一次访问List页应当cookies中不含有F80系列cookies，此时必定202，并返回F80S和假F80T, 获得meta头

②第二次访问List页应当带上第一次访问返回的F80S和用第一次返回的假F80T生成的真F80T，此时会返回vjkl5， 获得meta头

第二步:
此时我们应当保存上一步最后请求时的真F80T，还有①中的F80S, vjkl5, ②中的meta头。
之后的每一次访问ListContent页面，都需要使用上一次访问时（在第一次访问ListContent的时候，用的是②中的真F80T）的真F80T去生成新的真F80T，且每次生成的F80T仅可使用一次后作废，作废后用于生成下一次新的真F80T。

####爬虫生命周期理论
当遇到了任何一个接口返回码为202时，意味着一次上述的完整证明周期结束。需要重新按照上面的生命周期运行。
此处包含，访问时出现的202或者是更换了代理IP（暂时未验证，如果有验证的朋友可以给我提一下测试结果）。


建议：相同请求请加上3秒左右的延迟





## 更新tip

### 2019.1.20
在连续5天的奋战下，我们sdk最终版终于完成！本项目以jssdk为核心，本次发布python调用实例，敬请参考。
将在未来1-2天内发布java，go，c#的实例版本，欢迎大家star和加入我们这个有爱的数据矿工(下🈶群号)群体。
一测试：商标网已通杀可通过本sdk访问。

python版：guid请自行找算法生成，否则会remind key！！

本次开发全程直播，将由"时光机"和老高两位志愿开发者将视频剪辑后发布，具体视频地址敬请期待。
虎牙直播间:17593443欢迎订阅

[一个97少年的战斗史，找对象，找工作]

### 2019.1.17
这个版本加密里面工程师下的毒太多了，现在上传的是已经确定加密过程，但由于部分加密参数获取的生成方式依旧不是很全面，所以暂时无法通过瑞数的审核，带生成的参数访问页面会400错误。
不过现在可以肯定的是目前这个版本是整个MmEwMd的主要生成方式，待我整理思路把不确定的参数生成方式全部弄清楚，会给大家继续献上完整SDK。下次更新时间预计为2019.1.19之前。

请clone代码后，清空浏览器缓存打开文书网，把当前的cookies中的FSSBBIl1UgzbN7N80T参数值填写到python代码对应位置直接运行生成的就是MmEwMd参数。
关于MmEwMd：已经通过比对，确认生成的长度和规则是一致的。

## 快乐的爬虫群
**QQ119794042**



### 鼓励
如果我的项目帮助到了你，可否通过打赏鼓励一下作者


<img src="https://github.com/sml2h3/mmewmd_crack_for_wenshu/blob/master/1548066223468.jpg" width="366" hegiht="570" style="display: inline-block"/>
<img src="https://github.com/sml2h3/mmewmd_crack_for_wenshu/blob/master/mm_facetoface_collect_qrcode_1548066239153.png" width="366" hegiht="570" style="display: inline-block"/>
