---
title: 哔哩哔哩的 API 接口
layout: page
---

这里收集 B 站所有无需 appkey 和 appsecret 的 API。

<p class=yousa>合理调用，不要频繁发送请求，以免被识别成机器。</p>

<p class=yousa>【注意】B 站的静态图片资源（i*.hdslb.com 等域）做了根据 referer 进行跨站请求判断的机制，从非白名单 referer 请求图片会报 403 错误。一些 API 似乎也有此限制。你需要在请求头中写明 Referer 的值为 https://www.bilibili.com 。</p>

不得不吐个槽！！你看 B 站多大度！API 从不搞稀奇古怪的跳转验证加 cookie！除了耗流量的静态资源为了防盗链才做了个 js！！反观某浪！！简直就是耍流氓！！渣浪再这样封闭下去，早晚得给作死

### 稿件相关

**通过 av 号（aid）获得对应的稿件分段（cid）。** 可以向如下地址发送 GET 请求：

`https://api.bilibili.com/x/player/pagelist?aid={aid}&jsonp=jsonp`

返回结果（以 [av11586438](https://www.bilibili.com/video/av11586438/) 为例）：

```json
{"code":0,"data":[{"cid":19147671,"page":1,"from":"vupload","part":"第1话  传说的少女","duration":1407,"vid":"","weblink":""},{"cid":19147700,"page":2,"from":"vupload","part":"第2话  朱雀的巫女","duration":1406,"vid":"","weblink":""},{"cid":19147672,"page":3,"from":"vupload","part":"第3话  朱雀七星","duration":1407,"vid":"","weblink":""},{"cid":19147666,"page":4,"from":"vupload","part":"第4话  没有交集的思绪","duration":1407,"vid":"","weblink":""},{"cid":19147679,"page":5,"from":"vupload","part":"第5话  迷惘的心","duration":1407,"vid":"","weblink":""},{"cid":19147680,"page":6,"from":"vupload","part":"第6话  就算牺牲自己","duration":1407,"vid":"","weblink":""},{"cid":19147673,"page":7,"from":"vupload","part":"第7话  归心似箭","duration":1393,"vid":"","weblink":""},{"cid":19147655,"page":8,"from":"vupload","part":"第8话  想见到你","duration":1403,"vid":"","weblink":""},{"cid":19147674,"page":9,"from":"vupload","part":"第9话  看不见的敌人","duration":1407,"vid":"","weblink":""},{"cid":19147681,"page":10,"from":"vupload","part":"第10话  被囚禁的少女","duration":1406,"vid":"","weblink":""},{"cid":19147659,"page":11,"from":"vupload","part":"第11话  青龙的巫女","duration":1407,"vid":"","weblink":""},{"cid":19147667,"page":12,"from":"vupload","part":"第12话  只有你","duration":1407,"vid":"","weblink":""},{"cid":19147656,"page":13,"from":"vupload","part":"第13话  因为爱","duration":1407,"vid":"","weblink":""},{"cid":19147682,"page":14,"from":"vupload","part":"第14话  碉堡之狼","duration":1407,"vid":"","weblink":""},{"cid":19147675,"page":15,"from":"vupload","part":"第15话  复活之乡","duration":1407,"vid":"","weblink":""},{"cid":19147701,"page":16,"from":"vupload","part":"第16话  悲哀的战斗","duration":1407,"vid":"","weblink":""},{"cid":19147687,"page":17,"from":"vupload","part":"第17话  邂逅之音","duration":1407,"vid":"","weblink":""},{"cid":19147657,"page":18,"from":"vupload","part":"第18话  恋慕的陷阱","duration":1407,"vid":"","weblink":""},{"cid":19147660,"page":19,"from":"vupload","part":"第19话  被撕裂的爱","duration":1407,"vid":"","weblink":""},{"cid":19147668,"page":20,"from":"vupload","part":"第20话  没希望的愿望","duration":1407,"vid":"","weblink":""},{"cid":19147702,"page":21,"from":"vupload","part":"第21话  为了保护你","duration":1406,"vid":"","weblink":""},{"cid":19147692,"page":22,"from":"vupload","part":"第22话  再也不分离","duration":1407,"vid":"","weblink":""},{"cid":19147676,"page":23,"from":"vupload","part":"第23话  谋略的预兆","duration":1339,"vid":"","weblink":""},{"cid":19147669,"page":24,"from":"vupload","part":"第24话  火焰的决心","duration":1406,"vid":"","weblink":""},{"cid":19147677,"page":25,"from":"vupload","part":"第25话  爱与悲伤","duration":1407,"vid":"","weblink":""},{"cid":19147658,"page":26,"from":"vupload","part":"第26话  星见祭之夜","duration":1407,"vid":"","weblink":""},{"cid":19147678,"page":27,"from":"vupload","part":"第27话  墓前的誓言","duration":1407,"vid":"","weblink":""},{"cid":19147662,"page":28,"from":"vupload","part":"第28话  古昔之旅","duration":1406,"vid":"","weblink":""},{"cid":19147693,"page":29,"from":"vupload","part":"第29话  开始行动之谜","duration":1407,"vid":"","weblink":""},{"cid":19147683,"page":30,"from":"vupload","part":"第30话  战争的闪光","duration":1406,"vid":"","weblink":""},{"cid":19147663,"page":31,"from":"vupload","part":"第31话  不安的漩涡","duration":1406,"vid":"","weblink":""},{"cid":19147703,"page":32,"from":"vupload","part":"第32话  朱雀的星宿殉难了","duration":1407,"vid":"","weblink":""},{"cid":19147694,"page":33,"from":"vupload","part":"第33话  柳宿永远的别离","duration":1407,"vid":"","weblink":""},{"cid":19147696,"page":34,"from":"vupload","part":"第34话  冰的防人","duration":1406,"vid":"","weblink":""},{"cid":19147684,"page":35,"from":"vupload","part":"第35话  奈落的海市蜃楼","duration":1407,"vid":"","weblink":""},{"cid":19147688,"page":36,"from":"vupload","part":"第36话  被蹂躏的爱","duration":1407,"vid":"","weblink":""},{"cid":19147695,"page":37,"from":"vupload","part":"第37话  幻惑的温情","duration":1325,"vid":"","weblink":""},{"cid":19147690,"page":38,"from":"vupload","part":"第38话  心的黎明","duration":1394,"vid":"","weblink":""},{"cid":19147664,"page":39,"from":"vupload","part":"第39话  妖惑的幻觉","duration":1407,"vid":"","weblink":""},{"cid":19147697,"page":40,"from":"vupload","part":"第40话  虚伪的爱","duration":1407,"vid":"","weblink":""},{"cid":19147652,"page":41,"from":"vupload","part":"第41话  复活的阳光","duration":1407,"vid":"","weblink":""},{"cid":19147665,"page":42,"from":"vupload","part":"第42话  无法越过的阻碍","duration":1407,"vid":"","weblink":""},{"cid":19147685,"page":43,"from":"vupload","part":"第43话  诀别的到来","duration":1407,"vid":"","weblink":""},{"cid":19147689,"page":44,"from":"vupload","part":"第44话  刹那的攻防","duration":1407,"vid":"","weblink":""},{"cid":19147653,"page":45,"from":"vupload","part":"第45话  分歧之光","duration":1407,"vid":"","weblink":""},{"cid":19147654,"page":46,"from":"vupload","part":"第46话  虚实的少年","duration":1407,"vid":"","weblink":""},{"cid":19147661,"page":47,"from":"vupload","part":"第47话  镇魂之空","duration":1407,"vid":"","weblink":""},{"cid":19147698,"page":48,"from":"vupload","part":"第48话  牺牲自己也在所不惜","duration":1407,"vid":"","weblink":""},{"cid":19147699,"page":49,"from":"vupload","part":"第49话  华烛之典","duration":1407,"vid":"","weblink":""},{"cid":19147670,"page":50,"from":"vupload","part":"第50话  赎罪的瞬间","duration":1407,"vid":"","weblink":""},{"cid":19147691,"page":51,"from":"vupload","part":"第51话  被托付的希望","duration":1407,"vid":"","weblink":""},{"cid":19147686,"page":52,"from":"vupload","part":"第52话  为了心爱的人","duration":1388,"vid":"","weblink":""}],"message":"0","ttl":1}
```

> 为啥选这个视频？→视频刚好有分 p 而已……

cid → 分段对应的唯一 ID

page → 第几 P

part → 分 P 的名称

duration → 分段的长度（秒）

**获取稿件基本信息。** 以 <https://www.bilibili.com/video/av8086541> 为例，向以下地址发送 GET 请求：

`https://api.bilibili.com/x/article/archives?ids={aid}&jsonp=jsonp`

返回数据如下:

```json
{"code":0,
  "data":{
    "8086541":
    {"aid":8086541,
      "videos":1,
      "tid":28,
      "tname":"原创音乐",
      "copyright":1,
      "pic":"http://i1.hdslb.com/bfs/archive/54472f950e8b0aa8e245589e8330bf9e1fd6f9d1.jpg",
      "title":"【泠鸢·原创】泼墨漓江【玖玲】【茜色诗集】",
      "pubdate":1484755580,
      "ctime":1497413947,
      "desc":"#茜色诗集#收录曲【伴奏】http://pan.baidu.com/s/1i5qhL5r  乐师联动绫依版：av8088191\n非常开心能找到玖玲合作！往后希望也能够出更多好作品，谢谢冥凰一如既往的帮助，不知道我是不是也有机会去一次漓江~\nSTAFF众多无法写下，详见PV\n#茜色诗集#【专辑相关资讯请看：】http://qr07.cn/B6G1TJ",
      "state":0,
      "attribute":49152,
      "duration":306,
      "rights":{
        "bp":0,
        "elec":0,
        "download":0,
        "movie":0,
        "pay":0,
        "hd5":0,
        "no_reprint":0},
        "owner":{
          "mid":282994,
          "name":"泠鸢yousa",
          "face":"http://i0.hdslb.com/bfs/face/3cd9998cdb9444528a4e62ed2b4e69d64282dbeb.jpg"},
          "stat":{
            "aid":8086541,
            "view":478942,
            "danmaku":4452,
            "reply":3424,
            "favorite":36764,
            "coin":35600,
            "share":5500,
            "now_rank":0,
            "his_rank":17,
            "like":124},
            "dynamic":""}},
          "message":"0",
          "ttl":1}
```

<p class=yousa>中文部分可能含有正则表达式语法，需要额外处理。</p>

data → 数据

data > videos → 视频分 P 数量

data > tid → 分区编号（用于机器识别）

data > tname → 分区名称

data > pic → 封面 URL

data > title → 稿件标题

data > pubdate → 发布时间（UNIX 时间戳）

data > ctime → （UNIX 时间戳）

data > desc → 视频描述

data > state → 稿件状态，0 表示正常

data > duration → 视频时间总长（秒）

data > owner → UP 主

data > owner > mid → UP 主个人空间号

data > owner > name → UP 主昵称

data > owner > face → UP 主头像

data > stat → 视频统计信息

data > stat > view → 视频播放数

data > stat > danmaku → 弹幕数合计

data > stat > reply → 评论数

data > stat > favorite → 收藏数

data > stat > coin → 硬币数

data > stat > share → 分享数

data > stat > now_rank → 稿件当前排名

data > stat > his_rank → 稿件全站最高日排行

你也可以用这个返回较为简单的接口：

`https://api.bilibili.com/archive_stat/stat?aid={aid}&type=jsonp&_=1482889080665`

返回结果如下：

```json
{"code":0,
  "data":
  {"aid":7248433,
    "view":14691978,
    "danmaku":1663567,
    "reply":10643,
    "favorite":69346,
    "coin":226356,
    "share":8786,
    "now_rank":0,
    "his_rank":2,
    "like":860,
    "no_reprint":0,
    "copyright":1},
    "message":"0",
    "ttl":1}
```

data > like → 稿件推荐数（刚上线不久）

**通过番剧地址获得 aid、番剧信息和分段信息（cid）。** 以 <https://bangumi.bilibili.com/anime/6421#114928> 为例，先观察列表中各话的 URL，GET 请求如下地址：

`https://bangumi.bilibili.com/web_api/episode/{episodeid}.json`

（ `episodeid` 是 URL 中井号后面的数）

返回如下结果：

```json
{"code":0,
  "message":"success",
  "result":{
    "season":{
      "cover":"http://i0.hdslb.com/bfs/bangumi/a65418c77579dfe5ac361b8aaec28906da7044ac.jpg",
      "season_title":"第二季",
      "title":"阿松 第二季",
      "version":"tv"},
    "upInfo":{
      "face":"http://i0.hdslb.com/bfs/face/69ef6861067d6ef637b7c73b77d71c3414996745.jpg",
      "mid":21453565,
      "sign":"テレビ東京",
      "uname":"TV-TOKYO",
      "vip":{
        "vipStatus":0,
        "vipType":2}},
      "upVipInfo":{
        "vipStatus":0,
        "vipType":2},
      "currentEpisode":{
        "avId":"14989419",
        "bangumiTitle":"",
        "cover":"http://i1.hdslb.com/bfs/archive/b5a2cbdc033e62597677b3396470ebcdd8c676f1.jpg",
        "danmaku":"24417385",
        "episodeId":114928,
        "index":"1",
        "indexTitle":"1",
        "isDelete":"0",
        "longTitle":"复活 阿松",
        "mid":"21453565",
        "page":"1",
        "pubDate":"2017-10-03",
        "pubTime":"",
        "published":"1",
        "push":"1",
        "seasonId":6421,
        "status":2,
        "weekday":-1}}}
```

code → 稿件状态

cover → 番剧封面 URL

season-title → 该季的名称

title → 番剧的名称

version → TV 动画/OVA 等

upInfo → 上传者信息

upinfo > face → 头像

upinfo > mid → 个人空间地址

upinfo > sign → 个性签名

upinfo > uname → 用户昵称

upinfo > vip → 大会员

currentEpisode > avId → 该 P 对应的 AV 号

currentEpisode > cover → 视频封面 URL

currentEpisode > danmaku → 和视频 cid 保持一致

currentEpisode > episodeId → 和 URL 中的 episodeid 保持一致

currentEpisode > index → 分 P 编号（用于机器识别）

currentEpisode > indexTitle → 分 P 编号（用于屏幕显示）

currentEpisode > isDelete → 是否为删除

currentEpisode > LongTitle → 分 P 名称文字

currentEpisode > pubDate → 上线时间

currentEpisode > seasonId → 所在的番剧号（URL 中 anime 后面的号）

### 用户相关

**通过用户个人空间号（mid）获得详细信息。** （这个 API 居然在哔哩哔哩的动态里！）GET 请求如下地址：

`https://api.bilibili.com/cardrich?mid={mid}`

获得响应如下：

```json
{
  "code": 0,
  "data": {
    "card": {
      "mid": "282994",
      "name": "泠鸢yousa",
      "approve": true,
      "sex": "女",
      "rank": "10000",
      "face": "http://i2.hdslb.com/bfs/face/3cd9998cdb9444528a4e62ed2b4e69d64282dbeb.jpg",
      "DisplayRank": "1041",
      "regtime": 1325487597,
      "spacesta": 2,
      "birthday": "2016-05-19",
      "place": "四川省 成都市",
      "description": "bilibili 知名UP主",
      "article": 0,
      "attentions": [
        97329145,
        34149649,
        7875104,
        6813499,
        1885078,
        55762711,
        26283835,
        310709,
        139905,
        12444306,
        837019,
        1269948,
        168598,
        374377,
        777536,
        1998535,
        342646,
        1467772,
        883968,
        2970476,
        2019740,
        2728123,
        5669526,
        4790659,
        585267,
        15312,
        103835,
        2648
      ],
      "fans": 890996,
      "friend": 28,
      "attention": 28,
      "sign": "【个人专辑TB搜:茜色诗集】泠ling鸢yuan本人认可‘冷鸟’为昵称~【微博@泠鸢yousa】",
      "level_info": {
        "current_level": 6,
        "current_min": 28800,
        "current_exp": 1398313,
        "next_exp": "-"
      },
      "pendant": {
        "pid": 0,
        "name": "",
        "image": "",
        "expire": 0
      },
      "nameplate": {
        "nid": 8,
        "name": "知名偶像",
        "image": "http://i0.hdslb.com/bfs/face/27a952195555e64508310e366b3e38bd4cd143fc.png",
        "image_small": "http://i2.hdslb.com/bfs/face/0497be49e08357bf05bca56e33a0637a273a7610.png",
        "level": "稀有勋章",
        "condition": "所有自制视频总播放数>=100万"
      },
      "official_verify": {
        "type": 0,
        "desc": "bilibili 知名UP主"
      },
      "vip": {
        "vipType": 0,
        "vipDueDate": 0,
        "dueRemark": "",
        "accessStatus": 1,
        "vipStatus": 0,
        "vipStatusWarn": ""
      }
    },
    "space": {
      "s_img": "http://i0.hdslb.com/bfs/space/768cc4fd97618cf589d23c2711a1d1a729f42235.png",
      "l_img": "http://i0.hdslb.com/bfs/space/cb1c3ef50e22b6096fde67febe863494caefebad.png"
    }
  },
  "message": "0",
  "ttl": 1
}
```

regtime → 注册时的 UNIX 时间戳

### BLive 相关

**获得哔哩哔哩动态详情。** GET 如下地址：

`https://api.vc.bilibili.com/dynamic_svr/v1/dynamic_svr/get_dynamic_detail?dynamic_id={dynamic_id}`

响应如下：

```json
{
  "code": 0,
  "msg": "",
  "message": "",
  "data": {
    "card": {
      "desc": {
        "uid": 927587,
        "type": 8,
        "rid": 17403962,
        "acl": 0,
        "view": 0,
        "repost": 6,
        "like": 83,
        "dynamic_id": 63493197324135090,
        "timestamp": 1513621562,
        "pre_dy_id": 0,
        "orig_dy_id": 0,
        "orig_type": 0,
        "user_profile": {
          "info": {
            "uid": 927587,
            "uname": "木鱼水心",
            "face": "https://i1.hdslb.com/bfs/face/696df59d35c78430f1a0bdb6184558e7b7eb4a6e.jpg",
            "rank": "10000",
            "mobile_verify": 0,
            "platform_user_level": 6,
            "official_verify": {
              "type": -1,
              "desc": ""
            }
          },
          "card": {
            "official_verify": {
              "type": -1,
              "desc": ""
            }
          },
          "live_info": {
            "title": "木鱼水心的直播间",
            "room_id": 310773,
            "uid": 927587,
            "online": 0,
            "live_time": "-62170012800",
            "live_status": 2
          }
        },
        "stype": 0
      },
      "card": "{ \"aid\": 17403962, \"videos\": 1, \"tid\": 182, \"tname\": \"影视杂谈\", \"copyright\": 1, \"pic\": \"https:\\/\\/i2.hdslb.com\\/bfs\\/archive\\/d424ff77471ee60c49778c47de3dd44750ac0e4e.jpg\", \"title\": \"【木鱼微剧场】《垫底辣妹》\", \"pubdate\": 1513621562, \"ctime\": 1513621562, \"desc\": \"《垫底辣妹》和许多日本同类的文艺作品一样，把努力和青春用最单纯最直接的方式来表现，讲述了一个最最简单的主题，那就是，别在事情发生之前，就把自己的全部可能性抹去，去尝试，去努力，总会有收获。不怕失败，勇于挑战梦想的力量，才是最耀眼的青春。\", \"state\": 0, \"attribute\": 49280, \"duration\": 955, \"rights\": { \"bp\": 0, \"elec\": 0, \"download\": 0, \"movie\": 0, \"pay\": 0, \"hd5\": 0, \"no_reprint\": 1 }, \"owner\": { \"mid\": 927587, \"name\": \"木鱼水心\", \"face\": \"https:\\/\\/i1.hdslb.com\\/bfs\\/face\\/696df59d35c78430f1a0bdb6184558e7b7eb4a6e.jpg\" }, \"stat\": { \"aid\": 17403962, \"view\": 3523, \"danmaku\": 141, \"reply\": 386, \"favorite\": 76, \"coin\": 229, \"share\": 20, \"now_rank\": 0, \"his_rank\": 0, \"like\": 44 }, \"dynamic\": \"【木鱼微剧场】《垫底辣妹》和许多日本同类的文艺作品一样，把努力和青春用最单纯最直接的方式来表现，讲述了一个最最简单的主题，那就是，别在事情发生之前，就把自己的全部可能性抹去，去尝试，去努力，总会有收获。不怕失败，勇于挑战梦想的力量，才是最耀眼的青春。\" }"
    },
    "result": 0,
    "_gt_": 0
  }
}
```

在 card 中，去掉所有的转义字符 “\\”就可以把这个字段变成标准的 json 了。

**获得动态转发列表。** GET 请求如下地址：

```json
{
  "code": 0,
  "msg": "",
  "message": "",
  "data": {
    "has_more": false,
    "comments": [
      {
        "uid": 19462115,
        "comment": "转发动态",
        "ts": 1513623726,
        "face_url": "https://i1.hdslb.com/bfs/face/458f4481b09125943400ee172976a6cf42cd2834.jpg",
        "uname": "Forever丿思念灬",
        "rp_dyn_id": 63502491631266984,
        "ctrl": "[]"
      },
      {
        "uid": 21068165,
        "comment": "转发动态",
        "ts": 1513623481,
        "face_url": "https://i1.hdslb.com/bfs/face/aca7a440ab56231a3f878cce87d24b38b4df2823.jpg",
        "uname": "故衿233",
        "rp_dyn_id": 63501439365327980,
        "ctrl": ""
      },
      {
        "uid": 1486210,
        "comment": "转发动态",
        "ts": 1513623456,
        "face_url": "https://i0.hdslb.com/bfs/face/9645f23c0d54fb2b51228e31f3915b89493bc52f.jpg",
        "uname": "雲哥_",
        "rp_dyn_id": 63501331992194150,
        "ctrl": "[]"
      },
      {
        "uid": 8947155,
        "comment": "在考研的最后一周，因为生物钟已经乱掉一个多月，在看到看到片尾默默的哭了，真是感同身受。谢谢木鱼大大能做这类的影评，我会尽力的",
        "ts": 1513623313,
        "face_url": "https://i0.hdslb.com/bfs/face/379e243eb98d9ba09d5725e385498e402c975938.jpg",
        "uname": "JN吃肉",
        "rp_dyn_id": 63500717811870780,
        "ctrl": ""
      },
      {
        "uid": 169195979,
        "comment": "如果怀疑自己的努力是否会成功，那就用行动去验证吧，时间会告诉你答案。",
        "ts": 1513623186,
        "face_url": "https://i2.hdslb.com/bfs/face/a076329348d82164c3f54598ee90239c17817d21.jpg",
        "uname": "气死小懒",
        "rp_dyn_id": 63500172351024160,
        "ctrl": ""
      },
      {
        "uid": 10319358,
        "comment": "转发动态",
        "ts": 1513622579,
        "face_url": "https://static.hdslb.com/images/member/noface.gif",
        "uname": "泰泰泰健康",
        "rp_dyn_id": 63497565304826790,
        "ctrl": ""
      }
    ],
    "total_count": 6,
    "_gt_": 0
  }
}
```



### 弹幕相关

**获得视频稿件的弹幕（XML 格式）。** 可以向如下地址发送 GET 请求：

- 获取历史时间戳：`https://comment.bilibili.com/rolldate,{cid}`

- 获取相应时间戳之间的历史弹幕：`https://comment.bilibili.com/dmroll,{timestamp},{cid}`

- 获取当前弹幕池：`https://comment.bilibili.com/{cid}.xml`

<p><span class=yousa>XML 下载后可能需要做 deflate 解压。</span><a href = https://www.crifan.com/set_accept_encoding_header_to_gzip_deflate_return_messy_code/ target=\_blank>处理方法</a></p>

弹幕 XML 解释

- maxlimit：弹幕池上限
- chatid：和视频 cid
- p 第一位：弹幕出现的时间，单位秒
- p 第二位：弹幕类型。1~3 - 普通 4 - 底部 5 - 顶部 6 - 逆向 7 - 精准定位 8 - 高级弹幕
- p 第四位：颜色，十进制
- p 第五位：unix 时间戳
- p 第六位：弹幕池类型，默认 0
- p 第七位：发送者 id（彩虹表加密）
- p 第八位：弹幕 id（即为要记录的 danmaku_uid）

**获得直播的实时弹幕（动态更新的 JSON）。** 向地址

`https://live.bilibili.com/ajax/msg`

发送表单，其中的项为 `roomid` ，值为主播的房间号。

<p class=yousa>有些主播直播间的 URL 和房间号不一致。你可能需要手动获取 roomid。</p>

请参见知乎上的这个[实现](https://zhuanlan.zhihu.com/p/21360141)（Python）。

### 其他

**获取视频推荐。** 获取有关某个视频的推荐视频。向以下地址发送 GET 请求：

`https://api.bilibili.cn/author_recommend?aid={aid}`

结果如下：

```json
{"code":0,
  "list":[{
    "aid":15770997,
    "title":"\u3010\u6ce0\u9e22\u3011\u4ea4\u7ec7together\u3010\u5355\u4eba\u7248\u3011",
    "cover":"https:\/\/i0.hdslb.com\/bfs\/archive\/0eb6f509d9c332a35ec1b601836eb25ab52335f7.jpg",
    "click":162341,"review":1717,"favorites":8469,"video_review":1579},{
    "aid":15519586,
    "title":"\u3010\u6ce0\u9e22\u3011\u7384\u9cb8\u4e4b\u8a93",
    "cover":"https:\/\/i1.hdslb.com\/bfs\/archive\/f891fe01e6e74e4372c35729205767a872902cb0.jpg",
    "click":211526,
    "review":2991,
    "favorites":13324,
    "video_review":1981},
  {
    "aid":14816615,
    "title":"\u3010FGO\u5468\u5e74\u5e86\u3011\u8272\u5f69-\u6ce0\u9e22\u7ffb\u5531",
    "cover":"https:\/\/i2.hdslb.com\/bfs\/archive\/5687e2680e7722344b09d60ab1b1267d54c9f0bb.jpg",
    "click":213991,
    "review":2601,
    "favorites":7163,
    "video_review":1838},
  {
    "aid":14927846,
    "title":"\u3010\u6ce0\u9e22\u00b7\u539f\u521b\u3011\u5c0f\u4e11\u7684\u54c1\u683c\u3010\u602a\u76d7V\u3001Leon\u3011\u3010\u831c\u8272\u8bd7\u96c6\u3011",
    "cover":"https:\/\/i1.hdslb.com\/bfs\/archive\/920c5173cbc86d1f2694c469684f917dbb9f5eb4.jpg",
    "click":277356,
    "review":3121,
    "favorites":23018,
    "video_review":2586},
  {
    "aid":14047368,
    "title":"1.\u3010\u6ce0\u9e22\u3011\u4f60\u66fe\u662f\u5c11\u5e74 MV\u3010\u5f00\u5b66\u8981\u52b1\u5fd7\u3011",
    "cover":"https:\/\/i0.hdslb.com\/bfs\/archive\/a2038725f6c4a41bf4d032844d5fa3d8d4554d63.jpg",
    "click":468301,
    "review":4412,
    "favorites":21401,
    "video_review":6709},
  {
    "aid":13203642,
    "title":"\u3010\u53d6\u7ecf\u8ba1\u5212\u00b7\u539f\u521b\u3011\u65b0\u00b7\u4e5d\u4e5d\u516b\u5341\u4e00\u3010\u6ce0\u9e22\u3011",
    "cover":"https:\/\/i1.hdslb.com\/bfs\/archive\/353bc71791f4661a126ac470ca30d7a59ea8ac6e.jpg",
    "click":2607532,
    "review":21189,
    "favorites":237321,
    "video_review":40778},
  {
    "aid":12187193,
    "title":"\u3010\u6ce0\u9e22\u3011\u6211\u7684\u4e16\u754c\u5df2\u5760\u5165\u7231\u6cb3\u3010AMV\u6388\u6743\u4f7f\u7528\u3011",
    "cover":"https:\/\/i1.hdslb.com\/bfs\/archive\/e7fcd23a3f178df26c3804b1faffe287b317d4b1.jpg",
    "click":371137,
    "review":3759,
    "favorites":20221,
    "video_review":4536},
  {
    "aid":11567945,
    "title":"\u3010\u6ce0\u9e22\u3011\u5728\u5ead\u56ed\u4e2d\u3002",
    "cover":"https:\/\/i2.hdslb.com\/bfs\/archive\/769944b5062ca60f9cb3d162bca1bf2b1cfe2c08.jpg",
    "click":363306,
    "review":3468,
    "favorites":24415,
    "video_review":2801},
  {
    "aid":10983593,
    "title":"\u3010\u6ce0\u9e22\u3011\u91d1\u9c7c\u59ec\u306e\u68a6\u60f3\u3010\u516d\u4e00\u7279\u4f9b\u3011\u3010\u7edf\u6cbb\u4e16\u754c\u4e0d\u53ea\u662f\u8bf4\u8bf4\u800c\u5df2\uff01\u3011",
    "cover":"https:\/\/i1.hdslb.com\/bfs\/archive\/1d83e0ee16ab3eab6ad8dd3a0ec32c810e22f036.jpg",
    "click":235943,
    "review":2146,
    "favorites":11054,
    "video_review":2291},
  {
    "aid":10848989,
    "title":"\u3010\u6ce0\u9e22\u00b7\u539f\u521b\u3011\u4e61\u60c5\u66f2\u3010\u76d6\u76d6\u3011\u3010\u831c\u8272\u8bd7\u96c6\u3011",
    "cover":"https:\/\/i2.hdslb.com\/bfs\/archive\/4c8f1fdd5bfc8e74c2585ae9c7fca69bfdd7719f.jpg",
    "click":229787,
    "review":1962,
    "favorites":10947,
    "video_review":2171},
  {
    "aid":10193446,
    "title":"\u3010\u6ce0\u9e22\u00b7\u4eba\u58f0\u672c\u5bb6\u3011\u68a6\u60f3\u82ad\u83f2\u2606",
    "cover":"https:\/\/i2.hdslb.com\/bfs\/archive\/86e2d5395208c71b0f0afd1b197dae4e0eff0937.jpg",
    "click":183790,
    "review":2459,
    "favorites":6046,
    "video_review":1675},
  {
    "aid":9760079,
    "title":"\u3010\u6ce0\u9e22\u3011\u5c11\u5e74\u4e0e\u5200",
    "cover":"https:\/\/i2.hdslb.com\/bfs\/archive\/36c229151d3129cc0bf337e451485632beda592e.jpg",
    "click":253594,
    "review":2143,
    "favorites":10613,
    "video_review":1384},
  {
    "aid":9383750,
    "title":"\u3010\u6ce0\u9e22\u3011\u7a9d\u8981\u5ba3\u674e\u767d[\u901f\u5f55\u7ffb\u5531-\u674e\u767d]",
    "cover":"https:\/\/i1.hdslb.com\/bfs\/archive\/b4647f86e1086f84b5a02a0b908dc0661e3390b4.jpg",
    "click":363387,
    "review":2942,
    "favorites":13587,
    "video_review":3873},
  {
    "aid":9201285,
    "title":"\u5e73\u5b89\u5947\u5999\u7269\u8bed\u3010\u6ce0\u9e22yousa\/KBShinya\/\u7948Inory\/\u4f51\u53ef\u732b\/\u7384\u89de\/\u4e91\u306e\u6ce3\/\u5947\u7136\/Mario\u3011\u966a\u4f34\u662f\u552f\u4e00\u7684\u7948\u613f",
    "cover":"https:\/\/i2.hdslb.com\/bfs\/archive\/9d0f2551c52d0e201bdcd546367c25883fafacd3.jpg",
    "click":319649,
    "review":2095,
    "favorites":26611,
    "video_review":5660},
  {
    "aid":9098914,
    "title":"\u3010\u6ce0\u9e22\u00b7\u4e1c\u4eac\u5854\u3011\u82b1\u5934\u53f0",
    "cover":"https:\/\/i0.hdslb.com\/bfs\/archive\/b824f460efbe3ed3f61f970a5e2a64cc3fe6ee88.jpg",
    "click":180776,
    "review":1873,
    "favorites":9701,
    "video_review":1275},
    {
      "aid":8825394,
      "title":"\u3010\u7956\u5a05\u00b7\u6ce0\u9e22\u00b7\u6d1b\u8431\u3011\u4e07\u795e\u7eaa\u3010\u4e09\u4eba\u7ffb\u5531\u3011",
      "cover":"https:\/\/i2.hdslb.com\/bfs\/archive\/afd03456c709e7bda3762498f5e542e8eac955d8.png",
      "click":440170,
      "review":2904,
      "favorites":25343,
      "video_review":3884},
    {
      "aid":8673782,
      "title":"\u3010\u6ce0\u9e22\u3011\u9189\u3010\u5ae3\u6c50\u66f2\u7ffb\u5531-\u4f4e\u97f3\u7ec3\u4e60\u4e2d\u2026\u3011",
      "cover":"https:\/\/i1.hdslb.com\/bfs\/archive\/1edf369fff93aa4fe2d6da5e364a4446de14a73e.jpg",
      "click":429323,
      "review":2975,
      "favorites":27328,
      "video_review":3394}]}
```

<p class=yousa>这里的返回值目测含有正则表达式语法，可能需要稍作处理。</p>

aid → AV 号

title → 视频标题（ASCII 格式）

cover → 封面 URL

click → 点击数

review → 弹幕数

favorites → 收藏数

video_review → 评论数

<p style="color:lightgrey">bilibili、哔哩哔哩是上海幻电信息科技有限公司的注册商标。</p>
