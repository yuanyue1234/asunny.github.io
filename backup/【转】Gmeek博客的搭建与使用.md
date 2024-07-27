转载自：[Gmeek博客的使用方法](https://blog.liyifan.xyz/post/yong-Gmeek-da-jian-yi-ge-shu-yu-zi-ji-de-bo-ke.html)
感谢作者，同样感谢这个博客系统，推荐大家试一试，搭建一个自己的博客。写一写自己的东西，感谢他们让这变得无比简单。

> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.liyifan.xyz](https://blog.liyifan.xyz/post/yong-Gmeek-da-jian-yi-ge-shu-yu-zi-ji-de-bo-ke.html)

> [Gmeek](https://github.com/Meekdai/Gmeek) 博客完全依托 github，提供域名，无需服务器，比起传统的服务器建站更方便快捷。

博客中的内容将完全公开，不要上传隐私内容！！

一、创建 github 仓库
--------------

### 1. 登录 github

> 没有账号的话可以在 github 主页注册

### 2. 进入 [Gmeek](https://github.com/Meekdai/Gmeek) 仓库

[https://github.com/Meekdai/Gmeek](https://github.com/Meekdai/Gmeek)

### 3. 创建仓库

在 Gmeek 仓库的 readme 中点击`通过模板创建仓库`

![](https://img.liyifan.xyz/file/e860fa26fc02859344a77.png)

会打开如下网页：

![](https://img.liyifan.xyz/file/c4fc9e5406082ab8eaf02.png)

在`Repository name`处填写`github账号的名字.github.io`

> 比如 github 账号的名字是`liyifan`，就填写`liyifan.github.io`

Note

`Repository name`可以随意填写，但是为了之后生成的域名简短，最好填`github账号的名字.github.io`

最后点击`create repository`完成仓库创建！

![](https://img.liyifan.xyz/file/e7a2658c391bb245ff30f.png)

二、配置仓库
------

### 1. 进入刚刚创建完成的仓库，点击`settings`

![](https://img.liyifan.xyz/file/edc56fb31b0510b441497.png)

### 2. 进入`pages`分页

![](https://img.liyifan.xyz/file/89198898a426807f1ed19.png)

### 3. 将构建方式改为`github actions`

![](https://img.liyifan.xyz/file/5adfdac21ba9da137f6e4.png)

Note

关于自定义域名，可以在下方的`custom domain`中填写，需要一个二级域名，并添加 cname 解析，指向`github账号的名字.github.io`  
![](https://img.liyifan.xyz/file/8f04f09bdcdf8fd81cd6f.png)  
![](https://img.liyifan.xyz/file/98294a9f9b913b9caf96b.png)

### 4. 进入`issues`页面，然后点击`new issue`

![](https://img.liyifan.xyz/file/087b466ec09136a170fa9.png)

### 5. 随意填入标题和正文，随意添加一个`标签（lable）`，然后点击`submit new issue`

![](https://img.liyifan.xyz/file/7bc0d98eed8e4fe84484c.png)

此时在`actions`界面中可以看到正在构建，等待一分钟左右直到构建完成

### 6. 回到`code`界面，此时域名已经生成

![](https://img.liyifan.xyz/file/68b636609b57df758edc2.png)

> 如果没添加自定义域名，域名会是 xxx.github.io

三、修改配置文件
--------

### 1. 打开`config.json`

在 code 界面点击`config.json`

![](https://img.liyifan.xyz/file/4dcf3ca2c7fbc0f740eba.png)

点击钢笔图案开始编辑

![](https://img.liyifan.xyz/file/ca56f9adf974763b3d6ae.png)

### 2. [配置参数](https://blog.meekdai.com/post/Gmeek-kuai-su-shang-shou.html)

Caution

最后一行配置末尾不需要逗号，其他行末尾都需要逗号（英文逗号）

```
{
    "title":"Meekdai",
    "subTitle":"童话是一种生活态度，仅此而已。",
    "avatarUrl":"https://github.githubassets.com/favicons/favicon.svg",
    "GMEEK_VERSION":"last"
}


```

以上是必须的字段，下面是可以自定义字段的描述，可以选择加入到`config.json`中。

```
"displayTitle":"Meekdai",
"homeUrl":"http://blog.meekdai.com",
"faviconUrl":"https://github.githubassets.com/favicons/favicon.svg",
"email":"meekdai@163.com",
"startSite":"02/16/2015",
"filingNum":"浙ICP备20023628号",
"onePageListNum":15,
"singlePage":["about"],
"iconList":{"music":"M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8Zm8-6.5a6.5 6.5 0 1 0 0 13 6.5 6.5 0 0 0 0-13Z"},
"exlink":{"music":"https://music.meekdai.com"},
"commentLabelColor":"#006b75",
"yearColorList":["#bc4c00", "#0969da", "#1f883d", "#A333D0"],
"i18n":"CN",
"UTC":8,
"themeMode":"manual",
"dayTheme":"light",
"nightTheme":"dark_colorblind",
"urlMode":"pinyin",
"style":"",
"script":"",
"indexStyle":"",
"indexScript":"",
"showPostSource":1,
"rssSplit":"sentence",
"bottomText":"转载请注明出处",
"ogImage":"https://cdn.jsdelivr.net/gh/Meekdai/meekdai.github.io/logo64.jpg",
"primerCSS":"<link href='https://mirrors.sustech.edu.cn/cdnjs/ajax/libs/Primer/21.0.7/primer.css' rel='stylesheet' />",
"needComment":0,


```

<table role="table"><thead><tr><th>配置参数</th><th>说明</th></tr></thead><tbody><tr><td>title</td><td>【必填】博客标题</td></tr><tr><td>subTitle</td><td>【必填】博客描述 &amp; 自述</td></tr><tr><td>avatarUrl</td><td>【必填】博客头像</td></tr><tr><td>GMEEK_VERSION</td><td>【必填】Gmeek 版本，一般写 last 也可以用具体 tag 版本</td></tr><tr><td>displayTitle</td><td>用于头像后面的标题展示，如果和 title 一致则不用添加</td></tr><tr><td>homeUrl</td><td>博客的主页地址，自定义域名时需要配置</td></tr><tr><td>faviconUrl</td><td>页面的 favicon 地址，如果和 avatarUrl 一致则不用添加</td></tr><tr><td>email</td><td>用于自动提交仓库时用，不添加也可以</td></tr><tr><td>startSite</td><td>用于页面底部显示网站运行天数</td></tr><tr><td>filingNum</td><td>用于页面底部显示备案信息</td></tr><tr><td>onePageListNum</td><td>用于首页每页展示的文章数量</td></tr><tr><td>singlePage</td><td>自定义独立页面，例如 about 或者 link 等</td></tr><tr><td>iconList</td><td>用于定义 singlePage 按钮展示的 SVG 图标 (16px)，about 和 link 内置无需定义</td></tr><tr><td>exlink</td><td>用于自定义首页右上角圆形按钮到外部链接功能，按钮图标定义在 iconList 中</td></tr><tr><td>commentLabelColor</td><td>用于自定义显示评论数量标签的颜色</td></tr><tr><td>yearColorList</td><td>用于自定义显示不同年份标签的颜色</td></tr><tr><td>i18n</td><td>用于定义博客语言，目前支持 EN/CN/RU</td></tr><tr><td>UTC</td><td>用于定义时区</td></tr><tr><td>themeMode</td><td>用于定义主题模式，默认为 manual，也可选择 fix 详细说明</td></tr><tr><td>dayTheme</td><td>用于定义亮主题</td></tr><tr><td>nightTheme</td><td>用于定义暗主题</td></tr><tr><td>urlMode</td><td>用于定义文章链接生成模式，目前支持 pinyin/issue/ru_translit</td></tr><tr><td>style</td><td>用于自定义文章页全局 CSS</td></tr><tr><td>script</td><td>用于自定义文章页全局 JavaScript</td></tr><tr><td>indexStyle</td><td>用于自定义首页 CSS</td></tr><tr><td>indexScript</td><td>用于自定义首页 JavaScript</td></tr><tr><td>showPostSource</td><td>设置为 1 则在文章页显示 issue 链接按钮，设置为 0 则不显示</td></tr><tr><td>rssSplit</td><td>设置 RSS 输出的截断符号，默认 sentence 为第一句话，可配置其他特殊符号</td></tr><tr><td>bottomText</td><td>用于设置文章页面右下角显示的内容</td></tr><tr><td>ogImage</td><td>用于设置 Open Graph 协议展示的图片</td></tr><tr><td>primerCSS</td><td>用于设置 primer.css 的 CDN 地址，默认使用南科大</td></tr><tr><td>needComment</td><td>用于设置是否需要评论功能，1 开启评论，0 关闭</td></tr></tbody></table>

Note

一般默认的配置文件修改后就可以了，无需额外添加！

### 3. 应用配置文件

进入`actions`界面，点击`build gmeek`，选择`run workflow`并点击

![](https://img.liyifan.xyz/file/6fc709491a266dee0d820.png)

等待一分钟左右直到完成

到此 Gmeek 博客搭建全部完成
-----------------

![](https://img.liyifan.xyz/file/6d96abb3b04bbf1c681f9.png)

Gmeek 博客基本使用方法
--------------

*   写、发文章：在`issues`里提交新 issue

> 必须至少包含一个`标签（lable）`

*   删除文章：关闭或删除对应 issue，然后在`action`中的`build gmeek`里`run workflow`
*   置顶文章：pin 文章对应的`issue`
*   标题目录列表：

```
<!-- ##{"script":"<script src='https://blog.liyifan.xyz/assets/GmeekTOC.js'></script>"}## -->


```

*   回到顶部按钮：

```
<!-- ##{"script":"<script src='https://blog.liyifan.xyz/assets/backtotop.js'></script>"}## -->


```

*   插入图片：

```
`Gmeek-html<img src="" alt="" width="100%">`


```

*   插入网易云外链播放器：

```
`Gmeek-html<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="100%" height="86" src="https//music.163.com/outchain/player?type=2&id=xxxxxxxx&auto=1&height=66"></iframe>`


```

*   插入视频：

```
`Gmeek-html<video src="" type="video/xxx" controls width="100%"></video>`
autoplay //自动播放
loop //循环播放
muted //静音
poster //第一帧加载之前的预览图

```