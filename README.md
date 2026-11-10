# blg-cheer · BLG 应援许愿树

为 BLG 3:1 战胜 T1 晋级 S16 决赛而做的应援网站。决赛倒计时 + 夜色许愿大树 + 选手打CALL，单文件 HTML，零构建零依赖，数据存云端——明年回来看，牌子和声波都还在。

> 🎮 **在线试玩（国内直连）**：<https://blg-cheer.app.workbuddy.host/?sharecode=Z4HISPH5CZ>
>
> 🌐 **GitHub Pages**：<https://johnnysilverhandv.github.io/blg-cheer/>
>
> 📦 **离线版下载**：[GitHub Releases](https://github.com/JohnnySilverhandV/blg-cheer/releases) ｜ [码云 Releases](https://gitee.com/johnny-silver-hand123/blg-cheer/releases)

## 源码仓库

| 平台 | 地址 |
|---|---|
| GitHub | https://github.com/JohnnySilverhandV/blg-cheer |
| Gitee（国内镜像） | https://gitee.com/johnny-silver-hand123/blg-cheer |

## 功能

### ⏱ 决赛倒计时

- 对阵：**BLG（LPL） vs GEN（LCK）**
- 时间：北京时间 2026 年 11 月 15 日 03:00 · 纽约布鲁克林巴克莱中心
- 直观格式「xx天xx时xx分xx秒」，开赛后自动切换为应援模式

### 🌳 许愿大树

- 纯 SVG 手绘夜色场景：月亮星子、远山、金灯、萤火虫、发光蘑菇
- 应援牌挂在树梢随风轻摆，阵营配色区分：
  - **BLG 牌**：青蓝 #3CC0E6 木牌 + 右上角一枚粉色圆晕 #F96D9C（按队标取色）
  - **GEN 牌**：对角线一半黄一半黑
- 点「挂上我的应援牌」弹窗选阵营、写内容，确定后挂上树
- **每台设备限 1 块牌，可随时修改**（数据库唯一索引防注水）
- **15 日决赛之后**页面出现金色「回来还愿」按钮，点一下给牌子盖「已还愿」金印

### 📣 选手打CALL

- BLG 六人：Bin / Flandre（双上单）、Xun、Knight、Viper、ON
- GEN 五人：Kiin、Canyon、Chovy、Ruler、Duro
- 点选手名卡即发一次声波 +1，声波数实时累计存云端
- 每台设备每天 10 次，零点重置，页面常驻显示今日剩余

### 🛡 文明用语与反垃圾（双层过滤）

- **数据库层**（真正的安全边界）：PostgreSQL 触发器，脏词词表 + 正则（亲人称呼类骂人、中英文脏话、拉长变体）+ 网址黑名单（防色情/赌博引流），INSERT 和 UPDATE 全拦
- **前端层**（友好体验）：同源词库提交前预检，红字提示、内容保留可改
- 自家站点域名白名单，转发应援站链接不会被误伤

## 技术

- 单文件 `index.html`（HTML + CSS + JS），无框架、无构建
- 云数据库（WorkBuddy 云服务），公开读 + 受控写，RLS 行级安全策略
- 打CALL计数用数据库聚合函数，许愿按设备 ID 唯一约束

## 文件

```
index.html   完整页面（HTML + CSS + JS，单文件，无构建、无依赖）
README.md    本文件
LICENSE      MIT 许可证
```

## 🆕 更新日志

### v1.0 — 首发：决赛倒计时 + 许愿大树 + 选手打CALL（2026-11-09）

- 决赛倒计时（BLG vs GEN，巴克莱中心）
- 许愿大树：挂牌 / 改牌 / 还愿金印，每设备 1 块防注水
- 选手打CALL：11 名选手声波计数，每设备每天 10 次
- 文明用语双层过滤（脏词 + 亲人称呼正则 + 英文词边界匹配）
- 网址黑名单防引流（自家域名白名单）

## License

MIT 许可证，详见 [LICENSE](LICENSE)。

## 版权申明

本站所有视觉素材（树、徽章、应援牌等）均为自制 SVG/CSS 绘制，未使用任何官方图片素材。「League of Legends」及「Worlds」相关名称与商标权利归 Riot Games 所有，本站为粉丝自制应援页面，与 Riot Games、BLG、GEN 及各赛区官方无隶属关系。
