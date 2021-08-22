## Naive Security - 稚云安全

稚云安全是一款基于Bukkit API的安全验证工具，作者QQ[1733640981](http://wpa.qq.com/msgrd?v=3&uin=1733640981&site=qq&menu=yes)注明来意。

稚云安全平台的原理是：于Bukkit服务器启动时开放21017端口，与玩家使用的安全平台客户端通信；玩家的登录账户为玩家的UUID，安全密匙需在游戏中第一次手动设置，除配置文件外无法更改安全密匙；安全密匙采用MD5方式验证，不会直接暴露；全过程为Bukkit服务器与玩家客户端的连接，无任何连接外部网络的行为。

采用稚云安全平台可以实现：玩家知晓上次登录的时间和IP地址，用于判断账号是否被异常登录；定制插件时高危操作（如购买、使用特殊物品等）可以采用此平台进行二次验证，防止盗号产生的影响扩大；实现安全资产，与其他资产隔离。

### 开发API

调用静态方法简单实现验证平台客户端是否登录，调整安全资产

```api
所属类 com.hxzmmc.call.Client
1.0.0:
static boolean ifConnect(Player player)根据服务器数据判断玩家的安全客户端是否在线
static boolean ifConnect(String UUID)根据服务器数据判断玩家的安全客户端是否在线
1.1.0添加:
static void addMoney(.Player player, int Money)添加玩家安全资产数量
static void addMoney(String UUID, int Money)添加玩家安全资产数量
static int getMoney(Player player)获取玩家的安全资产数量
static int getMoney(String UUID)获取玩家的安全资产数量
static boolean hasKey(Player player)判断玩家是否设置安全密匙
static boolean hasKey(String UUID)判断玩家是否设置安全密匙
static boolean isEnough(Player player, int Money)判断玩家安全资产是否充足
static boolean isEnough(String UUID, int Money)判断玩家安全资产是否充足
static void setMoney(Player player, int Money)设置玩家安全资产数量
static void setMoney(String UUID, int Money)设置玩家安全资产数量
```

###已知问题

1.虽然支持1.8以上版本，但是可能是由于官方验证方法不同？或是其他原因，亲测1.8版本和1.12版本的同用户(我自己的/正版登录)UUID不同，所以尽量不要跨版本复制存档文件，前提是你已经确定前后版本的UUID相同

### Download

下载地址 [1.0.0](https://github.com/1733640981/1733640981.github.io/releases/tag/1.0.0) 支持1.12+
下载地址 [1.1.0](https://github.com/1733640981/1733640981.github.io/releases/tag/1.1.0) 支持1.8+
