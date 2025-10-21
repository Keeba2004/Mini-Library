# Mini Library Management System

A simple yet comprehensive library management system built with Python, demonstrating object-oriented programming principles and data structure usage.

##  Overview

This project implements a complete library management system that allows users to:
- Manage books and library members
- Handle book borrowing and returning operations
- Search and filter books by various criteria
- Maintain data integrity and enforce business rules

##  Features

### Book Management
- **Add Books**: Add new books with ISBN, title, author, genre, and copy count
- **Update Books**: Modify book information (title, author, genre, total copies)
- **Delete Books**: Remove books from the system (with safety checks)
- **Search Books**: Find books by title or author
- **Display Books**: View all books with availability status

### Member Management
- **Add Members**: Register new library members with unique IDs
- **Update Members**: Modify member information (name, email)
- **Delete Members**: Remove members from the system (with safety checks)
- **Display Members**: View all members with their borrowed books

### Borrowing System
- **Borrow Books**: Members can borrow up to 3 books at a time
- **Return Books**: Return borrowed books to make them available again
- **Availability Tracking**: Real-time tracking of book availability
- **Borrowing Limits**: Enforced maximum borrowing limit per member

### Data Validation
- **ISBN Uniqueness**: Prevents duplicate book entries
- **Member ID Uniqueness**: Ensures unique member identification
- **Email Validation**: Basic email format validation
- **Genre Validation**: Restricts books to predefined genres
- **Business Rules**: Prevents deletion of books/members with active transactions

##  Architecture

### Data Structures
- **Books**: Dictionary with ISBN as key, book details as value
- **Members**: List of dictionaries containing member information
- **Genres**: Tuple of predefined valid genres

### Design Principles
- **Separation of Concerns**: Clear separation between data management and business logic
- **Data Integrity**: Comprehensive validation and error handling
- **User Experience**: Informative error messages and status updates
- **Extensibility**: Modular design for easy feature additions

##  Quick Start

### Prerequisites
- Python 3.6 or higher
- No external dependencies required

### Installation
1. Clone or download the project
2. Navigate to the project directory
3. Run the demo to see the system in action:

```bash
python demo.py
```

### Running Tests
```bash
python tests.py
```

##  Usage Examples

### Basic Operations

```python
from operations import *

# Add a book
add_book("978-1234567890", "The Great Gatsby", "F. Scott Fitzgerald", "Fiction", 3)

# Add a member
add_member("D001", "Jane Conteh", "Jane@email.com")

# Search for books
results = search_books("Gatsby", "title")

# Borrow a book
borrow_book("D001", "978-1234567890")

# Return a book
return_book("D001", "978-1234567890")

# Display all books and members
display_books()
display_members()
```

### Advanced Operations

```python
# Update book information
update_book("978-1234567890", title="The Great Gatsby (Special Edition)", total_copies=5)

# Update member information
update_member("D001", name="Jane Conteh", email="Jane@email.com")

# Search by author
results = search_books("Fitzgerald", "author")
```

##  Valid Genres

The system supports the following book genres:
- Fiction
- Non-Fiction
- Sci-Fi
- Mystery
- Romance
- Biography
- History
- Science

##  API Reference

### Book Operations

| Function | Description | Parameters | Returns |
|----------|-------------|------------|---------|
| `add_book()` | Add a new book | isbn, title, author, genre, total_copies | bool |
| `update_book()` | Update book details | isbn, **kwargs | bool |
| `delete_book()` | Delete a book | isbn | bool |
| `search_books()` | Search books | search_term, search_by | list |
| `display_books()` | Show all books | None | None |

### Member Operations

| Function | Description | Parameters | Returns |
|----------|-------------|------------|---------|
| `add_member()` | Add a new member | member_id, name, email | bool |
| `update_member()` | Update member details | member_id, **kwargs | bool |
| `delete_member()` | Delete a member | member_id | bool |
| `display_members()` | Show all members | None | None |

### Borrowing Operations

| Function | Description | Parameters | Returns |
|----------|-------------|------------|---------|
| `borrow_book()` | Borrow a book | member_id, isbn | bool |
| `return_book()` | Return a book | member_id, isbn | bool |

### Utility Functions

| Function | Description | Parameters | Returns |
|----------|-------------|------------|---------|
| `get_genres()` | Get valid genres | None | tuple |

##  Testing

The project includes comprehensive unit tests covering:
- Book addition and validation
- Member management
- Borrowing and returning operations
- Error handling and edge cases
- Data integrity checks

Run tests with:
```bash
python tests.py
```

##  Project Structure

```
mini_library/
├── operations.py      # Core library management functions
├── demo.py           # Demonstration script
├── tests.py          # Unit tests
├── README.md         # This documentation
└── __pycache__/      # Python cache directory
```

