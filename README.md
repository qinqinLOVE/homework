/*my project*/
#include <stdio.h>  
#include <windows.h>  
#include <string.h>  
#include<time.h>  
#include <stdlib.h>  
int fun_A(int[]);  
void fun_B();  
/* 修改了 */int fun_C(int[]);  
void fun_D();  
typedef struct ticket
{
	int number[7];

}ticket;
ticket use1;
int flag=0;//标志特殊位置

void main()  
{  
int sel,i;  
ticket use; /* 修改了 */ 
char ans;  
printf("正在进入系统，请稍后！........\n");  
for(i=0;i<70;i++)  
{  
printf(">");  
Sleep(20);  
}  
system("cls");  
printf("\t系统程序加载成功！\n\n");  
system("pause");  
system("cls");  
system("color 3f");  
do  
{  
system("cls");  
printf("\t\t欢迎进入彩票系统\n"); 
printf("\t\t本课题设计组员：孙芹 \n");  
 printf("\t\t【一、开始投注 】 【二、查看规则】\n");  
printf("\t\t【三、 开 奖   】  【四、获奖情况】\n"); 
printf("\t\t【五、退出系统 】\n");
printf("请按键选择：");  
scanf("%d",&sel);  
switch(sel)  
{  
case 1:  
fun_A(use.number);  
break;  
case 2: fun_B(); break;  
case 3: fun_C(use.number); break;  
case 4:{
	   flag=1;
	     fun_C(use.number);
	   }      break;
case 5: fun_D(); break;  
default:  
printf("出错~！~~！");  

}  
getchar();
printf("请问是否继续选号:(Y/N)\n");
scanf("%c",&ans);
if(ans=='y')
fun_A(use1.number);
printf("\n请问你是否要返回到主页面（Y/N）：");  
scanf(" %c",&ans);  
}while(ans=='Y'||ans=='y');  
if(ans!='y'||ans!='Y')  
{  
fun_D();  
}  
}  
void fun_B()////规则  
{  
system("cls");  
printf("------------------------------我是分割线-----------------\n");  
Sleep(1000);  
printf("\n从1---33中选出7个不重复的号码。");  
Sleep(1000);  
printf("\n①、一等奖：所选号码与开奖号码有7和相同即可获得；奖人民币500万元。 \n\n");  
Sleep(1000);  
printf("②、二等奖：所选号码与开奖号码有6和相同即可获得；奖人民币100万元。 \n\n");  
Sleep(1000);  
printf("③、三等奖：所选号码与开奖号码有5和相同即可获得；奖人民币1万元。 \n\n");  
Sleep(1000);  
printf("④、四等奖：所选号码与开奖号码有4和相同即可获得；奖人民币2000元。 \n\n");  
Sleep(1000);  
printf("⑤、五等奖：所选号码与开奖号码有3和相同即可获得；奖人民币500元。\n\n");  
Sleep(1000);  
printf("⑥、六等奖：所选号码与开奖号码有2和相同即可获得；奖人民币100元。\n\n");  
Sleep(800);  
printf("--------------------------大家好呀，我是分割线--------------------------\n\n");
}  
int fun_A(int use[7])/////选号  
{  
int i,j,cc;  
char ch;  
int sel;  
printf("一 机选\n二 自己选\n");  
LOOP2: printf("请选择:");///////用户选择是机选还是自己选  
scanf(" %d",&sel);  

if(sel==1)///////////////////////用户定义机选号码 
{  
do  
{  
srand(time(0));  
use[0]=rand()%32+1;  
for(i=1;i<7;i++)  
{  
use[i]=rand()%32+1;  
for(j=0;j<i;j++)  
{  
if(use[i]==use[j])  
{  
i--;  
}  
}  
}  
printf("本次为您机选的号码为：");  
for(i=0;i<7;i++)  
{  
printf("%4d",use[i]);  
Sleep(800);  
}  
printf("\n请问你是否确认本次选号：（Y/N）");  
scanf(" %c",&ch);  
 }while(ch=='n'||ch=='N');  
return use[i];  



}  
else if(sel==2)/////////////////用户选择自己选！  
{  
do  
{  
for(i=0;i<7;i++)  
{  
LOOP1: printf("请输入第%d个号码：",i+1);//////用户进入自己选号  
cc=scanf("%d",&use[i]);  
if(use[i]>33)  
{  
printf("您输入的号码已经超出范围！\n");  
printf("\t\t请重新输入\n");  
goto LOOP1;  
}  
if(cc==1&&use[i]>=1&&use[i]<=33)  
{  
for(j=0;j<i;j++)  
{  
if(use[i]==use[j])  
{  
printf("您输入的号码已存在！\n");  
printf("\t\t请重新输入\n");  
goto LOOP1;  
i--;  
}  
}  
}  
}  
printf("本次您选的号码为：");  
for(i=0;i<7;i++)  
{  
printf("%4d",use[i]);  
Sleep(800);  
}  
printf("\n请问你是否确认本次选号：（Y/N）");  
scanf(" %c",&ch);  
}while(ch=='n'||ch=='N');  
return use[i];  
}  
 if(sel>=3)  
{  
printf("出错！");  
goto LOOP2;  
}  
}  
/* 修改了 */int fun_C(int use[7])//////开奖  
{  
int i,j,computernumber[7],count=0;  
srand(time(0));  
//computernumber[0]=rand()%10+1;  
for(i=0;i<7;i++)  
{  
computernumber[i]=rand()%32+1;  
for(j=0;j<i;j++)  
{  
if(computernumber[i]==computernumber[j])  
{  
i--;  
}  
}  
}  
if(flag==0)
{
printf("本次开奖的号码为：");  
for(i=0;i<7;i++)  
{  
printf("%4d",computernumber[i]);  
Sleep(800);  
}printf("\n");  
if(use[0]==0 && use[1]==0 && use[2]==0 && use[3]==0 && use[4]==0 && use[5]==0 && use[6]==0)   
{printf("没买？亏了！"); 
Sleep(800); 
return (0);
} 
printf("你所选的号码为：");  
for(i=0;i<7;i++)  
{  
printf("%4d",use[i]);  
}  
printf("\n");
printf("                  ");
for(i=0;i<7;i++)
{
	printf("%4d",use1.number[i]);
}
printf("\n");
} 
for(i=0;i<7;i++)  
{  
for(j=0;j<7;j++)  
{  
if(use[i]==computernumber[j])  
{  
count++;  
}  
}  
}  
if(flag==1){
if(count==7)  
{  
printf("恭喜你中了“一等奖”\n");  
printf("奖人民币500万元。\n");  
}  
if(count==6)  
{  
printf("!恭喜你中了“二等奖”\n");  
printf("奖人民币100万元.\n");  
}  
if(count==5)  
{  
printf("!恭喜你中了“三等奖”\n");  
printf("奖人民币1万元.");  
}  
if(count==4)  
{  
printf("!恭喜你中了“四等奖”\n");  
printf("奖人民币2000元.\n");  
}  
if(count==3)  
{  
printf("!恭喜你中了“五等奖”\n");  
printf("奖人民币500元。\n");  
}  
if(count==2)  
{  
printf("!恭喜你中了“六等奖”\n");  
printf("奖人民币100元。\n");  
}  
if(count<2)  
{  
printf("欢迎下次再来！！！\n");  
}  
}

}  
void fun_D()  
{  
int i;  
printf("正在安全退出系统，请稍后！........\n");  
for(i=0;i<70;i++)  
{  
printf(">");  
Sleep(100);  
}  
system("cls");  
printf("欢迎下次使用！\n");  
exit(0);  
}  
