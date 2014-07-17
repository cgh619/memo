#by chen
#今天想搭建自己的博客，记录自己的足迹。

创新新分支：memo

blog首页：index.html文件
	它的Yaml文件头表示，首页使用default模板，标题为"我的Blog"。然后，首页使用了{% for post in site.posts %}，表示对所有帖子进行一个遍历。这里要注意的是，Liquid模板语言规定，输出内容使用两层大括号，单纯的命令使用一层大括号。至于{{site.baseurl}}就是_config.yml中设置的baseurl变量。
blog设置文件:_config.yml 文本文件.
存放模板的文件夹:_layouts
	Blog的默认模板：default.html
存放blog文章的目录：_posts
	文件名必须为"年-月-日-文章标题.后缀名"的格式。如果网页代码采用html格式，后缀名为html；如果采用markdown格式，后缀名为md。
	每篇文章的头部，必须有一个yaml文件头，用来设置一些元数据。它用三根短划线"---"，标记开始和结束，里面每一行设置一种元数据。"layout:default"，表示该文章的模板使用_layouts目录下的default.html文件；"title: 你好，世界"，表示该文章的标题是"你好，世界"，如果不设置这个值，默认使用嵌入文件名的标题，即"hello world"。
	在yaml文件头后面，就是文章的正式内容，里面可以使用模板变量。{{ page.title }}就是文件头中设置的"你好，世界"，{{ page.date }}则是嵌入文件名的日期（也可以在文件头重新定义date变量），"| date_to_string"表示将page.date变量转化成人类可读的格式。
Liquid模板语言链接：http://jekyllrb.com/docs/configuration/

发布内容

先把所有内容加入本地git库。
　　$ git add .
　　$ git commit -m "备注信息”
上传到网站可以用github客户的sync同步到github服务端。

访问：https://cgh619.github.com/memo
