# 範例: 

父類別GeometricObject.cpp
```
#include "GeometricObject.h"

________::GeometricObject() --> GeometricObject
{
  color = "white";
  filled = false;
}

________::GeometricObject(const string& color, bool filled) --> GeometricObject
{
  this->color = ________; --> color
  ________->filled = filled; -->this
}

________ GeometricObject::getColor() const  --> string
{
  return ________; --> color
}

________ GeometricObject::setColor(const string& color) --> void
{
  ________ = color; --> this->color
}

________ GeometricObject::isFilled() const --> bool
{
  return ________; --> filled
}

________ GeometricObject::setFilled(bool filled) --> void
{
  ________ = filled; --> this->filled
}

________ ________::toString() const --> string GeometricObject
{
  return "Geometric Object";
}
```

### 作業:寫下DerivedRectangle.h

```
#ifndef RECTANGLE_H
#define RECTANGLE_H
#________ "GeometricObject.h" --> include

________ Rectangle: ________ GeometricObject --> class 、 public
{
________: --> public
  Rectangle();
  Rectangle(_______,_________);
  Rectangle(_______,_________,_________,_____);
  double _________ const;
  void _________;
  double _________ const;
  void _________(double);
  double _________const;
  double _________ const;
  string toString() const;

 _________:
  _________ width;
  _________ height;
};  // Must place semicolon here

#endif
```

==>子類別:Circle  繼承 父類別:GeometricObject

```
#include "DerivedCircle.h"

// Construct a default circle object
________::Circle()
{
  radius = 1;
}

// Construct a circle object with specified radius
Circle::Circle(double radius)
{
  setRadius(________);
}

// Construct a circle object with specified radius,
//  color and filled values
Circle::Circle(double radius, const string& color, bool filled)
{
  ________ = radius;
  setColor(color);
  setFilled(filled);
}

// Return the radius of this circle
double Circle::getRadius() const
{
  return ________;
}

// Set a new radius
void Circle::setRadius(double radius)
{
  this->radius = ________;
}

// Return the area of this circle
double Circle::getArea() const
{
  return ________ * 3.14159;
}

// Return the perimeter of this circle
double Circle::getPerimeter() const
{
  return ________ * 3.14159;
}

// Return the diameter of this circle
double Circle::getDiameter() const
{
  return ________;
}

// Redefine the toString function
string ________::toString() const
{
  return "Circle object";
}
```

### 作業:寫下DerivedCircle.h

主測試程式:TestGeometricObject.cpp
```
#________ "GeometricObject.h"
#________ "DerivedCircle.h"
#________ "DerivedRectangle.h"
#________ <iostream>

________ namespace std;

________ main()
{
//建立一個GeometricObject物件顏色(color)為red,有填
  GeometricObject shape;
  shape.setColor("________");
  shape.setFilled(________);
  cout << shape.toString() << endl
    << " color: " << shape.________
    << " filled: " << (shape.________? "true" : "false") << endl; 

//建立一個Circle物件半徑為11,顏色為black,沒填
  ________ circle(________);
  circle.setColor(________);
  circle.setFilled(________);
  cout << circle.toString()<< endl
    << " color: " << circle.________
    << " filled: " << (circle.________ ? "true" : "false") 
    << " radius: " << circle.________
    << " area: " << circle.________
    << " perimeter: " << circle.getPerimeter() << endl;

//建立一個Rectangle物件,顏色為orange,有填
  ________ rectangle(2, 3);
  rectangle.setColor("________");
  rectangle.setFilled(________);
  cout << rectangle.toString()<< endl
    << " color: " << circle.________
    << " filled: " << (circle.________ ? "true" : "false") 
    << " width: " << rectangle.________
    << " height: " << rectangle.________
    << " area: " << rectangle.________
    << " perimeter: " << rectangle.________ << endl;

  return 0;
}
```

### 作業:完成上述範例的UML類別圖

# 建構函式鏈(constructor chaining)與解構函式鏈(destructor chaining)

當建立子類別的物件時，子類別執行其自己的工作前，將呼叫父類別的建構函式。若父類別又繼承自其他類別，父類別建構函式在執行其工作前，將呼其父類別的建構函式，此過程將繼續進行到繼承鏈的最後一個建構函式。這稱之為建構函式鏈(constructor chaining)。

相反的，解構函式以相反的順序執之。當子類別物件被刪除時，子類別的解構函式將呼叫。當其工作執行完後，再呼叫其父類別的解構函式。此過程一直持續到繼承鏈的最後一個解構函式被呼叫。這稱之為解構函式鏈(destructor chaining)。

```
#include <iostream>
using namespace std;

class Person
{
public:
  Person()
  {
    cout << "Performs tasks for Person's constructor" << endl;
  }

  ~Person()
  {
    cout << "Performs tasks for Person's destructor" << endl;
  }
};

class Employee: public Person
{
public:
  Employee()
  {
    cout << "Performs tasks for Employee's constructor" << endl;
  }

  ~Employee()
  {
    cout << "Performs tasks for Employee's destructor" << endl;
  }
};

class Faculty: public Employee
{
public:
  Faculty()
  {
    cout << "Performs tasks for Faculty's constructor" << endl;
  }

  ~Faculty()
  {
    cout << "Performs tasks for Faculty's destructor" << endl;
  }
};

int main()
{
  Faculty faculty;

  return 0;
}
```

# protected 關鍵字

>* 允許子類別來存取定義在父類別中的資料項目或函式
>* 不允許非子類別存取這些資料項目與函式

```
#include <iostream>
using namespace std;

class B
{
public:
  int i;

protected:
  int j;

private:
  int k;
};

class A: public B
{
public:
  void display() const
  {
    cout << i << endl; // Fine, can access it
    cout << j << endl; // Fine, can access it
    cout << k << endl; // Wrong, cannot access it
  }
};

int main()
{
  A a;
  cout << a.i << endl; // Fine, can access it
  cout << a.j << endl; // Wrong, cannot access it
  cout << a.k << endl; // Wrong, cannot access it

  return 0;
}
```
