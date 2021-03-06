
# 前言
> 前段时间在给 Jekyll 博客加了音乐后，浏览文章确实舒服多了，但又感觉文章只能图文混排，没有图片的地方就像一片荒原没有一丝色彩，寻思着能不能再增加点什么元素，比如小表情什么的，不如先从我们日常的 Emoji 开始吧！


![textemoji](/img/in-post/2018-1-20-Emoji/textemoji.png)

# 添加 Emoji 表情

Jekyll 页面本身并不支持插入 Emoji 表情，好在 Jekyll 支持插件拓展。通过这个插件系统，你可以根据自己网站的需求来自定义地创建一些功能。基于插件系统的自定义代码可以在不修改 Jekyll 源码的情况下运行自定义的功能。

从这个思路切入，很自然地想到通过 Emoji 插件来实现 Jekyll 网页对 Emoji 的兼容。通过在 [RubyGems](https://rubygems.org/gems) 上对关键词 ```Emoji Jekyll``` 进行检索，发现已经有3个能够实现这一功能的插件。

![relevent Emoji](/img/in-post/2018-1-20-Emoji/releventEmoji.png)

我试用了下载量大的 ```jemoji``` 和 ```Emoji for Jekyll``` ，都能够完美实现 Jekyll 对 Emoji 的兼容。下面以 [jemoji](https://rubygems.org/gems/jemoji) 为例，来看教程吧。

![jemoji](/img/in-post/2018-1-20-Emoji/jemoji.png)


# Emoji 插件安装

这里推荐 3 种方式来安装插件：

#### **方法一**
使用以下语句安装 ```jemoji``` 插件
```
gem install jemoji
```

接着在网页根目录的 ```_config.yml``` 文件中添加名为 ```plugins``` 的列表 (当 Jekyll 版本低于 ```3.5.0``` 时用 ```gems``` ) 和对应需要使用的插件名。举个例子：

```
# For Jekyll < 3.5.0
# This will enable each of these plugins automatically.
plugins:
gems: [jekyll-paginate, jemoji]
```

```
# For Jekyll >= 3.5.0
# This will enable each of these plugins automatically.
plugins:
  - jekyll-paginate
  - jemoji
```

#### **方法二**
如果遇到用 **方法一** 中用语句 ```gem install jemoji``` 直接安装 ```jemoji``` 插件时一直没反应的情况，那么可以直接到 [RubyGems](https://rubygems.org/gems) 中搜索 ```jemoji``` ，在 [jemoji](https://rubygems.org/gems/jemoji) 页面的右下角下载 ```*.gem``` 文件

![downloadJemoji](/img/in-post/2018-1-20-Emoji/downloadjemoji.png)

再以引用路径的形式执行安装 (手机端显示不全可左右滑动查看)

```
# Use the file path and name
gem install C:\Users\Aaron\Desktop\jemoji-0.9.0.gem
```

归结起来应该是什么说不清楚的网络问题吧。完成上述安装后同样需要添加 ```plugins``` 列表，具体参加 **方法一** 。


#### **方法三**
该方法针对 ```*.rb``` 插件文件。

在你的网页文件根目录下新建一个名为 ```_plugins``` 的文件夹，将你下载的 ```*.rb``` 插件文件放入该文件夹，那么 Jekyll 在生成你的网页时会自动加载该文件夹内的所有插件

# Jekyll 中 Emoji 的使用方法

Jekyll 中 Emoji 采用与 [YouTube](https://youtube.com/) ， [Ruby China](http://ruby-china.org/) 等网站相同的通用引用方法，用冒号包裹简单的英文单词来引用 Emoji，如下表：

<style>
#emoji
img{margin: 0}
</style>

<table id="emoji" class="table table-bordered table-striped table-condensed">
	<thead>
		<tr>
			<th>Emoji</th>
			<th>Code</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td align="center"> :smile: </td>
			<td align="center"> <code>:smile:</code> </td>
		</tr>
		<tr>
			<td align="center"> :heart_eyes: </td>
			<td align="center"> <code>:heart_eyes:</code> </td>
		</tr>
		<tr>
			<td align="center"> :sweat_smile: </td>
			<td align="center"> <code>:sweat_smile:</code> </td>
		</tr>
		<tr>
			<td align="center"> :kissing_heart: </td>
			<td align="center"> <code>:kissing_heart:</code> </td>
		</tr>
    <tr>
			<td align="center"> :imp: </td>
			<td align="center"> <code>:imp:</code> </td>
		</tr>
		<tr>
			<td align="center"> :alien: </td>
			<td align="center"> <code>:alien:</code> </td>
		</tr>
		<tr>
			<td align="center"> :muscle: </td>
			<td align="center"> <code>:muscle:</code> </td>
		</tr>
    <tr>
			<td align="center"> :snowman: </td>
			<td align="center"> <code>:snowman:</code> </td>
		</tr>
    <tr>
			<td align="center"> :ship: </td>
			<td align="center"> <code>:ship:</code> </td>
		</tr>
		<tr>
			<td align="center"> :rocket: </td>
			<td align="center"> <code>:rocket:</code> </td>
		</tr>
		<tr>
			<td align="center"> :cn: </td>
			<td align="center"> <code>:cn:</code> </td>
		</tr>
    <tr>
			<td align="center"> :bird: </td>
			<td align="center"> <code>:bird:</code> </td>
		</tr>
  </tbody>
</table>

从表上看， Emoji 和对应的 Code 的关联性还是相当大的，记住几个常用的 Emoji 不是什么难事，你甚至可以直接凭空敲出 Code 来碰碰运气，我试了好几个简单的单词都成功得到对应的 Emoji。

但去记忆或者凭空想出来确实不是长久之计，这里给大家推荐一个 Emoji
神器—— [EMOJI CHEAT SHEET](https://www.webpagefx.com/tools/emoji-cheat-sheet/) ，正如它的名字一样，这个网站按类目收录了所有的 Emoji 及其对应的 Code ，可以方便的在上面查找想要的 Emoji。

<center>~ &nbsp;一起来作弊吧&nbsp; ~</center>
:smirk:


# 参考

1. [Emoji for Jekyll as a Ruby Gem](http://www.yihangho.com/emoji-for-jekyll-as-a-ruby-gem/)

2. [RubyGems](https://rubygems.org/gems)

3. [Jekyll document - Plugins](https://jekyllrb.com/docs/plugins/)

4. [EMOJI CHEAT SHEET](https://www.webpagefx.com/tools/emoji-cheat-sheet/)


<center>- Over -</center>
