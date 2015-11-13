# 饭否精选 API 列表

## About
- 此 API 由 rex 提供。文档由 Anthonyeef 整理而成。
- 08:00 发每日精选；周一 08:00 发每周精选；
- 内容由机器自动抓取；如有侵权，或您的信息不愿公开，请向[.rex](http://fanfou.com/zhasm) 申诉~
- 请把该 API 用在有趣的事情上 :) Don't do evil.

## 调用方法
该 API 全部的调用方法均为 `GET`

## API list

在 http://blog.fanfou.com/digest/json/index.json 可以获取全部的 API 地址列表。该地址返回值为 JSON 格式。举例：

```
[
"./json/2015-11-13.daily.json",
"./json/2015-11-12.daily.json",
"./json/2015-11-11.daily.json",
"./json/2015-11-10.daily.json",
"./json/2015-11-09.weekly.json",
"./json/2015-11-09.daily.json",
]
```

- Base url 为 `http://blog.fanfou.com/digest`。 Base url + 上面列表中的 Api 地址部分，即得到完整的 API 地址。例如：
` http://blog.fanfou.com/digest/json/2015-11-13.daily.json`.
- 列表中的 Api 分成 `daily` 和 `weekly` 两类。 `daily` 地址返回的是「每日精选」，`weekly` 地址返回的是「每周精选」。
- 能够获取到的 Api 数据从 `2015-10-05` 开始。因目前数据较少，故从`2015-10-05` 开始的精选数据会全部保留。

## Daily
`Daily` API 返回的数据为 JSON 格式。举例：

```
{
	shift: "daily",
	shift_cn: "每日",
	date: "2015-11-13",
	msgs: [
	{
	id: "188976923",
	count: "20",
	realname: "梁京",
	loginname: "liangjing116",
	avatar: "http://avatar1.fanfou.com/s0/00/ad/vs.jpg?1423455425",
	time: "2015-11-12 21:50",
	statusid: "iuxDcg-tO04",
	msg: "在无数自拍中选出满意的，精心 ps 发到朋友圈；在平庸的生活中找到微微闪光之处拍下，发到朋友圈… 不必否认，有些人的信心与快乐就来自于点赞和评论。我曾在心中嘲笑佯装生活丰富实则和我一般贫瘠的人的虚荣，现在想想又有什么可嘲笑的呢？在重复与厌倦中摇摆的生命，需要幻象，需要迷醉，需要不清醒。",
	img: {
		preview: "",
		page: ""
		}
}
``` 
- `shift`项是分类，返回值可以是 `daily` 或者 `weekly`。
- `shift_cn`：如字面所示。
- `msgs`：返回的是该期精选的全部内容。下面做详细说明：
	- `id`:该饭否er的唯一 id。
	- `count`：该条饭否的收藏次数。机器收集饭否精选的依据即是在饭否上的被收藏次数。实际上 API 返回的饭否条目也是以此为依据排序。
	- realname: 昵称
	- loginname: 如字面所示
	- avatar: 饭否er 的头像。该地址返回的是略缩图。如果需要品质稍好的头像图，可以手动将返回地址中的 `s0` 替换成 `l0`。如 `http://avatar1.fanfou.com/s0/00/ad/vs.jpg?1423455425` --> `http://avatar1.fanfou.com/l0/00/ad/vs.jpg?1423455425`。
	- statusid: 该条饭否的唯一 id
	- msg: 该条饭否的文字内容
	- img:该条饭否的图片内容
		- preview: 图片的略缩图地址。如果需要得到品质较好的大图，可以手动将返回地址中的`m0` 换成 `n0` 即可。例如：`http://mtmos.com/v1/mss_3d027b52ec5a4d589e68050845611e68/ff/m0/0c/2t/me_31976.jpg` --> `http://mtmos.com/v1/mss_3d027b52ec5a4d589e68050845611e68/ff/n0/0c/2t/me_31976.jpg`
		- page: 该图在饭否上的页面地址。

## Weekly
与 `daily` 内容相近。 
