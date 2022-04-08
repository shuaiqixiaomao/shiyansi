#include <stdio.h>
#include <string.h>

int main()
{
 char a[]="2+2*3+2/2-1";
 char kbfz[100];

 int h=-1;
 for(int  i=0;i<100;i++)
 {
	 if(a[i]=='*')
	 {
		 int left=kbfz[h]-'0';
	     int right=a[i+1]-'0';
		 kbfz[h]=left*right+'0';

		 i++;
	 
	 }
	 else if(a[i]=='/')
	 {
		 int left=kbfz[h]-'0';
	     int right=a[i+1]-'0';
		 kbfz[h]=left/right+'0';

		 i++;
	 
	 }
	 else
	 {
		 kbfz[++h]=a[i];
	 }

 
 }
	 int result=kbfz[0]-'0';
	 for(i=1;i<100;i++)
	 {
		 if(kbfz[i]=='+')
		 {
			 result=result+(kbfz[++i]-'0');
		 }
		 else if(kbfz[i]=='-')
		 {
			 result=result-(kbfz[++i]-'0');
		 }
	 }
	printf("%d\n",result);
	return 0;}
