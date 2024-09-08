# 管理员基础入门

## 环境要求

- 1.20.1 及以上；
- Spigot、Paper、Folia...；
- Java 21 及以上；

> 虽然本插件支持 Spigot 但是我们强烈推荐您升级到 Paper 或其分支核心（如 Purpur）以获得更好的性能体验。

## 安装方法

1. 将插件放入服务器的 `plugins` 目录下
2. 重启服务器
3. 在 `plugins/Dominion/config.yml` 中配置

## 权限节点

| 功能     | 权限节点             | 默认   |
|--------|------------------|------|
| 普通玩家指令 | dominion.default | true |
| 管理员指令  | dominion.admin   | op   |

## 玩家“滥发消息”导致被踢

由于本插件使用TUI作为交互方式，因此会与玩家客户端之间产生大量消息。而 spigot 增加了滥发消息保护，因此默认情况下当玩家快速操作界面时大概率会被踢出服务器。

![](https://ssl.lunadeer.cn:14437/i/2024/05/17/664723d8a3477.png)

解决办法为在 `spigot.yml` 配置文件中将本插件命令的消息设置为白名单：

```
...
commands:
  ...
  spam-exclusions:
  - /dom
  - /dominion
```

## 安装本插件后原来可以飞行现在飞不了

如果你安装了一些飞行相关的插件，在打开 flags 中的领地飞行后可能会遇到其他飞行插件不生效的问题。

这些问题包括但不限于：无法起飞、进入领地后“坠机”、离开领地时“坠机”等。

解决办法为在配置文件中添加对应插件的权限节点：

```
# 飞行权限节点 - 拥有以下任意一个权限节点的玩家不会被本插件拦截飞行
FlyPermissionNodes:
  - essentials.fly
  - cmi.command.fly
```

拥有此列表中任意一个权限节点的玩家不会被本插件拦截飞行行为。