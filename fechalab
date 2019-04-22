//Fecha.h
#pragma once
#include <string>
using namespace std;
class Fecha
{
private:
	int d,m,a;
public:
	Fecha(int _d, int _m, int _a);
	Fecha(long _f);
	Fecha(string _date);
	~Fecha(void);
	bool validarfecha();
	int devolverdia();
	int devolvermes();
	int devolveranio();
};

#include "StdAfx.h"
#include "Fecha.h"
#include <string>
using namespace std;

Fecha::Fecha(int _d,int _m,int _a )
{
	d=_d;
	m=_m;
	a=_a;
}

Fecha::Fecha(long _f)  //10112019 
{
	d= int(_f/1000000);
	m= int((_f-(d*1000000))/10000);
	a= int((_f-(d*1000000))-m*10000);
}

Fecha::Fecha(string _date)
{
	d=(atoi(_date.substr(0,2).c_str()));
	m=(atoi(_date.substr(3,2).c_str()));
	a=(atoi(_date.substr(6,4).c_str()));
}

Fecha::~Fecha(void)
{
}

bool Fecha::validarfecha()
{
   bool t=true;
   if(m>=1 && m<=12){
	   if(m==1 || m==3 || m==5 || m==7 || m==8 || m==10 || m==12)
	     if (d>=1 && d<=31)
		   return t;
	     else 
		   t=false;
	   else
		   if (m==4 || m== 6 || m==9 || m==11)
	           if(d>=1 && d<=30)
				   return t;
		       else 
				   t=false;
		   else 
			   //febrero
			   if(a%400==0 || (a%4==0 && a%100!=0))
				  if (d>=1 && d<=29)
					  return t;
				  else 
					  t=false;
			   else
				   if (d>=1 && d<=28)
					   return t;
				   else 
					   t=false;
}
}

int	Fecha::devolverdia()
{
	return d;
}
int Fecha::devolvermes()
{
	return m;
}
int Fecha::devolveranio()
{
	return a;
}

#include "stdafx.h"
#include "stdlib.h"
#include "Fecha.h"
#include <string>
#include <iostream>
#include "conio.h"
using namespace std;

void main()
{
	int d,m,a,opc,dd,mm,aa;
	string date;
	long f;

	cout<<"Que estilo de fecha desea ingresar: "<<endl;
	cout<<" 1.- dd , mm, aaaa."<<endl;
	cout<<" 2.- ddmmaaaa"<<endl;
	cout<<" 3.- dd/mm/aaaa"<<endl;
	cout<<" 4.- Salir"<<endl;
	cin>>opc;

	switch(opc)
	{
		case 1:	
				system("CLS");
				cout<<"Ingrese el dia: ";
				cin>>d;
				cout<<"Ingrese el mes: ";
				cin>>m;
				cout<<"Ingrese el año: ";
				cin>>a;
				break; //todo esto esta copiado del github realizado por Eduardo Suarez Bort

		case 2:
				system("CLS");
				cout<<"Ingrese la fecha: ";
				cin>>f;
				break;
		case 3:
				system("CLS");
				cout<<"Ingrese la fecha: ";
				getline(cin,date);
				break;
		case 4:	
				system("CLS");
				cout<<"Adios";
				break;
	}
	
	if(opc==1)
	{
		Fecha f1(d,m,a);
			if(f1.validarfecha()==true)
				{	
					dd=f1.devolverdia();
					mm=f1.devolvermes();
					aa=f1.devolveranio();
					cout<<"La fecha es: "<<dd<<"/"<<mm<<"/"<<aa;
				}else
				{
					cout<<"Fecha erronea";
				}
	}else
	{ if (opc==2)
		{	
			Fecha f1(f);
			if(f1.validarfecha()==true)
				{	
					dd=f1.devolverdia();
					mm=f1.devolvermes();
					aa=f1.devolveranio();
					cout<<"La fecha es: "<<dd<<"/"<<mm<<"/"<<aa;
				}else
				{
					cout<<"Fecha erronea";
				}
		}else
		{
			if (opc==3)
			{
				Fecha f1(date);
				if(f1.validarfecha()==true)
				{		
					dd=f1.devolverdia();
					mm=f1.devolvermes();
					aa=f1.devolveranio();
					cout<<"La fecha es: "<<dd<<"/"<<mm<<"/"<<aa;
				}else
				{
					cout<<"Fecha erronea";
				}
			}
		}
	}
	
	getch();
}
