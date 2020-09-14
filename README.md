# EzCheckInSchool
最简单的完美校园自动健康打卡，基于Github Actions免服务器运行。

- 仅需学号姓名🎫
- 随机校内经纬度🗺️
- 打卡结果微信推送💬
- 随机温度(36.2℃-36.4℃)🌡
- 校内打卡三次:06:05,12:35,21:05🕑

**首次开启若不在打卡时间将会重打早间卡作为测试**

**Github Actions定时任务可能出现几分钟的误差**

**推荐迁移到腾讯云云函数，修改`input()`为对应字符串后设置定时触发器即可**

## 更新日志
2020.9.13 20:45 更新最简单免抓包使用方法及代码

2020.9.12 7:00 修复时间判断代码，现在将正常打卡三次

## 使用方法
首先，点击`Star`和`Fork`
<button type="submit" class="btn btn-sm btn-with-count  js-toggler-target" aria-label="Unstar this repository" title="Star chillsoul/EzCheckInSchool" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;STAR_BUTTON&quot;,&quot;repository_id&quot;:294446353,&quot;originating_url&quot;:&quot;https://github.com/chillsoul/EzCheckInSchool&quot;,&quot;user_id&quot;:42226579}}" data-hydro-click-hmac="d76d13c9fe8c8f4dfc3124cd99a79b79adc1c00b33238e78926081d967cc450b" data-ga-click="Repository, click star button, action:files#disambiguate; text:Star">        <svg height="16" class="octicon octicon-star" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25zm0 2.445L6.615 5.5a.75.75 0 01-.564.41l-3.097.45 2.24 2.184a.75.75 0 01.216.664l-.528 3.084 2.769-1.456a.75.75 0 01.698 0l2.77 1.456-.53-3.084a.75.75 0 01.216-.664l2.24-2.183-3.096-.45a.75.75 0 01-.564-.41L8 2.694v.001z"></path></svg> Star </button>

<button class="btn btn-sm btn-with-count" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;FORK_BUTTON&quot;,&quot;repository_id&quot;:294446353,&quot;originating_url&quot;:&quot;https://github.com/chillsoul/EzCheckInSchool&quot;,&quot;user_id&quot;:49368189}}" data-hydro-click-hmac="f8be48acbef26b397228e428d75ea61fea22ca140e88951bbbf4e851ac835fb7" data-ga-click="Repository, show fork modal, action:files#disambiguate; text:Fork" type="submit" title="Fork your own copy of chillsoul/EzCheckInSchool to your account" aria-label="Fork your own copy of chillsoul/EzCheckInSchool to your account">              <svg class="octicon octicon-repo-forked" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M5 3.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm0 2.122a2.25 2.25 0 10-1.5 0v.878A2.25 2.25 0 005.75 8.5h1.5v2.128a2.251 2.251 0 101.5 0V8.5h1.5a2.25 2.25 0 002.25-2.25v-.878a2.25 2.25 0 10-1.5 0v.878a.75.75 0 01-.75.75h-4.5A.75.75 0 015 6.25v-.878zm3.75 7.378a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm3-8.75a.75.75 0 100-1.5.75.75 0 000 1.5z"></path></svg> Fork </button>



接下来你需要设置`Secert`

你Fork的项目->Settings->Secert->New Secert

|Name|Value|示例|
| :-----| :---- | :---- |
|`DEPT_TEXT`|`学院班级专业`|`理学院-应用物理学-应物1901`|
|`STU_ID`|`你的学号`|`201912340101`|
|`STU_NAME`|`你的姓名`|`李华`|
|`SC_URL`|[`Server酱调用URL`](http://sc.ftqq.com/?c=code)|`http://sc.ftqq.com/abcdefghigklmnopqrstuvwxyz.send`| 

使用前请注册绑定[Server酱](http://sc.ftqq.com/)


以上步骤完成后

Settings->Action->I understand... 开启Actions

回到项目主页，修改[README.md](/README.md)随便加几个空格即可

设置完成打卡后打卡时间内会每天自动打卡三次，第一次使用请观察效果。

**注意：本项目默认学校为河南工业大学，其他学校请自行抓包修改代码。**

|Method|URL|修改|
| :-----| :---- | :---- |
|`POST`|`https://reportedh5.17wanxiao.com/sass/api/epmpics`|`main.py`|
|`POST`|`https://reportedh5.17wanxiao.com/api/passcard/queryOrg`|`response.json`|
## 友情链接

https://github.com/YooKing/HAUT_autoCheck - 校外版Python代码参考

https://github.com/LovelyWhite/Haut-AutoCheckin - iPhone捷径版

