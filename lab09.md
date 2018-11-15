---
layout: default
title: 自顶向下 逐步求精
---

# <center><font size="7" font face="楷体" font color="#006666">自顶向下 逐步求精</font></center>
**<font size="4">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在本次实验中，我将简单地介绍一下自顶向下，逐步求精的设计思想，并以洗衣机的程序设计为例说明该如何使用这种设计思想。</font>**<br><br>

**<font size="5">概念</font>**

**<font size="3">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;“自顶而下，逐步求精”的设计思想，其出发点是从问题的总体目标开始，抽象低层的细节，先专心构造高层的结构，然后再一层一层地分解和细化。这使设计者能把握主题，高屋建瓴，避免一开始就陷入复杂的细节中，使复杂的设计过程变得简单明了，过程的结果也容易做到正确可靠。</font>**<br>
![](https://img-blog.csdn.net/20171129184722808?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveHVhbl90aW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast "大致模型")<br><br>

**<font size="5">实现</font>**

**<font size="3"></font>**

**<font size="3">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;概念不困难，但是要如何实现呢？</font>**<br><br>

**<font size="4">1.将任务分成几个大的步骤</font>**

**<font size="3">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这一步任务目标很明确，就是要将任务分成几个大的任务。要如何做，就一洗衣机为例：</font>**


<font size="3">1.选择洗衣的水位<br>2.注水：通过水位计限定水位<br>3.转动：左5次、右5次，计时器倒计时<br>4.浸泡：计时器倒计时<br>5.排水：水位计计录水位<br>（重复2-5步骤两次）<br>6.转动：脱水，计时器倒计时<br>7.洗衣结束，发出报警声后机器关机</font><br><br>

**<font size="4">2.继续细分每个大任务</font>**

**<font size="3">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在将洗衣机工作任务分成7个大块以后，接下来的目标便是将这7个大任务分成 n 个更小的任务，使得每个小任务都能较为轻松地实现。</font>**

<font size="3">**1.选择洗衣的水位：**<br>①显示可注入的水位；<br>②选择水位;<br>③读取水位；<br>**2.注水：通过水位计限定水位:**<br>①打开注水阀门<br>②水位计开始工作，返回水位数值；<br>③当水位达到要求的水位时，关闭注水阀门；<br>**3.转动：左5次、右5次，计时器倒计时:**<br>①计时器开始倒计时；<br>②开始转动；<br>③计时器返回数值为0时，停止转动。<br>**4.浸泡：计时器倒计时:**<br>①计时器开始倒计时；<br>②当计时器返回数值为0时，继续下一步任务；<br>**5.排水：水位计计录水位:**<br>①水位计开始工作读取数值；<br>②排水阀门打开；<br>③当水位计返回数值为0时，关闭排水阀门；<br>**（重复2-5步骤两次）**<br> **6.转动：脱水，计时器倒计时:**<br>①计时器开始倒计时，机器开始转动；<br>②当计时器返回数值为0时，停止转动；<br>**7.洗衣结束，发出报警声后机器关机**</font><br><br>

**<font size="4">3.实现每个小任务</font>**

**<font size="3">里面用到的函数：<br>water_in_switch(open_close)  // open 打开上水开关，close 关闭<br>water_out_switch(open_close)  // open 打开排水开关，close 关闭<br>get_water_volume()  // 返回洗衣机内部水的高度<br>motor_run(direction) // 电机转动。left 左转，right 右转，stop 停<br>time_counter()  // 返回当前时间计数，以秒为单位<br>halt(returncode) //停机，success 成功 failure 失败<br><br></font>**
```
    READ 用户要求注水水位
    times=0;
    REPEAT
        water_in_switch(open)                 //注水
    UNTIL get_water_volume() == 用户要求         
    
    water_in_switch(close)                    //停止注水
    
    REPEAT
        WHILE time_counter() is not equal to 0
            motor_run(left) for five times
            motor_run(right) for five times   //转动
        END WHILE

        WHILE time_counter() is not equal to 0
            The machine doesn't do anything   //浸泡
        END WHILE

        WHILE get_water_volume() is not equal to 0
            water_out_switch(open)            //排水
        END WHILE
        
        water_out_switch(close)               //停止排水
        
        INCREMENT times
    UNTIL times > 2

    REPEAT
        motor_run(left)                       //脱水
    UNTIL time_counter() is equal to 0

    halt(success)
```
<br>

**<font size="5">测试</font>**

**<font size="3">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;对于完成的任务步骤设计，如果有机会的话，通过在现实中进行检测，寻找其中的漏洞。如果没有，则需要自己给定一组操作数，来通过计算，检查能否顺利完成自己的目标。<br><br> 注意！！别小看测试是最后一步，这一步很多情况下也是最花时间、耗费最多精力的一步，同时也是能够顺利完成目标的重要要求与任务！！</font>**