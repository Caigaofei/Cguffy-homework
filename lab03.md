---
layout: default
title: HTML5游戏制作入门教程
---

# *飞机打怪兽* 游戏制作入门教程
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;制作一个好游戏难吗？这个我敢肯定的说：“难”。但是，制作一个游戏难吗？这可就不一定了。我也是一个编程上的小白，然而借助工具(construct 2)的帮助，即便新手也能轻松做出一个小游戏的。<br>
![](图片/飞机打怪兽.gif)
## 一、安装construct 2
### 1、安装construct 2链接: <br>https://www.scirra.com/construct2/releases/r262
### 2、打开链接后，点击Download,如下图。<br><br>![](图片/Download.jpg "Download")<br><br>然后点击"保存文件"。当下载完成后，打开安装包，按照提示安装*construct 2*。<br>
## 二、游戏制作流程
### 1、打开链接:<br>https://www.scirra.com/tutorials/37/beginners-guide-to-construct-2
### 2、创建新文件
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;打开**construct 2**软件，然后点击File,然后点击New如图。<br>![](图片/New.jpg)<br><br>点击"New empty project"<br>![](图片/newproject.jpg)
### 3、背景制作
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;保存下方图片到本地<br>![](https://www.scirra.com/images/articles/bg.png)<br><br>
双击空白处,然后双击"Tiled Background",之后点击任意空白处。<br>![](https://www.scirra.com/images/articles/insertobject.png)<br><br>
点击"Load an image from a file"。<br>![](https://www.scirra.com/images/articles/loadtexturefromfile.png)<br><br>
在本地文件中选择刚刚保存的图片。打开后点击右上角的"X"，关闭小窗口。之后在右侧将"Position"调为"0,0"，将"Size"调为"1280,1024"。<br>![](https://www.scirra.com/images/articles/tiledproperties.png)<br>按住ctrl键同时向下滑动鼠标滚轮，会看到这样的界面：<br>![](https://www.scirra.com/images/articles/tiledui.jpg)<br><br>
### 4、添加层次
在界面右方偏上，点击layer。<br>![](https://www.scirra.com/images/articles/layerstab.png)<br>
选中"layer 0"，点击“铅笔”的图标，将"layer 0"改名为"Background"，并点击“锁头”的图标将背景锁定不可选中。然后点击"十"的图标增加一层，并按上法改名为"Main"，最终结果如下。<br>![](https://www.scirra.com/images/articles/layersbar.png)
### 5、加入图标
双击空白处，双击选择"Sprite"，再点击空白处，并按之前**添加背景**的方式添加一下四个图标。<br>Player: ![](https://www.scirra.com/images/articles/player.png) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Monster: ![](https://www.scirra.com/images/articles/monster.png)<br><br><br><br>bullet:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![](https://www.scirra.com/images/articles/bullet.png)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Explosion:![](https://www.scirra.com/images/articles/explode.png)<br><br><br>
从"Layer"调回"Project"，将各图标的名称从"Sprite 1/2/3/4"改为各自对应名称如"Player"。<br>![](https://www.scirra.com/images/articles/objectname.png)
### 6、添加动作
单击你已添加的Player的图标，在左侧"Edit behaviour"旁点击"Add/Edit"。<br>![](https://www.scirra.com/images/articles/openbehaviors.png)<br><br>
双击"8 Direction"。<br>![](https://www.scirra.com/images/articles/add8dir.png)<br><br>
同理，为"Player"添加"Scroll To"和"Bound To Layout"。<br>![](https://www.scirra.com/images/articles/playerbehaviors_2.png)<br><br>
同样的：<br>为"Bullet"添加"Bullet Movement"和"Destroy Outside Layout"动作;<br>为"Monster"添加"Bullet movement"动作;<br>为"Explosion"添加"Fade"动作。<br><br>
单击"Monster"图标，在左侧的"Behaviors"处将"Speed"从400改至80。<br>同法，<br>将"Bullet"的"Speed"改至600；<br>将"Explosion"的"Fade Out time"改至0.5。<br><br>
**将"Bullet"和"Explosion"图标移动到背景外部黑色部分，以免在游戏中出现。**
### 7、增加Monster
按住ctrl键同时鼠标左键点击"Monster"图标，拖拽后松开，连续复制出7-8个"Monster"，排布最好如图。<br>![](https://www.scirra.com/images/articles/severalghosts.png)
### 8、添加活动(Event)
#### 1、让Player可移动
在左上角偏下处，点击"Event sheet 1"。<br>![](https://www.scirra.com/images/articles/eventsheettab.png)<br><br>
双击空白处，双击"System"。<br>![](https://www.scirra.com/images/articles/newevent_2.png)<br><br>
双击"Every tick"<br>![](https://www.scirra.com/images/articles/everytickcnd.png)<br><br>
点击"Add action"，双击"Player"<br>![](https://www.scirra.com/images/articles/addactiondlg.png)<br><br>
然后双击"Set angle toward position"。<br>![](https://www.scirra.com/images/articles/playersetanglepos.png)<br><br>
将X与Y的值分别输入为Mouse.X, Mouse.Y。<br>![](https://www.scirra.com/images/articles/setangleposparams.png)<br><br>
最后点击"Done"，结果会是下图<br>![](https://www.scirra.com/images/articles/alwayslookatmouse.png)
#### 2、射出Bullet
双击空白处，双击"Mouse"，双击"On click"，选择"Left clicked"。<br><br>
点击"Add action"，双击"Player"，双击"Spawn another object"，"Object"选择"Bullet"，"Layer"输入1，"Image point"输入0，结果如下。<br>![](https://www.scirra.com/images/articles/spawnbullet1.png)<br><br>
右键点击"Player"图标，单击"Edit animations"，点击"Set origin or image point"图标：![](https://www.scirra.com/images/articles/imagepointstool.png)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;再点击"Player"的炮口:<br>![](https://www.scirra.com/images/articles/placingimagepoint.png)<br><br>
#### 3、让Bullet能杀了Monster
在"Event sheet 1"层双击空白处，双击"Bullet"，双击"On collision with another object"，"Objecy"选择"Monster"；<br>
点击"Add action"，双击"Monster",双击"Destroy"；<br>
点击"Add action",双击"Bullet"，双击"Spawn another object"，"Object"选择"Explosion"，"Layer"输入1;<br>
点击"Add action"，双击"Bullet"，双击"Destroy"。
#### 4、调整爆炸效果
在"Layout 1"层点击"Explosion"图标，在左侧的"Blend mood"旁将"Normal"修改为"Additive"。
#### 5、让怪物更聪明
在"Event sheet 1"层双击空白处，双击"System"，双击"On start of Layout"；<br>
点击"Add action"，双击"Set angle"，"random"设置为360。<br>![](https://www.scirra.com/images/articles/ghostshooterevent4.png)<br>
双击空白处，双击"Monster"，双击"Is outside layout"。<br>
点击"Add action"，双击"Monster"，双击"Set angle toward position"，"X","Y"分别输入Play.X与Player.Y。
#### 6、调节怪物血量
**一、** <br>在"Layout 1"层点击"Monster"图标，在左侧"Edit variables"旁点击"Add/Edit",再点击"十"图标<br>![](https://www.scirra.com/images/articles/instvars.png)<br><br>
将"Name"改为"Health"，再将"Initial value"输入为5<br>![](https://www.scirra.com/images/articles/healthinstvar.png)<br><br>
**二、改变活动(Event)**<br> 在"Event sheet 1"层右键"Monster Destroy",点击"Replace"<br>![](https://www.scirra.com/images/articles/replaceaction.png)<br><br>
双击"Monster"，双击"Subtract from"，将Instant variable输入为"Health"，Value输入1，点击"Done"<br>![](https://www.scirra.com/images/articles/sub1fromhealth.png)<br><br>
双击空白处，双击"Monster"，双击"Compare instance variable"，选择"Health"与"Less or equal 0"；<br>
点击"Add action"，双击"Monster"，双击"Spawn another object"，选择"Explosion"，"Layer"输入1；<br>
点击"Add action"，双击"Monster"，双击"Destroy"。<br>![](https://www.scirra.com/images/articles/monsternohealth.png)
#### 7、获得得分
在"Event sheet 1"层右键，点击"Add globle variable"<br>![](https://www.scirra.com/images/articles/addglobal.png)<br><br>
"Name"改为"Score"，"Initial value"输入0<br>![](https://www.scirra.com/images/articles/addglobalscore.png)<br><br>
在"Monster:health less or equal 0"的活动(Event)中点击"Add action"，双击"System"，双击"Add to"，选择"Score"，"Value"输入为1<br>![](https://www.scirra.com/images/articles/scoreeevent.png)<br><br>
#### 8、增加计分层
在"Layer 1"处增加多一层并改名为"HUD"；<br>
在"Layout 1"处双击空白处，双击"Text"，并将其放在左上角，调节字体<br>![](https://www.scirra.com/images/articles/textinlayout.png)<br><br>
在"Event sheet 1"层的"Every tick"活动(Event)前add action：双击"Text"，双击"Set text"，输入"Score:"&Score。
#### 9、怪物复活机制
"Event sheet 1"层双击空白处，双击"System"，双击"Every X seconds"，输入3；<br>
点击"Add action"，双击"System"，双击"Create object"，选择"Monster"，"Layer"输入为1，"X"，"Y"分别输入为1400，random(1024)；<br>
双击空白处，双击"Monster"，双击"On collision with another object"，选择"Player"；<br>
点击"Add action"，双击"Player"，双击"Destroy"。<br><br>
### 到此为止，一个游戏就制作完了，是不是挺简单的呢？对于自己做的一个小游戏，有什么感想呢？只要克服了心里的一些小障碍，小伙伴们想必会发现更宽广的世界吧。为美好的世界献上祝福!