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


	|--------------Course ----------------|
	|                                     |
      Students----------------------------Teachers

