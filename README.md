# Library System
 Authors: \<[Chandler Mahkorn](https://github.com/CMahk)\> \<[Aaron Liu](https://github.com/aliu112)\>

## Project Description
The Library System is a tool that allows for the client to add media like books or magazines to a database, which they can then search through to find media similar to the criteria they are looking for.

## Why a Library System as the Project?
 **Aaron:** This is an interesting project because it dips into the realm of databases and how you can use them to display information that the users needs. These needs include what books we have and possibily the location of the book like real libraries display.
 
 **Chandler:** I have worked with small database objects in personal projects, so I wanted to further experiment with them in a group project.

## Languages and Technologies
* Primary Programming language: C++ 11

* **Inputs and outputs**
	* Not all inputs and outputs will be available depending on the given book. For example, a book may not a have cover or an author, or if it is an old book, it may not have a specified year when it was published.
	* **Input:** Books, user text
        	* Specific details per product: Title, author, cover, genre, sub-genre, date published, description, price, availability, and location
	* **Output:** Same as input if applicable (printed), book categories (printed), book hierarchy (printed), book hierarchy (text file)
 
* **Design Patterns:** Facade, Composite

	* **Aaron:** To implement the interface of this library system I have decided to use the design pattern Facade. This is the perfect design pattern for creating the interface because it essentially hides all of the complex code that the user does not need to see. It basically will mask all the code that we use to acheive the data. The user will only see a simple webpage that will display the information they need to get their book.
 
	* **Chandler:** To create a functional database of consumable media, the Composite design pattern will be used. This design pattern can be used to create an a base class that can then be utilized to create a hierarchy of objects representing the library's database. This database can then be traversed easily to present the data that the user requests, including individual books and entire categories of books.

## Class Diagrams
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/FinalFacade.png)
This diagram shows how I will be utilizing the facade design pattern to conceal all of the complex code from the user. The Library_Facade will be the class that the user will be interacting with to perform all the actions such as borrowing a book, logging in, creating an account, paying off an debts, etc. There are multiple classes that will be used to assist the facade in retreving, adding, or removing any of the necessary information. After the interface is implemented, the user will simply have to type in input which will then call the functions within the Library_Facade class. The Library_Facade class will then utilize the other classes to correctly perform the action. For example, if the user wants to login, they will simply have to type in their username and password. The Library_Facade will use a function call that utilizes the class User to check and see if the inputs values are already in the system. If it is then the user will be logged in, and if not the user will be given an error message. The bookManager is there as a place holder because Chandler will be handling the database part of the project. It is also a huge a reason for using facade because the facade will allow easy access for the user to retrieve any wanted information from the database. The facade will bascially provide one simple/easy-to-use class that will be able to provide all the functionality which will mask all the complex code that is within the other classes.
 
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/Composite.png)
This diagram describes how I will be utilizing the composite design pattern to create an interface to a functional database storing categories that then store individual books. The Library_Facade instantiates the BookManager as the Library_Facade class will be utilizing the manager to add and remove contents at will. 
* The BookManager class contains a vector that can add or remove Category objects from itself. The BookManager can display the entire class' hierarchy of categories and books stored, or just the names of the categories it is holding. The manager can also modify a category's title, modify which category a Book object is in, or find a Book within its categories. 

* The Category class also contains a vector that it uses to store Book objects, which can be added or removed whenever. The Category can find a specific Book using the overloaded findBook() function which can be called by the manager or by itself, which then returns the Book to the BookManager.
 
* The Book class will contain the essential data that differentiates itself from other Books. This includes the Book's title, author, date published, number of pages, its availability, and ISBN-13 value for easy inquiry.

## Screenshots
Exiting before account creation/logging in
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20154204.png)

Invalid Input
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/invalid%20input.png)

Incorrect Login (retry)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20154333.png)

Incorect Login (make new account)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20154422.png)

New Account 
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20154452.png)

All Library functionality (display, borrow, add, remove, etc...)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20154602.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20154629.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20155047.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20155151.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20160321.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20160657.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/Screenshot%202020-12-09%20161633.png)

Export function
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/export.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/exportFile.png)

Import Function

![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/import.png)

![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/import2.png)

![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/import3.png)

![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/import4.png)

 ## Installation/Usage
 Our program is simple and easy to use. You only need to clone the repository and run it inside of the console. Although, you will need Google tests and cmake installed to run it exactly the way we run it.
 ## Testing
 For testing we decided to go with google tests to confirm that our class functions are fully functional before we incorporated it into our interface.
 
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/test%20pt1.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/test%20pt2.png)
![](https://github.com/CMahk/CS100-Final-Project-Library-System/blob/main/InputOutput/test%20pt3.png)
 
