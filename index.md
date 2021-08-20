## Naive Security - 稚云安全

稚云安全是一款基于Bukkit API的安全验证工具，作者QQ[1733640981](http://wpa.qq.com/msgrd?v=3&uin=1733640981&site=qq&menu=yes)注明来意。

稚云安全平台的原理是：于Bukkit服务器启动时开放21017端口，与玩家使用的安全平台客户端通信；玩家的登录账户为玩家的UUID，安全密匙需在游戏中第一次手动设置，除配置文件外无法更改安全密匙；安全密匙采用MD5方式验证，不会直接暴露；全过程为Bukkit服务器与玩家客户端的连接，无任何连接外部网络的行为。
采用稚云安全平台可以实现：玩家知晓上次登录的时间和IP地址，用于判断账号是否被异常登录；定制插件时高危操作（如购买、使用特殊物品等）可以采用此平台进行二次验证，防止盗号产生的影响扩大；预计下个版本中实现安全资产，与其他资产隔离，同样需要安全平台验证才可交易。

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/1733640981/NaiveSafety.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
