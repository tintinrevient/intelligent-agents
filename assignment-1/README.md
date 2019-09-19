## Assignment 1

1. Given the following classes “person”, “parent”, “happyPerson”, “marriedPerson”, “malePerson” and the relation “hasChild”. Represent the following in DL:

* Father: parent ⊓ malePerson
* Strange people are parents who have only married or happy kids
* Retired people are happy people who have at least one happy married child • Brave parents are parents with exactly two children
* Married men do not have children
* Michael is a father with children named Alice and Bob.
* Charlie is a married man.


2. The following ontology has been defined in DL:

* instructor ≡ person ⊓ ∃teaches.(course ⊔ lab)
* projectCourse ≡ course ⊓ lab
* busyInstructor ≡ instructor ⊓ ∀teaches.projectCourse • john: busyInstructor
* simulation: projectCourse

Apply the tableaux algorithm to answer the following and show your steps:

* Is this ontology consistent? If not, what has to change to make it consistent? • Does John teach simulation?
* Is simuation a lab?


3. Add the following fact to the above ontology: Mary is a person who teaches the programming course. Again apply the tableaux algorithm to answer the following:

* Is Mary an instructor?
* Is programming a project course? • Is Mary a busy instructor?


