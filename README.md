# assignment_data_modeling
Mmmmm.... dataaaaa....

*Include your ERM modeling "pseudocode" in the space below*

Online Learning Platform:

Goals/Needs:

Providing courses for people.
Checking taken classes don't overlap.
Making sure courses prepare student for the subsequent course.
Courses keep on time schedule.

Entities:

Students, courses, teachers, semester

Attributes:

Students:

First Name = string
Last Name = string
Email = string
ID = integer

Courses:

Name = string
Description = string
Content = string
Prerequisites = array of ids
Time = time
Semester = string
ID = integer

Teachers:

First Name = string
Last Name = string
Email = string
ID = integer

Join Table Student to Courses:
Student ID = integer
Course ID = integer
If-Completed = bool

Join Table Teachers to Courses:
Teacher ID = integer
Course ID = integer
If-Currently = bool

Relationship

|--------------Course ----------------|
|                                     |
Students----------------------------Teachers


| Tables                   | Are           |
| ------------------------ |:-------------:|
| students                 | right-aligned |
| teachers                 | centered      |   
| courses                  | are neat      |    
| student to courses       | are neat      |    
| teacher to courses       | are neat      |    

Table: students
| StudentID                | First Name    | Last Name  | Email                              |
| ------------------------ |:-------------:| ----------:| ----------------------------------:|
| 1                        | steven        | li         | steven4354@gmail.com               |
| 2                        | gene          | tinderholm | tinderholmgene@gmail.com           |


Table: teachers
| TeacherID                | First Name    | Last Name  | Email                              |
| ------------------------ |:-------------:| ----------:| ----------------------------------:|
| 1                        | vlad          | zelinschi  |                                    |
| 2                        | chris         | scavello   |                                    |

Table: courses
| CourseID                 | Title         | Description             | Prerequisites                    | Content                        | Time      | Semester     |
| ------------------------ |:-------------:| -----------------------:| --------------------------------:| ------------------------------:| ---------:|-------------:|
| 1                        | Javascript    | "full stack engineering"| [1,2,3]                          | Coffee, Calligraphy            | 7AM       | Summer 2017  |

Table: students to courses
| CourseID                 | StudentID     | If-Completed  |
| ------------------------ |:-------------:| -------------:|
| 1                        | 1             | False         |
| 1                        | 2             | False         |

Table: teachers to courses  
| CourseID                 | TeacherID     | If-Currently  |
| ------------------------ |:-------------:| -------------:|
| 1                        | 1             | True          |
| 1                        | 2             | True          |


------------------------------------------------------------


Profile To User Database:

Goals/Needs:

Profile Page for each User

Entities:

User

Attributes:

User:

First Name = string
Last Name = string
ID = integer
Profile = string for path
City = string
Country = string
Next Subdivision (after country) = string
Age = string
Gender = string


Relationship

	|--------------User----------------|

Tables

| Tables                   | Are           |
| ------------------------ |:-------------:|
| Users                    | right-aligned |

Table: Users
| UserID                   | First Name    | Last Name     | Profile                          | City                           | Country   | Subdivision | Age          | Gender    |
| ------------------------ |:-------------:| -------------:| --------------------------------:| ------------------------------:| ---------:|------------:| ------------:| ---------:|
| 1                        | Gene          | Tinderholm    | 'facebook.com/gene'              | Savage                         | US        | MN          | 27           | Male      |
| 2                        | Steven        | Li            | 'facebook.com/steven'            | Berkeley                       | US        | CA          | 19           | Male      |


--------------------------------------------------

Message Board Database:

Goals/Needs:

Every user to message board.
Users can post links.

Entities:

User
Message  

Replies

Join Message to Users

Join Replies to Message



Attributes:

User:

Userame = string
ID = integer
Profile = string for path

Message:

ID = integer
UserID = integer
First Message in Thread: integer
Content = string

Board:

Board ID: integer
Board Name: string

Thread:

Thread ID: integer
Thread Name: string
Board ID: integer
Messages: Array of MessageIDs

Relationship

User----------------Message-------First Message (Thread ID)------------Board
                      |
                      |
                   Next Message

Tables

| Tables                   | Are           |
| ------------------------ |:-------------:|
| Users                    | right-aligned |

Table: Users
| UserID                   | Username    | Profile                          |
| ------------------------ |:-----------:| --------------------------------:|
| 1                        | jimothy97   | 'messagenews.com/jomothy97'      |
| 2                        | bucket_head | 'messagenews.com/bucket_head'    |

Table: Message
| MessageID                | UserID      | ThreadID    |   Body                                             |
| ------------------------ |:-----------:| -----------:| --------------------------------------------------:|
| 1                        | 2           | 1           | 'user post'                                        |
| 2                        | 5           | 5           | 'disagreement! Internet argument! Rabble rabble!'  |

Table: Board

| Board ID |  Board Name  |
| --------:|:------------:|
| 1        | 'gardening'  |
| 2        | 'cats'       |


Table: Thread
| ThreadID                | Thread Name      | BoardID    |   Messages                                             |
| ----------------------- |:----------------:| ----------:| ------------------------------------------------------:|
| 1                       | 'emacs?'         | 2          | [1, 5, 9, 42, 199]                                     |
| 2                       | 'cat picturs'    | 2          | [3, 8, 41, 654, 65131263541351354]                     |
