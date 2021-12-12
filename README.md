# task3
Data Structure Task3
Usage of const keyword:
  It can be used with (variables, pointers, functions arguments and return types, class data members, class member functions, objects).
1.	Variables:-
Specifies that a variable's value is constant and tells the compiler to prevent the programmer from modifying it.
Ex:

~~~cpp
int main
{
    const int a = 10;
    const int b = a + 10;     // works fine
    a++;     //  leads to Compile time error   
}
~~~

2.	Pointers:-
•	Make a pointer always points at the same memory location which can be useful to have a storage that its value can be changed without moving its memory location.
Ex:

~~~cpp
int x = 1;
int* const y = &x;
~~~

•	A constant pointer is used for returning constant strings and arrays from functions.

3.	Functions arguments and return types:-
•	Used to make the return type or arguments of a function as const.
Ex:

~~~cpp
const int f1()
{
return 1;
}
~~~

4.	Class Data members:-
•	Used to initialize a data variable in constructor not during declaration and make it unchangeable.
5.	Class object:-
•	Used to prevent the modification of member variables of an object either by direct modification or by calling functions that set values to object member variables.
Ex (4,5):

~~~cpp
class Test
{
    const int i;
    public:
    Test(int x):i(x)
    {
        cout << i;
    }
};
int main()
{        
        Test t2(30);  //i is initialized in constructor
  const Test t(10);  // i can never be changed after being initialized 
   
} 
~~~

6.	Class's Member function:-
•	Specifies that the function can’t modify the object when it is called as a const member function will not modify the object or call any non-const member functions that may modify the object.
Ex:

~~~cpp
class Data
{
public:
   Data(string name, int age );
   string getname() const;     //function can't modify an object
   void setage( int x );     // A write function; can't be const

private:
int age;
string name;
};

string Data::getname() const
{
   return name;        // Doesn't modify anything
}
void Data::setage( int x )
{
   age = x;          // Modifies data member
}
int main()
{
   Data person1( "Ahmed", 23 );
   const Data person2( "Karim", 18 );
   person1.setage( 4 );    // Okay
   person2.getname();    // Okay
   person2.setage( 4 ); // C2662 Error
}
~~~


Usage of & operator:
1.	 It is used as as a reference declarator to represent memory address of a variable.
Ex:

~~~cpp
int num = 20;
cout << &num;   //prints the memory address of the integer num.
~~~

2.	It is used to assign the address of a variable to a pointer.
Ex:
~~~cpp
int* ptr = &num; 
~~~

3.	It can be used as a bitwise operator which performs operations on integer data at the individual bit-level. These operations include testing, setting, or shifting the actual bits.
- The bitwise AND & operator returns 1 if and only if both the operands are 1. Otherwise, it returns 0.
Ex:

~~~cpp
int a = 12;    //00001100 (In Binary)
int b = 25;    //00011001 (In Binary)
cout << ( a & b );  // prints 8 which is 00001000 (In Binary)
~~~
