<div align="center"><h1><img width="600" height="131" alt="68747470733a2f2f70616e2e73616d7979632e6465762f732f56596d4d5845" src="https://github.com/user-attachments/assets/d0316faa-c2d0-478f-a642-1e3c3651f1d4" /></h1></div>

<div class="section">
<div align="center"><h1>LaserTripmine for Swiftly2</h1></div>


<div align="center"><strong>基于 Swiftly2 框架开发的 CS2 激光绊雷插件。</p></div>

<div align="center"><strong>支持多种自定义配置。</p></div>
<div align="center"><strong>支持自定义模型,绊雷种类,伤害,激光攻击频率,爆炸范围,次数限制,金钱限制,管理员权限等。</p></div>
</div>

<div align="center">

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Z8Z31PY52N)
  

</div>

---

📦 创意工坊示例（激光绊雷 模型/音效等）


插件可结合以下创意工坊资源使用（示例）：
3618032051
```
要使用创意工坊资源,需要服务器安装metamod插件 multiaddonmanager 来管理服务器和玩家使用下载和安装创意工坊资源

安装multiaddonmanager插件后 在game\csgo\cfg\multiaddonmanager\multiaddonmanager.cfg配置文件中
 
找到第一行 mm_extra_addons  "3618032051"

把资源ID填写上去 等待服务器下载资源完毕 玩家进服会自动下载资源

之后用 Source2Viewer 软件 打开资源包 查看资源内的 模型路径与soundevent名字

之后根据需要填写到绊雷配置内使用
```
---

🧩 插件功能特色

支持 多种激光绊雷种类配置,多语言支持

支持 菜单选择激光绊雷创建  

支持激光绊雷两种类型 1. 发射激光,造成激光切割伤害 2.激光绊雷 触碰激光后引爆地雷 造成爆炸范围伤害

自定义菜单开启命令 (默认: sw_mine) 可进入配置内自己设置指令 用sw_ 开头

可自定义激光绊雷的各种属性,多重个性化选项

唯一名称(Name)

开关 (Enable) 模型(Model) 

类型(CanExplorer) → true 激光绊雷 false → 激光绊线

自我触发 CanOwnerTeamTrigger  → true 允许自己队伍的玩家触发地雷 false → 只允许敌对玩家触发地雷

```
激光绊线专属:

攻击频率 LaserRate  (0.1 = 每0.1秒攻击一次) 

自定义伤害 LaserDamage 击退 LaserKnockBack 
```

```
激光绊雷专属 :
爆炸范围 ExplorerRadius ExplorerDamage 爆炸伤害
```

队伍限制 Team (填写all 菜单所有队伍可见 填写ct只有ct能看到菜单内属于自己的激光绊雷)

价格 Price (填写 0 为免费 否则需要金钱购买)

限制 Limit (填写0为无限制创建,否则有创建限制)

管理员权限 Permissions (留空为不需要权限,否则需要权限才能创建)

透视外发光 GlowColor (留空为不设置外发光,否则根据rgba值设置外发光)

镭射光效 laserColor (绊线自定义颜色)

绊线尺寸粗细 laserSize (视觉效果)

激光绊雷放置音效 MineOpenSound (填写soundevent 来播放放置音效)

激光绊雷激光开始音效 LaserOpenSound (填写soundevent 来播放激光开始激活的音效)

激光绊线触发音效 LaserTouchSound (填写soundevent 来播放绊先触发时的伤害音效)

预缓存声音事件 PrecacheSoundEvent (填写声音事件文件可以用于预缓存)

模型方向修复 ModelAngleFix 如果 自定义模型角度不正确,可以设置角度让模型旋转

多种激光绊雷属性可自由扩展
---

