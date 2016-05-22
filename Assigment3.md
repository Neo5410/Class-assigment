# Class-assigment
Extra credit task :P

// I dedicate this code to life
// Muhammad Hanzalah Bhutta
//37-MTS-B
#include <iostream>
#include <string>
using namespace std;

// All people are humans, we live, we earn, we eat, we sleep, we DIE
struct human {
	
	int life=1; // 1 = alive, 0 = dead
	string name;
	int money;
	int age=0;
};

int monthly_income (int money, int life){
	if (life==1) money=money*1.2;// you earn 20% of what you own
	return money;
}

int monthly_expense (int money, int life){
	int expense = 100+money*0.1;
	if (life==0) 
	expense=0;
	return expense;
}

void printing (human a){
	cout<<a.name<<" lived "<<a.age<<" number of months and has "<<a.money<<"$ money left\n" ;
}
int main (){
	
	cout<<"This code will for 12 months.It will calculate how many months each person lived with out going in to debt. "<<endl;
	human one,two,three; // All humans are equal there is not difference
	one.name= "farmer";
	 one.money=200;
	two.name= "worker";
	 two.money=500;
	three.name= "king";
	 three.money=5000; 
	 
	int month=0;
	while (month<12)// What happens in a year
	
	{
		month++;
		one.money = monthly_income(one.money,one.life)-monthly_expense(one.money,one.life);
		two.money = monthly_income(two.money,one.life)-monthly_expense(two.money,two.life);
		three.money = monthly_income(three.money,one.life)-monthly_expense(three.money,three.life);
		
		if (one.money<0) one.life=0;
		 else one.age=one.age+1; // You died by starvation or lived another month
		if (two.money<0) two.life=0;
		 else two.age=two.age+1;
		if (three.money<0) three.life=0;
		 else three.age=three.age+1;
		
	}
	
	printing(one);
	printing(two);
	printing(three);
	return 0;
}
