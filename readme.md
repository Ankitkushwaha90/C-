Creating a comprehensive tutorial page for C++ with Object-Oriented Programming (OOP) examples involves covering the key concepts: classes, objects, inheritance, polymorphism, encapsulation, and abstraction. Below is a structured guide along with example code snippets for each concept.

# C++ Object-Oriented Programming (OOP) Tutorial
## Table of Contents
1. - Introduction to OOP
- 2. Classes and Objects
- 3. Encapsulation
- 4. Inheritance
- 5. Polymorphism
- 6. Abstraction
Example Project
### 1. Introduction to OOP
Object-Oriented Programming (OOP) is a programming paradigm that uses "objects" to represent data and methods. It promotes greater flexibility and maintainability in programming.

## Key Concepts:
- `Classes`: Blueprints for creating objects.
- `Objects`: Instances of classes.
- `Encapsulation`: Restricting access to certain components.
- `Inheritance`: Mechanism to create new classes based on existing ones.
- `Polymorphism`: Ability to process objects differently based on their data type or class.
- `Abstraction`: Hiding complex implementation details and showing only the essential features.
### 2. Classes and Objects
Example: Basic Class and Object
```cpp
#include <iostream>
using namespace std;

class Dog {
public:
    string name;
    int age;

    void bark() {
        cout << name << " says: Woof!" << endl;
    }
};

int main() {
    Dog myDog;
    myDog.name = "Buddy";
    myDog.age = 3;
    
    myDog.bark();  // Output: Buddy says: Woof!
    return 0;
}
```
### 3. Encapsulation
Encapsulation is the bundling of data and methods that operate on that data within one unit (class). It restricts direct access to some components.

Example: Using Access Modifiers
```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    double balance;

public:
    BankAccount(double initialBalance) {
        balance = initialBalance;
    }

    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    void displayBalance() {
        cout << "Balance: $" << balance << endl;
    }
};

int main() {
    BankAccount account(100.0);
    account.deposit(50);
    account.displayBalance();  // Output: Balance: $150
    return 0;
}
```
### 4. Inheritance
Inheritance allows a new class to inherit properties and behaviors from an existing class.

Example: Simple Inheritance
```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    void eat() {
        cout << "Eating..." << endl;
    }
};

class Cat : public Animal {
public:
    void meow() {
        cout << "Meow!" << endl;
    }
};

int main() {
    Cat myCat;
    myCat.eat();  // Output: Eating...
    myCat.meow();  // Output: Meow!
    return 0;
}
```
### 5. Polymorphism
Polymorphism allows methods to do different things based on the object that it is acting upon.

Example: Function Overriding
```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void sound() {
        cout << "Animal sound" << endl;
    }
};

class Dog : public Animal {
public:
    void sound() override {
        cout << "Bark" << endl;
    }
};

class Cat : public Animal {
public:
    void sound() override {
        cout << "Meow" << endl;
    }
};

void makeSound(Animal* animal) {
    animal->sound();
}

int main() {
    Dog myDog;
    Cat myCat;

    makeSound(&myDog);  // Output: Bark
    makeSound(&myCat);  // Output: Meow
    return 0;
}
```
### 6. Abstraction
Abstraction allows focusing on the essential characteristics while hiding the implementation details.

Example: Abstract Class
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual void draw() = 0;  // Pure virtual function
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing Circle" << endl;
    }
};

class Square : public Shape {
public:
    void draw() override {
        cout << "Drawing Square" << endl;
    }
};

int main() {
    Circle circle;
    Square square;

    circle.draw();  // Output: Drawing Circle
    square.draw();  // Output: Drawing Square
    return 0;
}
```
### 7. Example Project: Library Management System
Overview
This project will demonstrate a simple library management system using OOP principles.

Code Example
```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

class Book {
private:
    string title;
    string author;

public:
    Book(string t, string a) : title(t), author(a) {}

    void display() {
        cout << "Title: " << title << ", Author: " << author << endl;
    }
};

class Library {
private:
    vector<Book> books;

public:
    void addBook(Book book) {
        books.push_back(book);
    }

    void displayBooks() {
        for (const auto& book : books) {
            book.display();
        }
    }
};

int main() {
    Library library;
    library.addBook(Book("1984", "George Orwell"));
    library.addBook(Book("To Kill a Mockingbird", "Harper Lee"));

    cout << "Books in the library:" << endl;
    library.displayBooks();
    
    return 0;
}
```
### Conclusion
This tutorial provided a basic overview of Object-Oriented Programming in C++ with examples. You can further explore more complex topics such as multiple inheritance, interfaces, and design patterns as you become more comfortable with these concepts.

Feel free to experiment with the code snippets provided and expand upon them to deepen your understanding of C++ and OOP!