🧱 配置示例（节选）可以自由设置不同激光绊雷属性
```
{
  "HanMineS2CFG": {
    "MineList": [
		{
			"Enable": true,
			"Name": "镭射激光绊线",
			"Model": "models/stk_sentry_guns/lasermine/stk_lasermines_one.vmdl",
			"CanExplorer": false,
			"LaserRate": 0.1,
			"LaserDamage": 10.0,
			"LaserKnockBack": 100.0,
			"ExplorerRadius": 250,
			"ExplorerDamage": 500,
			"Team": "ct",
			"Price": "0",
			"Limit": 0,
			"Permissions": "",
			"GlowColor": "0,255,0,255",
			"laserColor": "0,0,255,255",
			"laserSize": "1.0",
			"MineOpenSound": "n4a_csdm_sentry.mine_set",
			"LaserOpenSound": "n4a_csdm_sentry.mine_activate",
			"LaserTouchSound": "n4a_csdm_sentry.elrocket_lghtning",
			"PrecacheSoundEvent": "soundevents/n4a_csdm_sentry.vsndevts",
			"ModelAngleFix": "90.0"
		},
		{
			"Enable": true,
			"Name": "阔剑地雷(允许自我触发)",
			"Model": "models/stk_sentry_guns/lasermine/stk_lasermines_two.vmdl",
			"CanExplorer": true,
			"CanOwnerTeamTrigger": true,
			"LaserRate": 0.1,
			"LaserDamage": 10.0,
			"LaserKnockBack": 100.0,
			"ExplorerRadius": 250,
			"ExplorerDamage": 500,
			"Team": "ct",
			"Price": "0",
			"Limit": 0,
			"Permissions": "",
			"GlowColor": "255,0,0,255",
			"laserColor": "255,0,0,255",
			"laserSize": "0.5",
			"MineOpenSound": "n4a_csdm_sentry.mine_set",
			"LaserOpenSound": "n4a_csdm_sentry.mine_activate",
			"LaserTouchSound": "n4a_csdm_sentry.elrocket_lghtning",
			"PrecacheSoundEvent": "soundevents/n4a_csdm_sentry.vsndevts",
			"ModelAngleFix": "0"
		},
		{
			"Enable": true,
			"Name": "阔剑地雷(无法自我触发)",
			"Model": "models/stk_sentry_guns/lasermine/stk_lasermines_two.vmdl",
			"CanExplorer": true,
			"CanOwnerTeamTrigger": false,
			"LaserRate": 0.1,
			"LaserDamage": 10.0,
			"LaserKnockBack": 100.0,
			"ExplorerRadius": 500,
			"ExplorerDamage": 10000,
			"Team": "ct",
			"Price": "0",
			"Limit": 0,
			"Permissions": "",
			"GlowColor": "0,255,125,255",
			"laserColor": "0,255,0,255",
			"laserSize": "0.5",
			"MineOpenSound": "n4a_csdm_sentry.mine_set",
			"LaserOpenSound": "n4a_csdm_sentry.mine_activate",
			"LaserTouchSound": "n4a_csdm_sentry.elrocket_lghtning",
			"PrecacheSoundEvent": "soundevents/n4a_csdm_sentry.vsndevts",
			"ModelAngleFix": "0"
		}
	]
  }
}
```
---
CS2 LaserTripMine Plugin (Based on SwiftlyS2 Framework)
This plugin adds laser trip mines to Counter-Strike 2, built on the SwiftlyS2 framework.
It offers extensive customization and allows players to deploy various types of laser mines via a menu.

---

📦 Workshop Resource Example (LaserTripMine Model/Sound Effects, etc.)
The plugin can be used in conjunction with the following Workshop resources (example): Resource ID: 3618032051
```
To use Workshop content, the server must have the Metamod plugin "MultiAddonManager" installed to handle downloads.
After installation, edit the config file:
game\csgo\cfg\multiaddonmanager\multiaddonmanager.cfg

Locate the line:
mm_extra_addons "3618032051"

Add the Workshop ID and wait for the server to download it. Clients will automatically download the content upon joining.
Then, use Source2Viewer to inspect the addon and find model paths (.vmdl) and sound event names.
Fill them into the mine configuration as needed.
```
---
🧩 Laser Tripmine Plugin Features

Core Features

Supports multiple types of laser tripmines, fully configurable

Multi-language support

Create laser tripmines via menu selection

Supports two laser tripmine types:

Laser Beam Trap – Emits a laser beam that continuously deals cutting damage

Explosive Laser Tripmine – Triggers an explosion when the laser beam is touched, dealing area-of-effect damage

Menu & Commands

Customizable menu command

Default command: sw_mine

The command can be changed in the configuration

Must start with sw_

Customizable Tripmine Properties
General Settings

Name
Unique identifier for the tripmine

Enable
Enable or disable this tripmine

Model
Model used by the tripmine

Type (CanExplorer)

true → Explosive laser tripmine

false → Laser beam trap

CanOwnerTeamTrigger

true → Players on the owner’s team can trigger the tripmine

false → Only enemy players can trigger it

Laser Beam Trap (Laser Wire) Settings

LaserRate
Attack interval

Example: 0.1 = attacks every 0.1 seconds

LaserDamage
Damage dealt by the laser

