---
layout: default
title: “Ben 10的守护”游戏制作
---

**<center><font size="6">“Ben 10的守护”游戏制作</font></center>**<br><br>
![](视频/守护朋友.gif "守护朋友")

![](图片/守护朋友.jpg "\"Ben 10的守护\"的部分code")<br><br><br>

**<font size="5">游戏背景</font>**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ben 10 是一位十岁大的男孩，他的生活因为一个撞上地球的陨石而永远改变。从天而降的陨石带来了 Omnitrix，让他拥有变身成十种以上外星英雄的能力，而每一个英雄都有独特的神奇力量。自此，小班成为一个超级英雄。在爷爷马克与堂妹小玟的帮助下，小班肩负起保卫世界的任务。此时，Ben 10和他的朋友忽然遭遇怪物的袭击，他的朋友 **受伤了不能移动**，因此 Ben 10 只能尽全力守护 **在朋友身边** 直到支援的到来。<br><br>

**<font size="5">玩法</font>**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;游戏中的player **Ben 10** 由玩家操控，点击一次鼠标左键会朝着鼠标的方向射出一发子弹。<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;游戏中有两种怪物： 一种是绿色怪物，有 **3滴血**；另一种是更大的红色怪物，有 **8滴血**。<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;每发子弹击中怪物会造成 **1 点伤害**。<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;当其中一种怪物 **碰撞** 到 **Ben 10** 或者 **他的朋友**，游戏结束； <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;当在 **击败40名敌人** 后 **Ben 10** 和 **他的朋友** 仍未被碰撞到，则游戏胜利;<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;游戏过程中会出现 **游戏道具**，用子弹 **击中** 游戏道具可以杀死 **当前屏幕内** 的所有怪物。<br><br><br><br>

**<font size="5">游戏CRC卡片</font>**
<br><br>

**<font size="4">Ben 10</font>**

<font size="4">Object name: Ben 10<br>Collaborator：Sprite<br>Events & Actions：射出子弹，消灭怪物</font><br>
<font size="4">Attribute:</font><br>
![](图片/Ben 10.jpg "Ben 10")<br><br>

**<font size="4">Ben 10的朋友</font>**

<font size="4">Object name: 楪祈<br>Collaborator：Sprite<br>Events & Actions：卧倒在地，被怪物碰撞后游戏结束</font><br>
<font size="4">Attribute:</font><br>
![](图片/朋友.jpg "Ben 10的朋友")<br><br>

**<font size="4">Green Monster</font>**

<font size="4">Object name: Green Monster<br>Collaborator：Sprite<br>Events & Actions：有3滴血，向 Ben 10 和 楪祈 撞击</font><br>
<font size="4">Attribute:</font><br>
![](图片/绿色怪物.jpg "Green Monster")<br><br>

**<font size="4">Red Monster</font>**

<font size="4">Object name: Red Monster<br>Collaborator：Sprite<br>Events & Actions：有8滴血，向 Ben 10 和 楪祈 撞击</font><br>
<font size="4">Attribute:</font><br>
![](图片/红色怪物.jpg "Red Monster")<br><br>

**<font size="4">Bullet</font>**

<font size="4">Object name: Bullet<br>Collaborator：Sprite<br>Events & Actions：向鼠标点击的位置沿直线移动，碰撞到怪物后消失并使怪物失去一滴血</font><br>
<font size="4">Attribute:</font><br>
![](图片/bullet.jpg "Bullet")<br><br><br><br>

**<font size="5">游戏设计</font>**


<font size="4">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;设置好在森林中的背景之后，添加入CRC卡片，并赋予各个角色所需要的属性以及行为。如 “朋友” 卧倒不可移动； Ben 10 要守护在朋友身边因此也不可移动； 子弹沿直线飞行； 怪物朝着 Ben 10 和 他的朋友冲来； 怪物的血量等等。待这些工作做完后，一个简单地小游戏就做出来了。</font>
