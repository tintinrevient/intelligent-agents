## Project Report

The concepts and the relations in-between are shown in the below diagram:

* Each concept displays as a table
* The concept's data properties display as rows in the table
* The concept's object properties display as arrows between tables

![class-diagram](../diagram/class_diagram.png)


Let's go through their DL descriptions in detail:
* Each course is taught by at least one lecturer:
* The course is taught on exactly two different days:
* Each lecturer teaches at most one course every period:
* Each course is on a set of topics:
* Each course uses exactly one research methodology:
* A course might be a prerequisite for a course:
* A course is considered similar to another course if there is an overlap on topics and the same research methodology is used:
* Topics are organized in a hierarchy, two topics could be disjoint or have overlaps:
* A student might prefer (not) to take a course by a certain lecturer, or on a certain day, or on a certain topic:
* At any given period, a student can take at least two and at most three courses:
* A student cannot register for a course more than once:
* A student can take a course only if she has taken the prerequisite:
*  When a student has an option between two courses that are equally preferable, the student would like to take a course that her friend takes:
  

