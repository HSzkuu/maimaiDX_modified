# maimaiDX_modified

fork 自 https://github.com/Yuri-YuzuChaN/maimaiDX  

[static.zip](https://plugin-static.shizk.moe/static.zip)

## 新增功能：

r50 = Random Best50  
xl50(x=level) = Level Best50  
ap50 = AP Best50

以上功能需要查分器开发者token以进行使用

# maimaiDX


移植自 xybot 及 [mai-bot](https://github.com/Diving-Fish/mai-bot) 开源项目，基于 [HoshinoBotV2](https://github.com/Ice-Cirno/HoshinoBot) 的街机音游 **舞萌DX** 的查询插件

项目地址：https://github.com/Yuri-YuzuChaN/maimaiDX

## 重要更新

**2024-07-23**

1. 更新部分牌子完成表和 `SyncPlay` 图片，下载更新图片包 `Update.zip` 解压，将 `static` 复制到插件根目录并覆盖，即 `maimaiDX/static`。**如果怕缺少图片请进行[使用方法第二步](#使用方法)**
   - [私人云盘](https://share.yuzuchan.moe/d/aria/Update.zip?sign=PFnIZpgyB_HptU-hHIQ-S_qhuuGTNDlmEEtmaEpmJlA=:0)
   - [onedrive](https://yuzuai-my.sharepoint.com/:u:/g/personal/yuzuchan_yuzuai_onmicrosoft_com/EcFTIQemNF9NlNQj8RZSdhABiV64tFi-X8-8a7JKxfEKJQ?e=P5nPnx)
2. 修复 `新增机厅` 指令 `id` 未增加的问题
3. 修复 `牌子进度` 指令 `sync` 未匹配的问题

## 使用方法

1. 将该项目放在HoshinoBot插件目录 `modules` 下，或者clone本项目
   
    ``` git
    git clone https://github.com/Yuri-YuzuChaN/maimaiDX
    ```
   
2. 下载静态资源文件，将该压缩文件解压后，将 `static` 文件夹复制到插件根目录并覆盖，即 `maimaiDX/static`
   - [私人云盘](https://share.yuzuchan.moe/d/aria/Resource.zip?sign=LOqwqDVm95dYnkEDYKX2E-VGj0xc_JxrsFnuR1BcvtI=:0)
   - [onedrive](https://yuzuai-my.sharepoint.com/:u:/g/personal/yuzuchan_yuzuai_onmicrosoft_com/EaS3jPYdMwxGiU3V_V64nRIBk6QA5Gdhs2TkJQ2bLssxbw?e=Mm6cWY)
3. 如果您拥有查分器的开发者 `token`，可修改 `maimaiDX/static/config.json` 文件，将 `token` 填入文件
4. 安装插件所需模块：`pip install -r requirements.txt`
5. 在 https://phantomjs.org/download.html 下载对应操作平台PhantomJS支持，`windows` 平台需要添加环境目录
6. 在 `config/__bot__.py` 模块列表中添加 `maimaiDX`
7. 重启HoshinoBot

## 指令

| 命令                                             | 功能                            |
|------------------------------------------------|-------------------------------|
| 帮助maimaiDX                                     | 查看指令帮助                        |
| 今日舞萌                                           | 查看今天的舞萌运势                     |
| XXXmaimaiXXX什么                                 | 随机一首歌                         |
| 随个[dx/标准][绿黄红紫白]<难度>                           | 随机一首指定条件的乐曲                   |
| 查歌<乐曲标题的一部分>                                   | 查询符合条件的乐曲                     |
| id<歌曲编号>                                | 查询乐曲信息或谱面信息                   |
| <歌曲别名>是什么歌                                     | 查询乐曲别名对应的乐曲                   |
| <id/歌曲别称>有什么别称                                 | 查询歌曲别名                        |
| 添加本地别名 <歌曲ID> <歌曲别名>                         | 添加本地别名，不上传别名服务器         |
| 添加别称 <歌曲ID> <歌曲别名>                             | 申请添加歌曲别名                      |
| 当前别名投票 <页数>                                        | 查看正在进行的投票                     |
| 同意别名 <标签>                                      | 同意其中一个标签的别名申请，可通过指令 当前别名投票 查看 |
| 开启/关闭别名推送                                      | 开启或关闭新别名投票的推送                 |
| 定数查歌 <定数> 定数查歌 <定数下限> <定数上限>                   | 查询定数对应的乐曲                     |
| 分数线 <难度+歌曲id> <分数线>                            | 展示歌曲的分数线                      |
| 开启/关闭mai猜歌                                     | 开关猜歌功能                        |
| 重置猜歌                                            | 停止当前进行的猜歌                  |
| 猜歌                                             | 顾名思义，识别id，歌名和别称               |
| 猜曲绘                                            | 猜曲绘                                |
| minfo<@> <id/别称/曲名>                            | 查询单曲成绩                        |
| ginfo[绿黄红紫白] <id/别称/曲名>                        | 查询乐曲游玩总览，不加难度默认为紫谱         |
| b50 <游戏名>                                      | 查询b50                         |
| 我要在<难度>上<分数>分 <游戏名>                            | 查看推荐的上分乐曲                     |
| 我要(在<难度>)上<分数>分 <名字>                           | 查看推荐的上分乐曲                     |
| <牌子名称>进度 <名字>                                  | 查看牌子完成进度                      |
| <等级><评价>进度 <名字>                                | 查看等级评价完成进度                    |
| <等级> 分数列表 <名字>                                 | 查看等级评价列表                      |
| 查看排名,查看排行 <页数>/<名字>                            | 查看水鱼网站的用户ra排行                 |
| 添加机厅 <店名> <位置> <机台数量>                     | 添加机厅信息                        |
| 删除机厅 <店名>                                      | 删除机厅信息                        |
| 修改机厅 <店名> 数量 <数量>                           | 修改机厅信息                        |
| 订阅机厅 <店名>                                      | 订阅机厅，简化后续指令                   |
| 查看订阅                                           | 查看群组订阅机厅的信息                   |
| 取消订阅,取消订阅机厅                                    | 取消群组机厅订阅                      |
| 添加机厅别名 <店名> <别名>                                | 添加机厅别名                      |
| 查找机厅,查询机厅,机厅查找,机厅查询 <关键词>                      | 查询对应机厅信息                      |
| <店名/别名>人数设置,设定,增加,加,+,减少,减,-<人数>                  | 操作排卡人数                        |
| <店名/别名>有多少人,有几人,有几卡,几人,几卡                         | 查看排卡人数                        |
| 全局[关闭/开启]别名推送                               | Bot管理员私聊指令，开关所有群的别名推送   |
| 更新别名库                                            | Bot管理员私聊指令，手动更新别名库   |
| 更新maimai数据                                            | Bot管理员私聊指令，手动更新已存所有数据  |

## 更新说明

**2024-07-24**

1. 更新部分牌子完成表和 `SyncPlay` 图片
2. 修复 `新增机厅` 指令 `id` 未增加的问题
3. 修复 `牌子进度` 指令 `sync` 未匹配的问题
4. 修复 `别名查歌` 指令查询到已删除的曲目时发生错误的问题

**2024-06-07**

1. 更新至 `舞萌DX 2024`
2. 更换所有图片绘制，需删除除 `json` 后缀的所有文件，**请重新进行使用方法第二步**
3. 更改部分 `json` 文件名称，便于识别，具体文件如下，**请务必修改文件名，否则开关文件以及本地别名文件将不会被读取**
   - `all_alias.json`    修改为 `music_alias.json`
   - `local_alias.json`  修改为 `local_music_alias.json`
   - `chart_stats.json`  修改为 `music_chart.json`
   - `group_alias.json`  修改为 `group_alias_switch.json`
   - `guess_config.json` 修改为 `group_guess_switch.json`
4. 新增管理员私聊指令 `更新完成表`，用于更新 `BUDDiES` 版本 `双系` 牌子
5. 新增指令 `完成表`，可查询牌子完成表，例如：`祝极完成表`
6. 新增指令 `猜曲绘`
7. 查看谱面支持计算个人加分情况，指令包括 `是什么歌`，`id`
8. 指令 `mai什么` 支持随机发送推分谱面，指令中需包含 `加分`，`上分` 字样，例如：`今日mai打什么上分`
9.  修改指令 `分数列表` 和 `进度` 发送方式
10. 优化所有模块

**2024-03-12**

1. 变更别名服务器地址
2. 修改所有别名请求以及参数
3. 开放普通用户申请别名

**2024-01-14**

1. 优先使用本地谱面
2. 使用 `numpy` 模块重新绘制定数表

**2023-09-23**

1. 重写 `API` 方法
2. 重写机厅模块
3. 将同步生成定数表方法修改为异步方法，防止堵塞进程
4. 将 `当前别名投票` 发送方式修改为图片形式
5. 本地添加别名单独存储为一个文件，不再添加在暂存别名文件中

**2023-08-10**

1. 新增后缀指令 `定数表`，`完成表`，查询指定等级的定数表和完成表，例如：`13+完成表`
2. 新增BOT管理员私聊指令 `更新定数表`，用于生成和更新定数表
3. 新增BOT管理员私聊指令 `更新maimai数据`，用于版本更新手动更新bot已存数据
4. 拆分并移除 `maimaidx_project.py` 的代码和文件，便于所有功能维护
5. 修复曲绘不存在时下载错误的问题
6. 修复猜歌提前发出答案的bug
7. 修改指令 `minfo` 部分绘图

**2023-06-15**

1. 新增添加本地别名的功能

**2023-06-09**

1. 更新至 `舞萌DX 2023`
2. 移除指令 `b40`
3. 更换静态资源
4. 修改指令 `b50` 部分绘图

**2023-04-22**

1. 限制所有网络请求时长
2. 新增别名文件本地备份
3. 新增ginfo指令默认使用紫谱数据

**2023-04-21**

1. 新增BOT管理员私聊指令 `全局关闭别名推送` 和 `全局开启别名推送`，关闭所有群的推送消息，无论先前开启还是关闭
2. 修复新版本更新后API暂未收录曲目的问题
3. 新增乐曲游玩总览 `ginfo` 指令
4. 新增猜歌库根据乐曲游玩次数添加
5. 新增每日更新机厅信息，删除旧版更新机厅机制

**2023-04-15**

1. 将获取数据的方式由启动Bot时获取改为连接到CQHTTP后获取
2. 修复因查分器API内容变动而无法启动Bot的问题

**2023-03-29**

1. 重制 `b40/b50` ，`minfo` 和曲目信息的绘图
2. 修改投票网页端，改成共用网站
3. 修改垃圾代码

**2023-03-02**

1. 新增 `开启别名推送` 和 `关闭别名推送` 指令

**2023-02-25**

1. 修复猜歌答对后无法结束的问题

**2023-02-23**

1. 投票网页端

**2023-02-22**

1. 修复启动BOT时无法获取所有曲目信息的问题，添加本地缓存
2. 修改别名库，使用API获取和添加，并同步所有使用该插件的BOT
3. 修改猜歌和别名功能
4. 新增指令 `当前别名投票` 和 `同意别名`

**2023-2-18**

1. 别称同步临时解决方案 #47

**2023-2-15**

1. 更新本地缓存水鱼网数据 #43

**2022-9-14**

1. 新增查询单曲指令 `minfo`
2. 修改查曲绘图

**2022-8-30**

1. 修复新版b40/b50 isinstance bug [#38](https://github.com/Yuri-YuzuChaN/maimaiDX/issues/38)
2. 修复新版b40/b50 找不到图片问题
3. 修复安慰分隐性bug

**2022-08-27**

1. 修复b40/b50小数点后四位错误的问题

**2022-08-25**

1. 修复猜歌模块发送曲绘时为未知曲绘的问题

**2022-08-16**

1. 修改 `b40/b50` 指令绘图，如不喜欢请将 `libraries/maimaidx_project.py` 第`6`行 `maimai_best_50` 改成 `maimai_best_40`
2. 修改查曲绘图

**2022-07-11**

1. 修复指令 `分数列表` 没有提供2022谱面的问题

**2022-06-23**

1. 支持2022
2. 修改所有曲绘后缀
3. 修改获取在线文件的路径

**2022-03-10**

1. 新增段位显示，感谢 [Kurokitu](https://github.com/Kurokitu) 提供源码及资源

**2022-02-13**

1. 修复部分新曲没有难易度参考的问题

**2022-01-27**

1. 修复添加/删除别名无效的问题

**2022-01-16**

1. 修复b40/b50查询@Ta人情况下无效的问题

**2022-01-03**

1. 修改获取音乐数据的函数，不在使用同步进程
2. 不再使用正则表达式获取@人员的QQ号
3. 不再使用CQ码方式发送图片
4. 修改大部分源码

**2021-11-15**

1. 在请求获取maimaiDX数据的函数添加 `@retry` 装饰器，遇到请求数据失败的情况时重新尝试请求

**2021-10-18**

1. 添加排卡功能，感谢 [CrazyKid](https://github.com/CrazyKidCN)

**2021-10-14**

1. 更新查看推荐的上分乐曲
2. 更新查看牌子完成进度
3. 更新查看等级评价完成进度
4. 查看水鱼网站的用户ra排行

**2021-09-29**

1. 更新b50、乐曲推荐功能，感谢 [BlueDeer233](https://github.com/BlueDeer233) 

**2021-09-13** 

1. 更新猜歌功能以及开关，感谢 [BlueDeer233](https://github.com/BlueDeer233) 


## 鸣谢

感谢 [zhanbao2000](https://github.com/zhanbao2000) 提供的 `nonebot2` 分支

感谢 [CrazyKid](https://github.com/CrazyKidCN) 提供的源码支持

感谢 [Diving-Fish](https://github.com/Diving-Fish) 提供的源码支持

感谢 [BlueDeer233](https://github.com/BlueDeer233) 提供猜歌功能的源码支持

## License

MIT

您可以自由使用本项目的代码用于商业或非商业的用途，但必须附带 MIT 授权协议。
