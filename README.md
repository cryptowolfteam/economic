# NFT狼人杀经济模型

## 1.牌组介绍

NFT狼人杀卡牌牌面分为：平民，狼人，女巫，预言家，猎人和守卫。每张单牌是ERC1155代币，即同
一张牌可有有多份拷贝在流通

一组完整的套牌为：
| 类型  | 个数 |
| -----|:-----:|
| 平民  | 4 |
| 狼人  | 4 |
| 女巫  | 1 |
| 预言家 | 1 |
| 猎人  | 1 |
| 守卫  | 1 |

一组套牌是一个ERC721代币

## 2.参与者

艺术家：为牌面作画，命名，如创造“平民——马一龙”牌面。
委员会：审核艺术家上传的牌面信息
收藏者：收藏单牌或者把单牌组合成牌组的收藏家

## 3.代币种类以及创造销毁

- 系统中代币分为：ERC20狼币， ERC1155牌面， ERC721牌组
- 艺术家需要消耗狼币数目C来创造牌面，牌面和名称提交给委员会审核，如果审核成功，0.9C的狼币被销毁，0.1C奖励给参与
本牌面审核的委员，同时mint出ERC1155牌面给艺术家，牌面上限为M个。如失败则全额退回。
- 牌面可以在市场流通，也可以赠与，标准ERC1155接口
- 收藏者可以收藏牌面，也可以通过收集相应数目的牌面来组成牌组。在牌组中，每个牌的牌面名称都不同。每个牌组独一无二。
例如：

| 类型  | 牌面 |
| -----|:-----:|
| 平民  | 马一龙，乔帮主，中本聪，V神 |
| 狼人  | 马爸爸，麻花藤，小渣，水掉哥头 |
| 女巫  | 乔治·马丁 |
| 预言家 | 梅丽珊卓 |
| 猎人  | 席恩 |
| 守卫  | 囧恩 |


- 收集一个牌组，锁定12张ERC1155，mint出ERC721牌组，同时奖励狼币数目B，这个操作成为封印。封印牌组可看作挖矿行为
- 假设某时刻系统中有40不同平民牌面，40狼人，10女巫，10预言，10猎人，10守卫，那么一共有
`((40*39*38*37)/(4*3*2))**2 * 10**4 = 83521321000000` 种组合。
- 可以拆散牌组重新变成12张单牌，这个操作叫解封。再次封印相同阵容，不会有狼币奖励

## 4.系统初始状态

- 初始供给50%归开发团队，50%用来社区推广，提供给早期参与的艺术家制作牌面的费用。其余的狼币，牌面，牌组都是后续创造和挖出来的。