LaserKnockBack
Knockback force applied to targets

Explosive Laser Tripmine Settings

ExplorerRadius
Explosion radius

ExplorerDamage
Explosion damage

Access & Restrictions

Team

all → Visible to all teams in the menu

ct → Only CT players can see and use this tripmine in the menu

Price

0 → Free

Any other value → Requires money to purchase

Limit

0 → Unlimited placements

Any other value → Placement limit

Permissions

Leave empty → No admin permission required

Set permission → Only players with the specified permission can create it

Visual Effects

GlowColor

Leave empty → No glow effect

Set RGBA values → Enables external glow effect

LaserColor
Custom color of the laser beam

LaserSize
Thickness of the laser beam (visual effect)

Sound Settings

MineOpenSound
Sound event played when placing the tripmine

LaserOpenSound
Sound event played when the laser becomes active

LaserTouchSound
Sound event played when the laser beam is triggered (damage hit)

PrecacheSoundEvent
Sound event file used for precaching

Model Adjustments

ModelAngleFix
If a custom model has incorrect orientation, this option can be used to rotate and fix the model angle

Extensibility

Supports easy expansion of additional laser tripmine attributes

Highly modular and customizable for future features
---
🧱 Configuration Example (Excerpt)

You can freely set different laser tripmine attributes:
```
{
  "HanMineS2CFG": {
    "MineList": [
		{
			"Enable": true,
			"Name": "镭射激光绊线",
			"Model": "models/stk_sentry_guns/lasermine/stk_lasermines_one.vmdl",
			"CanExplorer": false,
			"LaserRate": 0.1,
			"LaserDamage": 10.0,
			"LaserKnockBack": 100.0,
			"ExplorerRadius": 250,
			"ExplorerDamage": 500,
			"Team": "ct",
			"Price": "0",
			"Limit": 0,
			"Permissions": "",
			"GlowColor": "0,255,0,255",
			"laserColor": "0,0,255,255",
			"laserSize": "1.0",
			"MineOpenSound": "n4a_csdm_sentry.mine_set",
			"LaserOpenSound": "n4a_csdm_sentry.mine_activate",
			"LaserTouchSound": "n4a_csdm_sentry.elrocket_lghtning",
			"PrecacheSoundEvent": "soundevents/n4a_csdm_sentry.vsndevts",
			"ModelAngleFix": "90.0"
		},
		{
			"Enable": true,
			"Name": "阔剑地雷(允许自我触发)",
			"Model": "models/stk_sentry_guns/lasermine/stk_lasermines_two.vmdl",
			"CanExplorer": true,
			"CanOwnerTeamTrigger": true,
			"LaserRate": 0.1,
			"LaserDamage": 10.0,
			"LaserKnockBack": 100.0,
			"ExplorerRadius": 250,
			"ExplorerDamage": 500,
			"Team": "ct",
			"Price": "0",
			"Limit": 0,
			"Permissions": "",
			"GlowColor": "255,0,0,255",
			"laserColor": "255,0,0,255",
			"laserSize": "0.5",
			"MineOpenSound": "n4a_csdm_sentry.mine_set",
			"LaserOpenSound": "n4a_csdm_sentry.mine_activate",
			"LaserTouchSound": "n4a_csdm_sentry.elrocket_lghtning",
			"PrecacheSoundEvent": "soundevents/n4a_csdm_sentry.vsndevts",
			"ModelAngleFix": "0"
		},
		{
			"Enable": true,
			"Name": "阔剑地雷(无法自我触发)",
			"Model": "models/stk_sentry_guns/lasermine/stk_lasermines_two.vmdl",
			"CanExplorer": true,
			"CanOwnerTeamTrigger": false,
			"LaserRate": 0.1,
			"LaserDamage": 10.0,
			"LaserKnockBack": 100.0,
			"ExplorerRadius": 500,
			"ExplorerDamage": 10000,
			"Team": "ct",
			"Price": "0",
			"Limit": 0,
			"Permissions": "",
			"GlowColor": "0,255,125,255",
			"laserColor": "0,255,0,255",
			"laserSize": "0.5",
			"MineOpenSound": "n4a_csdm_sentry.mine_set",
			"LaserOpenSound": "n4a_csdm_sentry.mine_activate",
			"LaserTouchSound": "n4a_csdm_sentry.elrocket_lghtning",
			"PrecacheSoundEvent": "soundevents/n4a_csdm_sentry.vsndevts",
			"ModelAngleFix": "0"
		}
	]
  }
}
```
