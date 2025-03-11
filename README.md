# Library Management System(LMS)

## Overview

The Library Management System is a comprehensive C++ application designed to manage library operations efficiently. It provides functionality for managing books, users (students, faculty, and librarians), borrowing and returning books, and tracking fines. The system maintains persistent data through file storage and provides different interfaces for different user types.

## Features

### User Management

- **Multiple User Types**: Support for Students, Faculty, and Librarians
- **Authentication**: Username and password-based login system
- **Role-based Access**: Different functionalities based on user roles
- **User Administration**: Add, remove and update user details

### Book Management

- **Book Inventory**: Add, remove, and update book details
- **Search Functionality**: Find books by ISBN
- **Availability Status**: Track whether books are available, borrowed, or reserved

### Borrowing System

- **Borrow/Return Books**: Process for borrowing and returning books
- **Borrowing Limits**: 3 books for students, 5 books for faculty
- **Fine Management**: Calculate and process fines for overdue books
- **Borrowing History**: Track and display complete borrowing history

### Fine System

- **Automatic Fine Calculation**: Fine calculated based on days overdue
- **Different Rules for Different Users**: Students pay fines after 15 days, Faculty after 60 days
- **Fine Payment**: Process for paying fines

### Data Persistence

- **File-based Storage**: All data is stored in text files
- **Automatic Data Loading**: System loads data at startup
- **Regular Data Saving**: Changes are saved to ensure data integrity

## Implementation Details

### Class Structure

- **Book Class**: Manages book information and status
- **User Class**: Base class for all user types
- **Student Class**: Derived from User, includes student-specific functionality
- **Faculty Class**: Derived from User, includes faculty-specific functionality
- **Librarian Class**: Derived from User, includes administrative functionality
- **Library Class**: Main class that coordinates all operations
- **BorrowRecord Class**: Tracks borrowing history

### File Structure

- **books_data.txt**: Stores book information
- **students_data.txt**: Stores student information
- **faculties_data.txt**: Stores faculty information
- **librarians_data.txt**: Stores librarian information
- **borrow_history.txt**: Stores complete borrowing history

## Installation and Setup

### Prerequisites

- C++ compiler (GCC, Clang, MSVC, etc.)
- Basic knowledge of command-line interface

### Installation Steps

1. Clone the repository or download the source code
2. Navigate to the project directory
3. Compile the source code using your preferred C++ compiler:
   ```bash
   g++ Library_Management_System_Aritra_Ambudh_Dutta_230191.cpp -o lms
   ```
4. Run the compiled executable:
   ```bash
   ./lms
   ```

### First-time Setup

- On first run, the system will automatically create necessary data files with sample data
- Default users:
  - Students: Student1-Student5 (password: password1-password5)
  - Faculty: Faculty1-Faculty3 (password: password1-password3)
  - Librarians: Librarian1-Librarian3 (password: password1-password3)

## Usage Guide

### Login

1. Start the program
2. Select your role (1 for Student, 2 for Faculty, 3 for Librarian)
3. Enter your username and password

### Student Operations

1. **Borrow Book**: Borrow a book using its ISBN (limit: 3 books)
2. **Return Book**: Return a borrowed book
3. **Pay Fine**: View and pay fines for overdue books
4. **Show Current Borrowed Books**: View currently borrowed books
5. **View Borrowing History**: See complete borrowing history
6. **Reserve a Book** : Reserve a book that is currently borrowed by someone else
7. **Borrow Reserved Book** : Borrow a book that you previously reserved and is now available
8. **View Reserved Books** : See all books you have reserved
9. **View Available Books** : See all books currently available for borrowing
10. **Exit** : Return to main menu

### Faculty Operations

1. **Borrow Book**: Borrow a book using its ISBN (limit: 5 books)
2. **Return Book**: Return a borrowed book
3. **Show Current Borrowed Books**: View currently borrowed books
4. **View Borrowing History**: See complete borrowing history
5. **Reserve a Book** : Reserve a book that is currently borrowed by someone else
6. **Borrow Reserved Book** : Borrow a book that you previously reserved and is now available
7. **View Reserved Books** : See all books you have reserved
8. **View Available Books** : See all books currently available for borrowing
9. **Exit**: Return to main menu

### Librarian Operations

1. **Add Book**: Add a new book to the library
2. **Remove Book**: Remove a book from the library
3. **Add User**: Add a new user (student, faculty, or librarian)
4. **Remove User**: Remove a user
5. **View All Books**: Display information about all books
6. **View All Users**: Display information about all users
7. **View Book Status Details**: Check detailed status of all books
8. **Update Book**: Modify book details
9. **Update User**: Modify user details
10. **View User Borrowing History**: Check borrowing history for any user
11. **View All Reserved Books** : See all books currently reserved by any user
12. **Exit**: Return to main menu

## Rules and Policies

### Borrowing Rules

- Students can borrow up to 3 books
- Faculty can borrow up to 5 books
- Borrowed books must be returned within:
  - 15 days for students (fine and restriction applies after)
  - 60 days for faculty (restriction applies after)

### Reservation Rules

* Users can only reserve books that are currently borrowed by other users
* Users cannot reserve books they have already borrowed at that time
* When a reserved book is returned, its status changes to "Reserved" instead of "Available"
* Only the user who reserved the book can borrow it when it's in "Reserved" status
* Users must still follow borrowing limits when borrowing reserved books
* Students must have no outstanding fines to borrow reserved books

### Fine Calculation

- Students: Rs. 10 per day after 15 days
- Faculty: No fines, but cannot borrow if any book is kept for more than 60 days

## Troubleshooting

### Common Issues and Solutions

- **Missing Data Files**: If data files are deleted, the system will automatically create new ones with default data
- **Invalid Input**: The system validates input to prevent crashes; follow the provided prompts
- **Login Issues**: Ensure you're using the correct user type (student/faculty/librarian) and credentials
- **Reservation Issues** : Check that you're trying to reserve a book that is currently borrowed, not available

## Conclusion

This Library Management System provides a comprehensive solution for managing library operations. With features like user management, book tracking, borrowing history, and fine calculation, it addresses the core needs of a modern library system while maintaining data integrity through persistent storage.

The modular design with distinct classes for different entities allows for easy maintenance and extension of the system as requirements evolve.

Thank you for using the Library Management System! I hope this software helps streamline your library operations and enhances the experience for both librarians and students. Should you have any questions or encounter any issues, please don't hesitate to reach out to me.

Happy reading and managing!!

This program was developed by **Aritra Ambudh Dutta** as part of CS253 Course Programming Assignment offered in Semester 2024-25/II at IIT Kanpur.
