# Lab 02 
## C++: Inheritance 1
Authors: Jarosław Bułat, Artur Kos. Updated by: Andres Vejar.


### Exercise 1
1. Try to compile and run the following code:
```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
private:
  void printDescription();
public:
  Student();
  string description = "A student of the group";
};

Student::Student() {
  cout << "Creating an object of the class "
          "Student, with description: "
       << endl << " " << description << endl;
}

void Student::printDescription() {
  cout << "description: " << description << endl;
}

class Chairman {
public:
  string description = "A chairman of the group";
};

int main() {
  Student stud;
  stud.printDescription();
  return EXIT_SUCCESS;
}
```

Why the program is not compiling? Find the error, correct the code, and run
the program again. Pay attention to the messages displayed on the screen.


2. Modify the program so that the `Chairman` class will inherit from the
`Student` class.

3. Create a new `Chairman` object and run the program.  What are the
messages displayed?  What can be concluded about the constructor execution
order?

4. Call the `printDescription()` method for created object. What are the
messages displayed?  What is the conclusion with respect to the execution
of the inherited method?

5. Place the modified code **in your branch** in the remote repository.


### Exercise 2
Using the code from **Exercise 1**: 

1. Modify the `Chairman` class so now it will contain its own
`printDescription()` method, differing only in the content of the
displayed message.

2. Call the `printDescription()` method for created object.  What are the
messages displayed?  What is the conclusion with respect to the execution
of the new method?

3. Place the modified code **in your branch** in the remote repository.

### Exercise 3
Run the following code:

```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
public:
  string name_surname = "NO_NAME";
  unsigned int id_number = 0;
  string description = "A student of the group";
  Student(string name_surname, unsigned int id_number);
  void printDescription();
  void printData() {
    cout << " Method print_data() of the base class" << endl;
    cout << " name surname " << name_surname << endl;
    cout << " id number " << id_number << endl;
  }
};

class Chairman : public Student {
public:
  string email = "no@noemail";
  Chairman(string name_surname, unsigned int id_number, string email);
  string description = "A chairman of the group";
};

Chairman::Chairman(string name_surname, unsigned int id_number, string email)
  : Student(name_surname, id_number)
  , email(email) {
  cout << "Creating an object of the Chairman class named: "
       << description << endl;
}

Student::Student(string name_surname, unsigned int id_number)
  : name_surname(name_surname)
{
  id_number = id_number;
  cout << "Creating an object of the Student class named: "
       << description << endl;
}

void Student::printDescription()
{
  cout << "Description: " << description << endl;
}

int main() {
  Student stud("Jan Kowalski", 7);
  stud.printDescription();
  cout << "Data:"
       << stud.name_surname << " "
       << stud.id_number << endl;
  Chairman chair("Aleksandra Nowak", 999, "mail@nomail.dot");
  chair.printDescription();
  cout << "Data:"
       << chair.name_surname << " "
       << chair.id_number << endl;
       
  return EXIT_SUCCESS;
}
```
1. Analyze its operation. Note how a new, derived class object is created.
2. Modify the definition of the base class so that the members
`surname_name` and `id_number` will be private.
3. Run the program. Did the result changed? What is the conclusion?

4. Add the `printData()` method to the `chairman` class, which will also
include `email`. Is it possible to access to the components `name_surname` and
`id_number`? Correct the program so it will be displaying all `chairman`
class data correctly.

5. Place the modified code **in your branch** in the remote repository.
