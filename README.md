# Lab 01
## C ++ Overloading of operator and functions.
Authors: Jarosław Bułat, Artur Kos. Updated by: Andres Vejar.


#### Exercise 1. Constructor overloading.

1. Compile and run the program `ex_1.cpp`:
```cpp
#include <iostream>
using namespace std;

class Vector {
public:
  Vector(double);
  size_t dimension_;
private:
  double data_[3] = {0,0,0};
};

Vector::Vector(double element1) {
  cout << endl << "Creating a new Vector class object in R1 space:" << endl;
  dimension_ = 1;
  data_[0] = element1;
}

int main(void) {
  Vector r1(1.0); // R1
  cout << "Vector class object with number of dimensions:"
       << r1.dimension_  << endl;
  return EXIT_SUCESS;
}       
```
2. Add to the `Vector` class new constructors with 2 and 3 arguments corresponding to 2 or 3 dimensional vectors.
3. Change the text displayed when the overloaded constructors are creating new objects (dimension 2 or 3). 
   Change the value that is assigned to the variable `dimension_` (`dimension_` informs whether the vector is 2D or 3D).
4. In the `main ()` function demonstrate the different outputs calling of the all overloaded constructors.


#### Exercise 2. Function overloading.
  
1. Add to the modified code from the previous exercise two overloaded functions (external functions, not methods of the `Vector` class).
2. Change the access specifier of the `data_` element to `public`.
3. The first overloaded function should be called using single variable of the`double` type and should display value of this variable.
4. The second function should be called using single object of the `Vector` type and should display values of all elements of the array` data_`
   (based on the information of the array dimension stored in the component `dimension_`).
5. In the `main()` function demonstrate the operation of both overloaded functions.


#### Exercise 3. Method overloading.
  
1. Based on the code from the previous exercise, transform both overloaded functions into an overloaded methods of the `Vector` class.
2. Change the access specifier of the `data_` element to `public`.
3. The first overloaded method should be called using single variable of the`double` type and it should display the value of this variable.
4. The second method should be called using a single object of the `Vector`
   type and it should display the values of all the elements of the array`
   data_` (based on information about the array dimension stored in the component `dimension_`).
5. In the `main()` function demonstrate the operation of both overloaded methods.


#### Exercise 4. Operator overloading.

1. Add to the modified code from the previous exercise a new, external
(outside the `Vector` class ) definition of the` + `operator.
2. An overloaded operator should:
- be called using two `Vector` objects
- add the corresponding elements of the `data_` arrays of the `Vector` objects
- create a new `Vector` object to store the result of performed adding operation
  To simplify the task, you can limit the operation of the `+` operator to
  the `Vector` class objects created with the two-arguments version of the
  constructor.  
3. In the `main()` function demonstrate the successful execution of the overloaded operator.

