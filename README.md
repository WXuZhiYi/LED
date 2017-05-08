#include"LPC11xx.H"
void Delay();
 
void Delay(int x)
{
	int z,y;
	for(y=x;y>=0;y--)
	    for(z=500;z>=0;z--);
}
int main(void)
{
	
	int i;
	while(1)
	{
		for(i=0;i<8;i++)
		{
			LPC_GPIO2->DIR |=(1<<i);
			LPC_GPIO2->DATA &=~(1<<i);
			Delay(500);
			LPC_GPIO2->DATA |=(1<<i);
      Delay(500);
		}			
	}
}
