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
  ### **3. CRUD Operations**
  * #### **Read Operations**
    
    - **Find All Books**

          db.Books.find()

      ![find-all-books](https://github.com/user-attachments/assets/79a5e1c8-e621-4031-93fd-a5f7a3f75bfb)

    - **Find a Specific Book By Title**

          db.Books.find({title:"To Kill a Mockingbird"})

      ![find-book-by-title](https://github.com/user-attachments/assets/09f107fa-018d-431f-ba20-176480f71a29)

    - **Find All Books by a Specific Author (using author_id)**

          db.Books.find({ author_id: 5 })

      ![find-book-by-id](https://github.com/user-attachments/assets/5d965454-dc01-4a90-983e-35c754e388bb)

    - **Find All Available Books**

          db.Books.find({ available: true })

      ![find-all-available-books](https://github.com/user-attachments/assets/37c02f95-1f6c-430f-8021-11080a0d70fc)

    
  * #### **Update Operations**
    - **Update Book Availability**
    - 
      To mark the book with ***_id: 3*** (The Great Gatsby) as borrowed:

          db.Books.updateOne({ _id: 3 }, { $set: { available: false } })

      ![update-book-by-id](https://github.com/user-attachments/assets/26a2db03-3ed0-4467-8da3-11ebc9f82fa0)

    - **Add a Genre to a Book**
      
      To add a new genre to the book with ***_id: 8***:

          db.Books.updateOne({ _id: 8 }, { $addToSet: { genres: "True Story" } })

      ![update_add-book-new-genre-by-id](https://github.com/user-attachments/assets/6dd7a99d-f4ca-43d8-98d2-739bd577504c)

    - **Add a Borrowed Book to a Patron’s Record**
   
      To add the book with ***_id: 5*** (The Catcher in the Rye) to Patron 5's borrowed books:

          db.Patrons.updateOne({ _id: 5 }, { $push: { borrowed_books: 5 } })

      ![add-borrowed-book-to-patrons](https://github.com/user-attachments/assets/6babf0ef-5d0c-43d3-9704-aa9359e71a79)

  * #### **Delete Operations**
    - **Delete a Book by Title**
      
      To delete a book titled "Brave New World":
          
          db.Books.deleteOne({ title: "Brave New World" })

      ![delete-book-by-title](https://github.com/user-attachments/assets/111875ad-3be0-406b-bb52-15d39d9dff7e)

    - **Delete an Author**
      
      To delete the author with ***_id: 3***

          db.Authors.deleteOne({ _id: 3 })

      ![delete-author-by-id](https://github.com/user-attachments/assets/4c357872-03f8-4cf4-ab18-6541d0c42e14)

#
  ### **4. Advanced Queries with Operators**
  * **Find Books Published After 1950**
    
        db.Books.find({ published_year: { $gt: 1950 } })

    ![find-all-books-published-1950](https://github.com/user-attachments/assets/adcf81a2-a66a-4460-8b1e-a5ee4a115350)

  * **Find All American Authors**

        db.Authors.find({ nationality: "American" })

    ![find-all-American-Authors](https://github.com/user-attachments/assets/8046f9f6-9176-4df9-ad3c-093b006822dc)
  
  * **Set All Books to Available**

        db.Books.updateMany({}, { $set: { available: true } })

    ![find-all-available-books](https://github.com/user-attachments/assets/5d9c3d82-b277-476e-a9d0-b88ee0e432da)
  
  * **Find All Books That Are Available and Published After 1950**

        db.Books.find({ available: true, published_year: { $gt: 1950 } })

    ![find-all-available-books-published-after-1950](https://github.com/user-attachments/assets/be3bce23-c3ae-4249-abdb-b51bc658744a)
  
  * **Find Authors Whose Names Contain "George"**

        db.Authors.find({ name: { $regex: "George", $options: "i" } })

    ![find-authors-whose-name-contains-'Goerge'](https://github.com/user-attachments/assets/f278838f-d8cd-4ddd-8ee7-765451d07a75)

  * **Increment the Published Year of Books Published in 1869 by 1**

        db.Books.updateMany({ published_year: 1869 }, { $inc: { published_year: 1 } })

    ![incr-published-year-by-1](https://github.com/user-attachments/assets/14ac5708-0ee7-4ef2-9b8f-c0c76cad76e2)

#
  ### Conclusion

  In this README, you learned how to:  
  1. Install MongoDB and access the MongoDB shell.
  2. Create a LibraryDB database and collections (Books, Authors, Patrons).
  3. Insert multiple documents into collections using insertMany.
  4. Perform CRUD operations such as reading, updating, and deleting documents.
  5. Utilize advanced queries with operators like $gt, $eq, $inc, $set, and $regex.

For more details, refer to the MongoDB documentation.
