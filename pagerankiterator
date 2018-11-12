#include <stdio.h>
#include <math.h>
#include <vector>
#include <iterator>
#include <iostream>

void
kiir (std::vector <double> tomb)
{
std::vector<double>::iterator ptr;
int i = 0;
for (ptr = tomb.begin(); ptr != tomb.end(); ptr++)
	std::cout<<"Pagerank: "<<i++<<" "<<*ptr<<'\n';
}

double tavolsag(std::vector <double> pagerank,std::vector <double> pagerank_temp)
{
double tav = 0.0;
for(int i=0;i<pagerank.size();i++)
tav +=abs(pagerank[i] - pagerank_temp[i]);
return tav;
}

int main(void)
{
std::vector <std::vector <double>> L = {
{0.0, 0.0, 1.0 / 3.0, 0.0},
{1.0, 1.0 / 2.0, 1.0 / 3.0, 1.0},
{0.0, 1.0 / 2.0, 0.0, 0.0},
{0.0, 0.0, 1.0 / 3.0, 0.0}
};

std::vector <double> PR = {0.0, 0.0, 0.0, 0.0};
std::vector <double> PRv = {1.0 / 4.0, 1.0 / 4.0, 1.0 / 4.0, 1.0 / 4.0};

long int i,j,h;
i=0; j=0; h=5;

for (;;)
{
for(i=0;i<4;i++)
PR[i] = PRv[i];
for (i=0;i<4;i++)
{
double temp=0;
for (j=0;j<4;j++)
temp+=L[i][j]*PR[j];
PRv[i]=temp;
}

if ( tavolsag(PR,PRv) < 0.00001)
break;
}
kiir (PR);
return 0;

}
