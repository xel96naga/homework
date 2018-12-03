# 先写上最简单的贪吃蛇代码

    #include <stdio.h>
    #include <string.h>
    struct body{
    	int x,y;
    };
    void primap(char map[22][22]);
    //为了操作方便，此函数用于打印地图。 

    void move(int *head,int *tail,char dir,char map[22][22],struct body q[10000]);
    //此函数用于移动，也包含了撞墙，吃东西等情况。 

    void gameover(char map[22][22]);
    //为了方便，用于结束游戏的函数。 

    void createfood(char map[22][22]);
    /*当吃了东西，再随机生成一个。显然，此函数要套用在move函数里。*/

    int main(){
	    char map[22][22],dir,c;
    	int i,j,lenth,head,tail;
	    struct body q[10000];
    
	    /*我决定将蛇身作为队列，每次在末尾减去元素，在头部加上新元素，就完成了移动 */
	
	    for(i=0;i<=21;++i) for(j=0;j<=21;++j) map[i][j]=' ';
	    for(i=0;i<=21;++i){
		map[i][0]='*';map[i][21]='*';map[0][i]='*';map[21][i]='*';
    	}
    	map[1][1]='X';map[1][2]='X';
    	map[10][10]='$';
    	head=0;tail=2;q[1].x=1;q[1].y=1;  q[2].x=1;q[2].y=2;	
    	primap(map);
    	//以上均为初始值。 
    
    
    	while(1){
	    	//模拟帧数，动一次认为是一帧。 
	    	/*每个帧数要移动，并判断移动后的情况。都装在move里了。 */

	    	scanf("%c%c",&dir,&c);
	    	//c只用于读入换行符，没什么意义。 
	    	move(&head,&tail,dir,map,q);
	    	primap(map);
    	}
    	return 0;
    
    }
    void gameover(char map[22][22]){
    	primap(map);
    	printf("\n\n  Game Over  \n\n");
    
	    system("pause");
	    //此语句可结束程序。 
    }

    void primap(char map[22][22]){
	    int i,j;
	    for(i=0;i<=21;++i){
	    	for(j=0;j<=21;++j)
	    		printf("%c",map[i][j]);
	    	printf("\n"); 
	    }
    	printf("\n");
    }

    void move(int *head,int *tail,char dir,char map[22][22],struct body q[10000]){
	    struct body next;
	
	    next.x=q[*tail].x;next.y=q[*tail].y;
	    switch(dir){
	    	case 'w':next.x--;break;
	    	case 's':next.x++;break;
	    	case 'a':next.y--;break;
	    	case 'd':next.y++;break;
    	}
	
    	//next.x next.y存放下一步的坐标，以便讨论。 
	
	    if (map[next.x][next.y]=='*'||map[next.x][next.y]=='X')
	    	gameover(map);
	    //撞墙，咬自己，当然死了。 
    
	    if (map[next.x][next.y]=='$'){
	    	(*tail)++;
	    	q[*tail].x=next.x;q[*tail].y=next.y;
	    	map[ q[*tail].x ][ q[*tail].y ]='X';
    
	    	createfood(map);
	    	//如果下一步吃东西
	    	//自然要再生成食物的。 
	    }
	    else{
	    	(*head)++;
	    	map[ q[*head].x ][ q[*head].y ] =' ';
	    	(*tail)++;
	    	q[*tail].x=next.x;q[*tail].y=next.y;
	    	map[ q[*tail].x ][ q[*tail].y ]='X';

		    //对队列进行操作，模拟移动。 
	    }
    }

    void createfood(char map[22][22]){
    	int x,y;
    	x=rand()%20+1;
    	y=rand()%20+1;
    	/*随机数，特别注意防止0生成，0在墙里。*/ 
    
    	if (map[x][y]!='X') map[x][y]='$';
    	else createfood(map);
    }