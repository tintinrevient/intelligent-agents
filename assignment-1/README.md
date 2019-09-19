## Assignment 1

### 1. Given the following classes “person”, “parent”, “happyPerson”, “marriedPerson”, “malePerson” and the relation “hasChild”. Represent the following in DL:

* Father ≡ parent ⊓ malePerson

* Strange people are parents who have only married or happy kids ⊑ parent ⊓ ∀hasChild.(marriedPerson ⊔ happyPerson)

* Retired people are happy people who have at least one happy married child ⊑ happyPerson ⊓ ∃hasChild.(marriedPerson ⊓ happyPerson)

* Brave parents are parents with exactly two children ⊑ parent ⊓ ≤2 hasChild.person ⊓ ≥2 hasChild.person

* Married men do not have children ⊑ marriedPerson ⊓ malePerson ⊓ ∃hasChild.person ⊑ ⊥

* Michael is a father with children named Alice and Bob ≡ Michael: (parent ⊓ malePerson), hasChild(Michael, {Alice, Bob})

* Charlie is a married man ≡ Charlie: (marriedPerson ⊓ malePerson)


### 2. The following ontology has been defined in DL:

* instructor ≡ person ⊓ ∃teaches.(course ⊔ lab)
* projectCourse ≡ course ⊓ lab
* busyInstructor ≡ instructor ⊓ ∀teaches.projectCourse
* john: busyInstructor
* simulation: projectCourse

 ### Apply the tableaux algorithm to answer the following and show your steps:

* #### Is this ontology consistent? If not, what has to change to make it consistent?

	It is consistent.

* #### Does John teach simulation?

	I cannot say it from the defined DL, because:

	* busyInstructor teaches only projectCourse -> john is busyInstructor -> john teaches projectCourse
	* simulation is just one of projectCourse -> john might teach other projectCourse, but not simulation

* #### Is simuation a lab?

	simulation is a lab, because:

	* simulation belongs to projectCourse
	* projectCourse is the intersection of course and lab -> projectCourse is a course, and projectCourse is a lab
	* simulation is a course, and simulation is a lab


### 3. Add the following fact to the above ontology: Mary is a person who teaches the programming course. Again apply the tableaux algorithm to answer the following:

* #### Is Mary an instructor?

	The prerequisite is as below:

	* A = {Mary: person, teaches(Mary, programming course)}
	* Q = {Mary: instructor}?

	The inference is as below:

	* Mary: person
	* teaches(Mary, programming course)
	* Mary: ¬instructor
	* programming course: course
	* teaches(Mary, course)
	* Mary: instructor

	There is a CLASH, so Mary is an instructor.

* #### Is programming a project course?

	The prerequisite is as below:

	* A = {Mary: person, teaches(Mary, programming course)}
	* Q = {programming course: projectCourse}?

	The inference is as below:

	* Mary: person
	* teaches(Mary, programming course)
	* programming course: ¬projectCourse
	* programming course: course
	* teaches(Mary, course)
	* Mary: instructor

	There is no CLASH, and it cannot be deduced that Mary is busyInstructor or programming course is a lab, so I cannot say programming course is a projectCourse.

* #### Is Mary a busy instructor?

	The prerequisite is as below:

	* A = {Mary: person, teaches(Mary, programming course)}
	* Q = {Mary: busyInstructor}?

	The inference is as below:

	* Mary: person
	* teaches(Mary, programming course)
	* Mary: ¬busyInstructor
	* programming course: course
	* teaches(Mary, course)
	* Mary: instructor

	There is no CLASH, and it cannot be deduced that Mary is busyInstructor or programming course is a lab, so I cannot say programming course is a projectCourse.


