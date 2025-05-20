
#C++ Class Generator



A simple command-line utility for generating C++ class template files with Orthodox Canonical Form (OCF) compliance.
Overview
This tool automatically generates pairs of .hpp (header) and .cpp (implementation) files for C++ classes. Each generated class includes:

Default constructor
Copy constructor
Assignment operator
Destructor

All generated classes follow the Orthodox Canonical Form (OCF), ensuring proper memory management and consistent behavior.
Requirements

C++ compatible compiler (for std::filesystem support)
Standard C++ libraries

Compilation
Compile the program using:
c++ class_generator.cpp -o class_generator 
Usage
'''
./class_generator [class_name1] [class_name2] ... [class_nameN]
'''
Example: 

 
./class_generator animal person vehicle

This will generate the following files:

Animal.hpp and Animal.cpp
Person.hpp and Person.cpp
Vehicle.hpp and Vehicle.cpp

Generated File Structure
Header File (.hpp)
cpp#ifndef CLASSNAME_HPP
# define CLASSNAME_HPP
# include <iostream>
class ClassName
{
    public:
        ClassName(void);
        ClassName(const ClassName& other);
        ClassName &operator=(const ClassName &other);
        ~ClassName();
};
#endif
Implementation File (.cpp)
cpp#include "ClassName.hpp"
// Default constructor
ClassName::ClassName(void)
{
    std::cout << "Default constructor called" << std::endl;
    return ;
}
// Copy constructor
ClassName::ClassName(const ClassName &other)
{
    std::cout << "Copy constructor called" << std::endl;
    (void) other;
    return ;
}
// Assignment operator overload
ClassName &ClassName::operator=(const ClassName &other)
{
    std::cout << "Assignment operator called" << std::endl;
    (void) other;
    return (*this);
}
// Destructor
ClassName::~ClassName(void)
{
    std::cout << "Destructor called" << std::endl;
    return ;
}
Customization
You can modify the class templates in the createClassFiles() function to include additional methods, member variables, or change the formatting to match your coding style preferences.
