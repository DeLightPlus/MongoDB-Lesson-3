# MongoDB-Lesson-3

# Library Management System – MongoDB Shell Commands
### Project Overview
The **Library Management System** allows managing a collection of books, authors, and patrons using MongoDB. This README provides instructions on how to interact with MongoDB shell (Mongosh) to achieve the following objectives:
  - Create a database (LibraryDB).
  - Create collections (Books, Authors, Patrons).
  - Insert multiple documents in each collection using the insertMany() method.
  - Perform CRUD operations on these collections.
  - Use advanced queries to manipulate and retrieve data.
#

  #### Access MongoDB shell
  Open a new command prompt window and run:
  
      mongosh
  
  

  #### **1. Create Database and Collections**
  In the MongoDB shell, you can create the LibraryDB database by using the use command:

    use LibraryDB
  
   ![mongosh-use-LibraryDB](https://github.com/user-attachments/assets/438528ae-5934-4f26-8b14-63d2d855ea4e)
  This command switches to the LibraryDB database, creating it if it doesn’t already exist.
#
  #### **2. Create Collections and Insert Documents**
  **Books Collection**
  
  Use the ***insertMany()*** method to insert multiple documents into the **Books** collection:

    db.Books.insertMany([
      { _id: 1, title: "1984", author_id: 1, genres: ["Dystopian", "Political Fiction"], published_year: 1949, available: true },
      { _id: 2, title: "To Kill a Mockingbird", author_id: 2, genres: ["Southern Gothic", "Bildungsroman"], published_year: 1960, available: true },
      { _id: 3, title: "The Great Gatsby", author_id: 3, genres: ["Tragedy"], published_year: 1925, available: true },
      { _id: 4, title: "Brave New World", author_id: 4, genres: ["Dystopian", "Science Fiction"], published_year: 1932, available: true },
      { _id: 5, title: "The Catcher in the Rye", author_id: 5, genres: ["Realist Novel", "Bildungsroman"], published_year: 1951, available: true },
      { _id: 6, title: "Moby-Dick", author_id: 6, genres: ["Adventure Fiction"], published_year: 1851, available: true },
      { _id: 7, title: "Pride and Prejudice", author_id: 7, genres: ["Romantic Novel"], published_year: 1813, available: true },
      { _id: 8, title: "War and Peace", author_id: 8, genres: ["Historical Novel"], published_year: 1869, available: true },
      { _id: 9, title: "Crime and Punishment", author_id: 9, genres: ["Philosophical Novel"], published_year: 1866, available: true },
      { _id: 10, title: "The Hobbit", author_id: 10, genres: ["Fantasy"], published_year: 1937, available: true }
    ])

  ![insert-books](https://github.com/user-attachments/assets/60397860-04fa-4572-90a8-ba32b1c17c63)


**Authors Collection**

insert multiple documents into the **Authors** collection:

    db.Authors.insertMany([
      { _id: 1, name: "George Orwell", nationality: "British", birth_year: 1903, death_year: 1950 },
      { _id: 2, name: "Harper Lee", nationality: "American", birth_year: 1926, death_year: 2016 },
      { _id: 3, name: "F. Scott Fitzgerald", nationality: "American", birth_year: 1896, death_year: 1940 },
      { _id: 4, name: "Aldous Huxley", nationality: "British", birth_year: 1894, death_year: 1963 },
      { _id: 5, name: "J.D. Salinger", nationality: "American", birth_year: 1919, death_year: 2010 },
      { _id: 6, name: "Herman Melville", nationality: "American", birth_year: 1819, death_year: 1891 },
      { _id: 7, name: "Jane Austen", nationality: "British", birth_year: 1775, death_year: 1817 },
      { _id: 8, name: "Leo Tolstoy", nationality: "Russian", birth_year: 1828, death_year: 1910 },
      { _id: 9, name: "Fyodor Dostoevsky", nationality: "Russian", birth_year: 1821, death_year: 1881 },
      { _id: 10, name: "J.R.R. Tolkien", nationality: "British", birth_year: 1892, death_year: 1973 }
    ])

  ![insert-authors](https://github.com/user-attachments/assets/c0e5908c-51a4-4a62-a35c-eaa04e195c14)


**Patrons Collection**

finally, insert documents into the Patrons collection:

    db.Patrons.insertMany([
      { _id: 1, name: "Alice Johnson", email: "alice@example.com", borrowed_books: [] },
      { _id: 2, name: "Bob Smith", email: "bob@example.com", borrowed_books: [1, 2] },
      { _id: 3, name: "Carol White", email: "carol@example.com", borrowed_books: [] },
      { _id: 4, name: "David Brown", email: "david@example.com", borrowed_books: [3] },
      { _id: 5, name: "Eve Davis", email: "eve@example.com", borrowed_books: [] },
      { _id: 6, name: "Frank Moore", email: "frank@example.com", borrowed_books: [4, 5] },
      { _id: 7, name: "Grace Miller", email: "grace@example.com", borrowed_books: [] },
      { _id: 8, name: "Hank Wilson", email: "hank@example.com", borrowed_books: [6] },
      { _id: 9, name: "Ivy Taylor", email: "ivy@example.com", borrowed_books: [] },
      { _id: 10, name: "Jack Anderson", email: "jack@example.com", borrowed_books: [7, 8] }
    ])

  ![insert-patrons](https://github.com/user-attachments/assets/7d544e0d-5ea0-4644-995b-08a62f606210)
#
