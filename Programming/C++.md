- # **Operators**
|Operator|	Description|
|-------|--------------|
|+  |	addition
|-  |	subtraction
|*  |	multiplication
|/  |	division
|%  |	modulo
|+= | (y += x)	same as y = y + x
|-= | (y -= x)	same as y = y - x
|*= | (y *= x)	same as y = y * x
|++ |	increment by 1
|-- |	decrement by 1
|== |	equal to
|!= |	not equal to
|>  |	greater than
|<  |	less than
|>= |	greater than or equal to
|<= |	less than or equal to
|&& |	logical AND
| \|\| |	logical OR
|!  |	logical NOT

- # **Data Types**
    - ## **Numerical data types**
    |Type Name|	Bytes|	Alias|	Range|
    |---------|------|-------|-------|
    |int	|4|	signed|	–2,147,483,648 to 2,147,483,647|
    |unsigned int|	4|	unsigned|	0 to 4,294,967,295|
    |__int8|	1|	char|	-128 to 127|
    |unsigned __int8|	1|	unsigned char|	0 to 255|
    |__int16|	2|	short, short int, signed short int|	–32,768 to 32,767|
    |unsigned __int16|	2|	unsigned short, unsigned short int|	0 to 65,535|
    |__int32|	4|	signed, signed int, int|	–2,147,483,648 to 2,147,483,647|
    |unsigned __int32|	4|	unsigned, unsigned int|	0 to 4,294,967,295|
    |__int64|	8|	long long, signed long long|	–9,223,372,036,854,775,808 to 9,223,372,036,854,775,807|
    |unsigned __int64|	8|	unsigned long long|	0 to 18,446,744,073,709,551,615|
    |short|	2|	short int, signed short int|	-32,768 to 32,767|
    |unsigned short|	2|	unsigned short int|	0 to 65,535|
    |long|	4|	long int, signed long int|	–2,147,483,648 to 2,147,483,647|
    |unsigned long|	4|	unsigned long int|	0 to 4,294,967,295|
    |long long|	8|	none|	–9,223,372,036,854,775,808 to 9,223,372,036,854,775,807|
    |unsigned long long|	8|	none|	0 to 18,446,744,073,709,551,615|
    |float|	4|	none|	3.4E +/- 38 (7 digits)|
    |double|	8|	none|	1.7E +/- 308 (15 digits)|
    |long double|	8|	none|	1.7E +/- 308 (15 digits)|
    - ## **Character data types**
    |Type Name|	Bytes|	Alias|	Range|
    |---|---|---|----|
    |char|	1|	none|	–128 to 127 by default 0 to 255 when compiled by using /J|
    |signed char|	1|	none|	-128 to 127|
    |unsigned char|	1|	none|	0 to 255|
    |wchar_t, char16_t, and char32_t|	2 or 4|	__wchar_t|	0 to 65,535 (wchar_t & char16_t), 0 to 4,294,967,295 (char32_t)|
    - ## **Other data types**
    |Type Name|	Bytes|	Alias|	Range|
    |---|---|---|----|
    bool|	1|	none|	true or false
    enum|	varies|	none|	dependant on the enclosed data types
    - ## **Arrays**
    ```c++
    int arrayName[10];
    int arrayName[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int arrayName[10] = {1, 2, 3};
    ```
    - ## **Strings**
    ```c++
    char isAString[6] = { 'H', 'e', 'l', 'l', 'o', '\0'}; 
    char isNotAString[5] = { 'H', 'e', 'l', 'l', 'o'}; 
    cout << isAString << endl; 
    cout << isNotAString << endl;

    char isAString[6] = "Hello"; 
    char isAnotherString[] = "Array size is inferred";

    #include <iostream>
    #include <string>
    using namespace std; 
    string myString = "Hello!"; 
    std::string myNewString = "Less typing";
    ```
    - ## **Structures**
    ```c++
    struct coffeeBean 
    { 
        string name; 
        string country; 
        int strength; 
    }; 

    coffeeBean myBean = { "Strata", "Columbia", 10 }; 
    coffeeBean newBean; 
    newBean.name = "Flora"; 
    newBean.country = "Mexico"; 
    newBean.strength = 9; 
    cout << "Coffee bean " + newBean.name + " is from " + newBean.country << endl;
    ```
    - ## **Unions**
    ```c++
    union numericUnion 
    { 
        int intValue; 
        long longValue; 
        double doubleValue; 
    }; 
    numericUnion myUnion; 
    myUnion.intValue = 3; 
    cout << myUnion.intValue << endl; 
    3
    myUnion.doubleValue = 4.5; 
    cout << myUnion.doubleValue << endl; 
    4.5
    cout << myUnion.intValue; cout << endl;
    0
    ```
    - ## **Enumerations**
    ```c++
    enum Day { Sunday = 1, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday }; 
    Day payDay; 
    payDay = Thursday; 
    cout << payDay << endl;
    ```
    - ## **Pointers**
    A pointer is simply a variable that holds the memory address of an object in C++.  To use pointers, you create a pointer variable.  As an example, if we want to, we can create a variable to point to our num variable's address in memory by using the following line of code:
    ```c++
    int num = 3;
    Int *pNum = &num;
    ```
    In this line of code, **int*** is referred to as a **pointer** to an int. In other words, it will contain the memory address of an int data type. The variable that will actually hold that memory address is called pNum. After the assignment operator, we see the use of the **&** symbol.  the **&** symbol, in this instance, is known as the  address-of operator and it allows us to get at the memory address of the num variable.
    
    **You should always initialize a pointer variable to NULL, nullptr, 0, or with a memory address.** Leaving a pointer variable uninitialized is an error that can result in difficult to find bugs and create security issues for your code.

    If you have a variable, described (for example) as:
    ```c++
    int a;
    ```
    To get it's address, you use the **&** operator:
    ```c++
    printf("%p", &a);
    ```
    To define a pointer variable to a given type (in this example int), use the **\*** operator, for example:
    ```c++
    int *b;
    ```
    Now you can have *b* point to the same address as *a* using the:
    ```c++
    b=&a;  //pointer b now is pointing to the same address as variable a.
    ```
    To print the pointer:
    ```c++
    printf("%p", b);
    ```
    To print the value stored at the pointer's address, use the * operator. This time, * tells the compiler to access the value, instead of the address:
    ```c++
    printf("%i", *b);
    ```
    To pass parameters by reference:
    ```c++
    void main(){
	    int a = 1;
	    int b = 2;
	    swap(&a,&b);	//pass the addresses of variables a and b, instead of their values
    }

    void swap(int *x, int *y){		//take two pointers as parameters
	    int tmp;				  //regular variable
	    tmp = *x;				  //tmp gets the value stored in pointer x
	    *x = *y;				  //the memory location to which x is pointing gets the value stored in pointer x
        *y = tmp;				  //the memory location to which y is pointing gets the value of tmp
    }
    ```
    ### **The dereference operator**
    This operator is another source of confusion for those who are new to pointers. The reason is because we are "overloading" the use of the **\*** symbol. It is used as the pointer symbol and also as the dereference symbol.  So what is a dereference?  Consider the following code sample.
    ```c++
    int num = 3;            // a simple variable holding the value 3
    int *pNum = &num;        // a pointer holding the address of num
    cout << pNum << endl;    // output the memory address of num
    cout << *pNum << endl;    // output the value 3
    *pNum = 45;
    cout << *pNum << endl;
    cout << num << endl;
    ```
    On the first line, we declare a variable called num and assign it the value 3. Next we create a pointer **\*pNum** and assign it the memory address of the variable **num**. The first cout statement outputs the address of **num**, because that is what the pointer variable **pNum** holds. But the last line outputs the value 3.
    ### **Reference types**
    A reference type is simply an alias for another type. It overloads the use of the **&** operator.
    
    You declare a reference type using a syntax similar to declaring a pointer variable. That is, you declare the data type for the C++ variable or object that will be referred to, then you use the **&** character followed immediately by the reference type name. It's important to note that when declaring a reference, you must assign it at that time. It behaves similar to a constant in this sense. An example demonstrates the declaration. 
    
    The reference cannot be reassigned later in program code.
    ```c++
    int num = 3;
    int &refNum = num;
    int &refNum2;                          //causes an error
    cout << refNum << endl;
    ```
    References are commonly used as function parameters. **Pass-by-reference** means to pass the reference of an argument in the calling function to the corresponding formal parameter of the called function. The called function can modify the value of the argument by using its reference passed in.
    ```c++
	 void passByRef(int &num1);
     ```
    When you use **pass-by-value**, the compiler copies the value of an argument in a calling function to a corresponding non-pointer or non-reference parameter in the called function definition. The parameter in the called function is initialized with the value of the passed argument. As long as the parameter has not been declared as constant, the value of the parameter can be changed, but the changes are only performed within the scope of the called function only; they have no effect on the value of the argument in the calling function.


