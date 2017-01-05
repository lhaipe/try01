# try01
basic C++
#include<iostream>
unsing namespace std;

class Test
{
puvlic:
  Test()
  {}
  Test(int d)
  {
    data=d;
  }
  Test(const Test &t)
  {
    data=t.data;
  }
  Test& operator=(const Test &t)
  {
    if(this != &t)
    {
      data=t.data;
    }
    return *this;
  }
  ~Test()
  {}
  int GetData()const
  {
    return data;
  }
private:
  int data; 
}

Test fun(Test &x)
{
  int value=x.GetData();
  return  Test(value);
}

void main()
{
  Test t1;
  Test t2(10);
  Test t3(t2);
  Test t4;
  t4=fun(t3);
  const Test t5;
  const Test &t6=t5;
}
