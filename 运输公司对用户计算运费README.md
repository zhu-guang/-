#include<stdio.h>

int main ( ) 
{
     int distance;
     float basicFreight,weight,discount,freight,pastmoney[6];
     printf("请输入基本运费 货物重量 距离：");
     scanf("%f %f %d",&basicFreight,&weight,&distance);
     
     pastmoney[1]=basicFreight*weight*250;
     pastmoney[2]=basicFreight*weight*(500-250)*(1-2/100.0);
     pastmoney[3]=basicFreight*weight*(1000-500)*(1-5/100.0);
     pastmoney[4]=basicFreight*weight*(2000-1000)*(1-8/100.0);
     pastmoney[5]=basicFreight*weight*(3000-2000)*(1-10/100.0);

     if(distance<250)
          discount=0,    freight=basicFreight*weight*distance*(1-discount/100.0);
     else if(distance>=250 && distance<500)
          discount=2,    freight=basicFreight*weight*(distance-250)*(1-discount/100.0)+pastmoney[1];
     else if(distance>=500 && distance<1000)
          discount=5,    freight=basicFreight*weight*(distance-500)*(1-discount/100.0)+pastmoney[2]+pastmoney[1];
     else if(distance>=1000 && distance<2000)
          discount=8,    freight=basicFreight*weight*(distance-1000)*(1-discount/100.0)+pastmoney[3]+pastmoney[2]+pastmoney[1];
     else if(distance>=2000 && distance<3000)
          discount=10,   freight=basicFreight*weight*(distance-2000)*(1-discount/100.0)+pastmoney[4]+pastmoney[3]+pastmoney[2]+pastmoney[1];
     else if(distance>=3000)
          discount=15,   freight=basicFreight*weight*(distance-3000)*(1-discount/100.0)+pastmoney[5]+pastmoney[4]+pastmoney[3]+pastmoney[2]+pastmoney[1];
     printf("总运费是：%15.4f\n",freight);
     return 0;
 }
