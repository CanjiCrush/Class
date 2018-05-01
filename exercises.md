Exercises.1:陣列存取與基本運算(2018/4/10)
```
把一個陣列元素全部都平方存到另一個陣列
把一個陣列元素全部都反轉存到另一個陣列
(參考老師上課之內容!)
```
```
(參考老師上課之內容!)
#include <iostream>
using namespace std;

int main()
{
  const int NUMBER_OF_ELEMENTS = 2;
  double numbers[NUMBER_OF_ELEMENTS];
  double numbers_squared[NUMBER_OF_ELEMENTS];
  double sum = 0;

  for (int i = 0; i < NUMBER_OF_ELEMENTS; i++)
  {
    cout << "輸入一個數字: ";
    cin >> numbers[i];
    sum += numbers[i];
    numbers_squared[i]=numbers[i]*numbers[i];
  }
  cout << "第二數為：" << numbers[1] << endl;
  cout << "第二數平方為" << numbers_squared[1] << endl;
  
  double average = sum / NUMBER_OF_ELEMENTS;

  int count = 0; // The number of elements above average
  for (int i = 0; i < NUMBER_OF_ELEMENTS; i++)
    if (numbers[i] > average)
      count++;

  cout << "平均為：" << average << endl;
  cout << "Number of elements above the average " << count << endl;
  system("pause"); 
  return 0;
}
(2018/4/10)
```
## 結果:

![結果](/PIC/EX1.PNG "結果")



Exercises.2:(2018/4/17)
```
(參考老師上課之內容!)
#include <iostream>
#include <iomanip>
using namespace std;
int fun(int array[3][3])
{
	int i,j,t;
	for(i=0;i<3;i++)
		for(j=0;j<i;j++)
		{
			t=array[i][j];
			array[i][j]=array[j][i];
			array[j][i]=t;
		}
		return 0;
}

//4/17 上課作業 

int main()
{
	int i,j;
	int array[3][3]={{2,3,4},{4,5,6},{5,6,7}};
	cout << "Converted Front" <<endl;
	for(i=0;i<3;i++)
	{
		for(j=0;j<3;j++)
			cout << setw(7) << array[i][j] ;
		cout<< endl;
	}
	fun(array);
	cout << "Converted result" <<endl;
	for(i=0;i<3;i++)
	{
		for(j=0;j<3;j++)
			cout << setw(7) << array[i][j] ;
		cout<< endl;
	}
    return 0;
}
```

```
程式功用:
先在程式碼中輸入指定數字，程式執行後，會將指定的各行數字，轉換為各列數字。
```
## 結果:

![結果](/PIC/EX2.PNG "結果")


Exercises.3:球型計算(2018/5/1)
```
(參考老師上課之內容!)
#include <iostream>
using namespace std;

class Ball
{
public:
  // The radius of this circle
  double radius;

  // Construct a default circle object
  Ball()
  {
    radius = 1;
  }

  // Construct a circle object
  Ball(double newRadius)
  {
    radius = newRadius;
  }

  // Return the area of this circle
  double getArea()
  {
    return 4*radius * radius * 3.14159;
  }
};  // Must place a semicolon here

int main()
{
  Ball Ball1(1.0);
  Ball Ball2(25);
  Ball Ball3(125);
  

  cout << "The spherical of the Ball of radius "
    << Ball1.radius << " is " << Ball1.getArea() << endl;
  cout << "The spherical of the Ball of radius "
    << Ball2.radius << " is " << Ball2.getArea() << endl;
  cout << "The spherical of the Ball of radius "
    << Ball3.radius << " is " << Ball3.getArea() << endl;

  // Modify circle radius
  Ball2.radius = 100;
  cout << "The spherical of the Ball of radius "
    << Ball2.radius << " is " << Ball2.getArea() << endl;

  return 0;
}
```
## 結果:

![結果](/PIC/EX3.PNG "結果")



Exercises.4(2018/5/1)
```
(參考老師上課之內容!)
#include<iostream>
using namespace std;
int main()
{
	char c1,c2;
	c1='a';
	c2='b'; 
	int i1,i2;
	printf("%c,%d\n%c,%d",c1,c1,c2,c2);
     return 0;
}
```
## 結果:

![結果](/PIC/EX4.PNG "結果")


Exercises.5:String類別(2018/5/1)
```
(參考老師上課之內容!)
#include <iostream>
using namespace std;



int main()
{
string s1("Welcome");
s1.append(" to CPP"); 
cout << s1 << endl; 

string s2("Welcome");
s2.append(" to C and Cpp", 3,10); 
cout << s2 << endl;

string s3("Welcome");
s3.append(" to C and Cpp", 13); 
cout << s3 << endl; 

string s4("Welcome"); 
s4.append(14, 'F'); 
cout << s4 << endl; 
} 
```
## 結果:

![結果](/PIC/EX5.PNG "結果")



Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
Exercises.1
