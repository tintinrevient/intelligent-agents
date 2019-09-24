## Project Report

The concepts and the relations in-between are shown in the below diagram:

* Each concept displays as a table.
* The concept's data properties display as rows in the table.
* The concept's object properties display as arrows between tables.

![class-diagram](../diagram/class-diagram.png)


Let's go through their DL descriptions in detail:
* Each course is taught by at least one lecturer: Course ⊓ ∃taught_by.Lecturer

* The course is taught on exactly two different days: Course ⊓ ≤2 taught_on.Timeslot ⊓ ≥2 taught_on.Timeslot (Timeslot must be on two different days?)

* Each lecturer teaches at most one course every period: ?

* Each course is on a set of topics: Course ⊓ ∃covers.Topic

* Each course uses exactly one research methodology: Course ⊓ ≤1 uses.Research_Methodologies ⊓ ≥1 uses.Research_Methodologies

* A course might be a prerequisite for a course: Course ⊔ ∃is_prerequisite_of.Course

* A course is considered similar to another course if there is an overlap on topics and the same research methodology is used: a: Course, b: Course, c: Research_Methodologies, d: Topic, (a, c): uses, (b, c): uses, (a, d): covers, (b, d): covers -> (a, b): is_similar_to, (b, a): is_similar_to (symmetric)

* Topics are organized in a hierarchy, two topics could be disjoint or have overlaps: Topic ⊔ ∃have.Topic

* A course might be a prerequisite for a course: Course ⊔ ∃is_prerequisite_of.Course

* A student might prefer (not) to take a course by a certain lecturer, or on a certain day, or on a certain topic: a: Lecturer, b: Student, (b, a): favourite_lecturers, c: Course, (c, a): taught_by, (a, c): enrolled_in

* At any given period, a student can take at least two and at most three courses: Student ⊓ ≥2 enrolled_in.Course ⊓ ≤3 enrolled_in.Course 

* A student cannot register for a course more than once: ?

* A student can take a course only if she has taken the prerequisite: 

*  When a student has an option between two courses that are equally preferable, the student would like to take a course that her friend takes:
  

