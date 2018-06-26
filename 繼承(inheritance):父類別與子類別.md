# 範例: 

父類別GeometricObject.cpp
```
#include "GeometricObject.h"

________::GeometricObject()
{
  color = "white";
  filled = false;
}

________::GeometricObject(const string& color, bool filled)
{
  this->color = ________;
  ________->filled = filled;
}

________ GeometricObject::getColor() const
{
  return ________;
}

________ GeometricObject::setColor(const string& color)
{
  ________ = color;
}

________ GeometricObject::isFilled() const
{
  return ________;
}

________ GeometricObject::setFilled(bool filled)
{
  ________ = filled;
}

________ ________::toString() const
{
  return "Geometric Object";
}
```
