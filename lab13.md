---
layout: default
title: 贪吃蛇实验报告
---
<center><font size="7" font face="楷体" font color="#000066">贪吃蛇实验报告</font></center><br><br>

<font size="4">1.snake_move.c</font><br><br>
```C
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define SNAKE_MAX_LENGTH 20          //蛇的最大长度 
#define SNAKE_HEAD 'H' 
#define SNAKE_BODY 'X'
#define	BLANK_CELL ' '
#define SNAKE_FOOD '$'
#define WALL_CELL '*'

//snake stepping:dy=-1(up),1(down); dx=-1(left),1(right); dx/dy = 0(no move); 
void snakeMove(int ,int );
//put a food randomized on a blank cell
void putMoney(void);
//out cells of the grid
void output();
//outs when gameover
void gameover(int ,int );
//determine whether the snake get the money or not
void getMoney(int ,int ); 

char map[12][12]=
	{"************",
	 "*XXXXH     *",
	 "*          *",                 //初始状态 
	 "*          *",                 //直接打表 
	 "*          *",
	 "*          *",
	 "*          *",
	 "*          *",
	 "*          *",
	 "*          *",
	 "*          *",
	 "************"};

//define vars for snake, notice name of vars in C	 
int snakeX[SNAKE_MAX_LENGTH]={1,2,3,4,5};
int snakeY[SNAKE_MAX_LENGTH]={1,1,1,1,1};               //蛇头和蛇身的坐标 
int snakeLength = 5;                                    //蛇的初始长度 

int isAlive = 1;                                        //等于 1 时表示蛇还存活，等于 0 时表示蛇已死亡 
int flag=0;                                             //等于 1 时表示吃到了 $ ,等于 0 时表示没吃到 $ 

int main(){
	char ch;
	int i,j;

	for(i=0;i<12;i++){
		for(j=0;j<12;j++){
			if(j<11)
				printf("%c",map[i][j]);
			else if(j==11)
				printf("%c\n",map[i][j]);
		}
	}                                                //打印初识蛇的位置与地图 
	
	while(isAlive!=0){
		scanf("%c",&ch);
		switch(ch){
			case 'A': gameover(-1,0);                //先判断是否触发gameover的条件 
					  snakeMove(-1,0);               //往左移动一格 
					  output();break;                //打印 
			case 'D': gameover(1,0);
					  snakeMove(1,0);                //往右移动一格 
					  output();break;              
			case 'W': gameover(0,-1);
					  snakeMove(0,-1);               //往上移动一格 
					  output();break;
			case 'S': gameover(0,1);
					  snakeMove(0,1);                //往下移动一格 
					  output();break;
		}
		
	}
	
	printf("Game Over!!!\n");
	
	return 0;
} 

void snakeMove(int dx,int dy){
	int tmpX1=0,tmpY1=0,tmpX2=0,tmpY2=0,i,j;
	tmpX1=snakeX[snakeLength-1];
	tmpY1=snakeY[snakeLength-1];
	
	for(i=snakeLength-2;i>=0;i--){
			tmpX2=snakeX[i];
			tmpY2=snakeY[i];               //tmpX2、tmpY2用于记录蛇当前部分的坐标 
			snakeX[i]=tmpX1;
			snakeY[i]=tmpY1;              //tmpX1、tmpY1用于记录蛇上一部分的坐标 
			tmpX1=tmpX2;
			tmpY1=tmpY2;
		}                                 //将后面的蛇身往前挪一位 
	
	map[tmpY1][tmpX1]=' ';                //将末尾改为 空格 
	
	if(dx==-1&&dy==0)
		snakeX[snakeLength-1]-=1;
	else if(dx==1&&dy==0)
		snakeX[snakeLength-1]+=1;
	else if(dx==0&&dy==-1)
		snakeY[snakeLength-1]-=1;
	else if(dx==0&&dy==1)
		snakeY[snakeLength-1]+=1;		  //将蛇头按方向行进一位
			                                   
	for(i=0;i<snakeLength;i++){
		if(i<snakeLength-1)
			map[snakeY[i]][snakeX[i]]='X';
		else if(i==snakeLength-1)
			map[snakeY[i]][snakeX[i]]='H';
	}									  //将蛇头和蛇身赋值相应字符
}

void gameover(int dx,int dy){
	if(map[snakeY[snakeLength-1]+dy][snakeX[snakeLength-1]+dx]=='X'||map[snakeY[snakeLength-1]+dy][snakeX[snakeLength-1]+dx]=='*')
		isAlive=0;
}                                             //判断游戏是否结束，若结束，将 0 赋值给 isAlive 

void output(){
	int i=0,j=0;
	for(i=0;i<12;i++){
		for(j=0;j<12;j++){
			if(j<11)
				printf("%c",map[i][j]);
			else if(j==11)
				printf("%c\n",map[i][j]);
		}
	}
}	                                    	  //打印 
```
<br><br>
<font size="4">2.snake_eat.c</font><br><br>
```C
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define SNAKE_MAX_LENGTH 20          //蛇的最大长度 
#define SNAKE_HEAD 'H' 
#define SNAKE_BODY 'X'
#define	BLANK_CELL ' '
#define SNAKE_FOOD '$'
#define WALL_CELL '*'

//snake stepping:dy=-1(up),1(down); dx=-1(left),1(right); dx/dy = 0(no move); 
void snakeMove(int ,int );
//put a food randomized on a blank cell
void putMoney(void);
//out cells of the grid
void output();
//outs when gameover
void gameover(int ,int );
//determine whether the snake get the money or not
void getMoney(int ,int ); 

char map[12][12]=
	{"************",
	 "*XXXXH     *",
	 "*          *",                 //初始状态 
	 "*          *",                 //直接打表 
	 "*          *",
	 "*          *",
	 "*          *",
	 "*          *",
	 "*          *",
	 "*          *",
	 "*          *",
	 "************"};

//define vars for snake, notice name of vars in C	 
int snakeX[SNAKE_MAX_LENGTH]={1,2,3,4,5};
int snakeY[SNAKE_MAX_LENGTH]={1,1,1,1,1};               //蛇头和蛇身的坐标 
int snakeLength = 5;                                    //蛇的初始长度 

int isAlive = 1;                                        //等于 1 时表示蛇还存活，等于 0 时表示蛇已死亡 
int flag=0;                                             //等于 1 时表示吃到了 $ ,等于 0 时表示没吃到 $ 

int main(){
	char ch;
	int i,j;
	
	putMoney();                                      //最开始放置一个食物 $ 
	
	for(i=0;i<12;i++){
		for(j=0;j<12;j++){
			if(j<11)
				printf("%c",map[i][j]);
			else if(j==11)
				printf("%c\n",map[i][j]);
		}
	}                                                //打印初识蛇的位置与地图 
	
	while(isAlive!=0){
		scanf("%c",&ch);
		switch(ch){
			case 'A': gameover(-1,0);                //先判断是否触发gameover的条件 
					  snakeMove(-1,0);               //往左移动一格 
					  output();break;                //打印 
			case 'D': gameover(1,0);
					  snakeMove(1,0);                //往右移动一格 
					  output();break;              
			case 'W': gameover(0,-1);
					  snakeMove(0,-1);               //往上移动一格 
					  output();break;
			case 'S': gameover(0,1);
					  snakeMove(0,1);                //往下移动一格 
					  output();break;
		}
		
	}
	
	printf("Game Over!!!\n");
	
	return 0;
} 

void snakeMove(int dx,int dy){
	int tmpX1=0,tmpY1=0,tmpX2=0,tmpY2=0,i,j;
	tmpX1=snakeX[snakeLength-1];
	tmpY1=snakeY[snakeLength-1];
	
	getMoney(dx,dy);
	if(flag==1){							  //当吃到了 $ 时 
		snakeLength++;
		snakeX[snakeLength-1]=snakeX[snakeLength-2]+dx;
		snakeY[snakeLength-1]=snakeY[snakeLength-2]+dy;
		map[snakeY[snakeLength-1]][snakeX[snakeLength-1]]='H';
		map[snakeY[snakeLength-2]][snakeX[snakeLength-2]]='X';
		flag=0;
	} 										  
	else if(flag==0){                         //当没吃到 $ 时 
		for(i=snakeLength-2;i>=0;i--){
			tmpX2=snakeX[i];
			tmpY2=snakeY[i];                  //tmpX2、tmpY2用于记录蛇当前部分的坐标 
			snakeX[i]=tmpX1;
			snakeY[i]=tmpY1;                  //tmpX1、tmpY1用于记录蛇上一部分的坐标 
			tmpX1=tmpX2;
			tmpY1=tmpY2;
		}                                     //将后面的蛇身往前挪一位 
	
		map[tmpY1][tmpX1]=' ';                //将末尾改为 空格 
	
		if(dx==-1&&dy==0)
			snakeX[snakeLength-1]-=1;
		else if(dx==1&&dy==0)
			snakeX[snakeLength-1]+=1;
		else if(dx==0&&dy==-1)
			snakeY[snakeLength-1]-=1;
		else if(dx==0&&dy==1)
			snakeY[snakeLength-1]+=1;		  //将蛇头按方向行进一位
			                                   
		for(i=0;i<snakeLength;i++){
			if(i<snakeLength-1)
				map[snakeY[i]][snakeX[i]]='X';
			else if(i==snakeLength-1)
				map[snakeY[i]][snakeX[i]]='H';
		}									  //将蛇头和蛇身赋值相应字符
	}
}

void gameover(int dx,int dy){
	if(map[snakeY[snakeLength-1]+dy][snakeX[snakeLength-1]+dx]=='X'||map[snakeY[snakeLength-1]+dy][snakeX[snakeLength-1]+dx]=='*')
		isAlive=0;
}                                             //判断游戏是否结束，若结束，将 0 赋值给 isAlive 

void putMoney(){
	int x,y;
	
	srand(time(NULL));
	x=1+(rand()%10);
	y=1+(rand()%10);
	while(map[x][y]!=' '){
		x=1+(rand()%10);
		y=1+(rand()%10);
	}
	map[x][y]='$';
}                                          //随机位置产生一个$

void getMoney(int dx,int dy){	
	if(map[snakeY[snakeLength-1]+dy][snakeX[snakeLength-1]+dx]=='$'){
		if(snakeLength<SNAKE_MAX_LENGTH){
			flag=1;
			putMoney();
		}
		else
			putMoney(); 
	}
}                                          //判断是否吃到 $ 

void output(){
	int i=0,j=0;
	for(i=0;i<12;i++){
		for(j=0;j<12;j++){
			if(j<11)
				printf("%c",map[i][j]);
			else if(j==11)
				printf("%c\n",map[i][j]);
		}
	}
}	                                    	  //打印 
```
<br><br>
<font size="4">3.随机放置食物的伪代码</font><br><br>
```
//get two numbers x,y,as 1 <= x <= 10 and 1 <= y <=10
//use x,y to be a coordinate (x,y)

WHILE the number of food is 0 THEN
    IF (x,y) of the map is not ' ' THEN
        regain two numbers to form a new coordinate
    ELSE IF (x,y) of the map is ' ' THEN
        turn ' ' to a food '$'
        the number of food = 1 
    END IF
END WHILE
```


<font size="4"></font><br><br>