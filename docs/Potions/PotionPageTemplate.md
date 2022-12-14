# 朱雀之魂
![朱雀之魂](../Img/Texture2D_Potion/朱雀之魂.png)
## 简介
## 圣物效果
#### **核心**  
- 造成伤害时：有<font color=gray>10%</font>/<font color=BlueViolet>15%</font>/<font color=gold>20%</font>的几率发射朱雀之炎对敌人造成<font color=gray>40%</font>/<font color=BlueViolet>50%</font>/<font color=gold>70%</font>火焰伤害</color>。每层圣物精炼效果会有额外<font color=gray>3%</font>/<font color=BlueViolet>4%</font>/<font color=gold>5%</font>的几率追加一次发射。(追加发射几率：每次精炼<font color=gray>3%</font>/<font color=BlueViolet>4%</font>/<font color=gold>5%</font>)

- 怒气达到100时：获得朱雀之赐，使你的所有伤害提高<font color=gray>30%</font>/<font color=BlueViolet>45%</font>/<font color=gold>60%</font>，每秒对周围的敌人造成攻击力<font color=gray>70%</font>/<font color=BlueViolet>90%</font>/<font color=gold>120%</font>点火焰伤害，持续5秒。
#### **力量** 
- 造成伤害时：额外造成相当于你攻击力<font color=gray>3%</font>/<font color=BlueViolet>3%</font>/<font color=gold>5%</font>的真实伤害。
- 你每拥有1层圣物精炼效果会使该技能的额外伤害提高<font color=gray>0%</font>/<font color=BlueViolet>1%</font>/<font color=gold>1.5%</font>。  
#### **敏捷**
- 每拥有1层圣物精炼效果，移动速度提高<font color=gray>0.5%</font>/<font color=BlueViolet>0.75%</font>/<font color=gold>1%</font>。
- <font color=bloeviolet>移动速度加成的50%会转化为攻击速度提高。</font>
#### **功效**
- 你每拥有1层圣物精炼效果，使你的防御提高<font color=gray>0.5%</font>/<font color=BlueViolet>0.75%</font>/<font color=gold>1%</font>。
- <font color=bloeviolet>当你生命低于20%时，防御加成提高翻倍。</font>
- <font color=gold>使你获得传说圣物的几率提高5%。</font>

## 圣物机制
|||
| :----: | :----: |
|怒气需求|80|
|掉落等级|白、紫、金|
|解锁方式|天赋精炼分支|

#### **核心**
怒气爆发后，会在玩家周围生成一个火圈。由于功能实现代码的部分问题，在火圈存在期间有怪物进入火圈时游戏画面可能会出现卡顿。
#### **力量**
额外附加的伤害计算方式为：  
`5% + 倍率系数 * 精炼个数`

例：

当圣物品质为金色，且当前精炼了20个圣物的情况下  
面板取值倍率为: `5% + 1.5% * 20 = 35%`


#### **敏捷**
当在敏捷槽携带朱雀之魂时，会依据当前的精炼计数提供对应数值的移速以及攻速加成。  


要注意的是：相比于须臾之砂的敏捷槽，朱雀之魂的移速转伤效果仅对精炼计数提供的移速加成生效。  
例：  
    假设当前总额外移速加成190%，其中朱雀之魂从精炼数提供的移速加成为30%  
    须臾之砂转伤幅度为 `190% * 50% = 85%`  
    朱雀之魂转伤幅度为 `30% * 50% = 15%`
#### **功效**
朱雀之魂在功效槽中时，会依据当前精炼计数提供对应数值的**减伤**。  
与文本描述不同，朱雀之魂的防御力加成效果是在伤害结算阶段以独立减伤的形式体现的。  
即：  
    假设朱雀之魂提供了30%的减伤，则在玩家受到伤害时，会将伤害值乘以`(1 - 30%) = 70%`。

同时，若精炼了50个以上的圣物后，生命值同时降低到20%以下，金色的朱雀之魂可以提供超过100%的减伤乘区，这会导致受到伤害时几乎不会掉血[1]。


## 补充
- 截至2022-8-17号，游戏内的朱雀之魂力量槽效果描述仍然存在问题。  
    文案文本：  
    *造成伤害时会附加攻击力* ***5%*** *的真实伤害*  
    实际效果：  
    *造成效果时会附加攻击力* ***3%*** *的真实伤害*


    即：基础提供的攻击力倍率并非`5%`而是`3%`

---
[1]游戏中或许存在保底伤害

<font color=grey>——Page Create By NekoIce</font>
