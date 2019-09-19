## Assignment 1

### 1. Given the following classes “person”, “parent”, “happyPerson”, “marriedPerson”, “malePerson” and the relation “hasChild”. Represent the following in DL:

* Father ≡ parent ⊓ malePerson

* Strange people are parents who have only married or happy kids ⊑ parent ⊓ ∀hasChild.(marriedPerson ⊔ happyPerson)

* Retired people are happy people who have at least one happy married child ⊑ happyPerson ⊓ ∃hasChild.(marriedPerson ⊓ happyPerson)

* Brave parents are parents with exactly two children ⊑ parent ⊓ ≤2 hasChild.person ⊓ ≥2 hasChild.person

* Married men do not have children ⊑ marriedPerson ⊓ malePerson ⊓ ∃hasChild.person ⊑ ⊥

* Michael is a father with children named Alice and Bob -> Michael: (parent ⊓ malePerson), (Michael, Alice): hasChild, (Michael, Bob): hasChild

* Charlie is a married man -> Charlie: (marriedPerson ⊓ malePerson)


### 2. The following ontology has been defined in DL:

* instructor ≡ person ⊓ ∃teaches.(course ⊔ lab)
* projectCourse ≡ course ⊓ lab
* busyInstructor ≡ instructor ⊓ ∀teaches.projectCourse
* john: busyInstructor
* simulation: projectCourse

### Apply the tableaux algorithm to answer the following and show your steps:

* #### Is this ontology consistent? If not, what has to change to make it consistent?

	**CLUE: expand all inferences**

	It is consistent.
	
	The inference is as below:
		
	* john: busyInstructor -> john: instructor -> john: ∀teaches.projectCourse
	* john: instructor -> john: person -> john: ∃teaches.(course ⊔ lab)
	* john: ∀teaches.projectCourse -> (john, a): teaches, a: projectCourse -> (john, a): teaches, a: course ⊓ lab
	* john: ∃teaches.(course ⊔ lab) ->
		* (john, a): teaches, a: course (NO CLASH)
		* (john, a): teaches, a: lab (NO CLASH)
	* simulation: projectCourse -> simulation: course ⊓ lab
	

* #### Does John teach simulation?

	**CLUE: negation of the query -> (john, simulation): ¬teaches -> find CLASH -> "john teaches simulation" is TRUE**

	I cannot say it from the defined DL, because:
	
	* busyInstructor teaches only projectCourse -> john is busyInstructor -> john teaches projectCourse
	* simulation is just one of projectCourse -> john might teach other projectCourse, but not simulation
	
	The answer is as below:
	
	* (john, simulation): ¬teaches
	* john: busyInstructor
	* john: (instructor ⊓ ∀teaches.projectCourse)
	* john: instructure
	* john: ∀teaches.projectCourse
	* john: ∀teaches.(course ⊓ lab)
	* (john, course): teaches
	* (john, lab): teaches
	* simulation: projectCourse
	* simulation: (course ⊓ lab)
	* simulation: lab, simulation: course
	* (john, a): teaches, a: lab, a: course (NO CLASH)

* #### Is simuation a lab?

	simulation is a lab, because:

	* simulation belongs to projectCourse
	* projectCourse is the intersection of course and lab -> projectCourse is a course, and projectCourse is a lab
	* simulation is a course, and simulation is a lab
	
	The answer is as below:
	
	* simulation: ¬lab
	* simulation: projectCourse
	* simulation: (course ⊓ lab)
	* simulation: course
	* simulation: lab (CLASH)


### 3. Add the following fact to the above ontology: Mary is a person who teaches the programming course. Again apply the tableaux algorithm to answer the following:

* #### Is Mary an instructor?

	The prerequisite is as below:

	* A = {Mary: person, (Mary, programming): teaches, programming: course}
	* Q = {Mary: instructor}?

	The inference is as below:

	* Mary: person
	* (Mary, programming): teaches
	* Mary: ¬instructor
	* programming: course
	* (Mary, course): teaches
	* Mary: instructor

	There is a CLASH, so Mary is an instructor.
	
	The answer is as below:
	
	* Mary: ¬instructor
	* Mary: ¬(person ⊓ ∃teaches.(course ⊔ lab))
	* Mary: ¬person ⊔ ∀teaches.(¬course ⊓ ¬labe)
		* Mary: ¬person -> Mary: person (CLASH)
		* Mary: ∀teaches.(¬course ⊓ ¬lab) -> (Mary, a): teaches, a: ¬course ⊓ ¬lab (CLASH)
	

* #### Is programming a project course?

	The prerequisite is as below:

	* A = {Mary: person, (Mary, programming): teaches}
	* Q = {programming: projectCourse}?

	The inference is as below:

	* Mary: person
	* (Mary, programming): teaches
	* programming: ¬projectCourse
	* programming: course
	* (Mary, course): teaches
	* Mary: instructor

	There is no CLASH, and it cannot be deduced that Mary is busyInstructor or programming course is a lab, so I cannot say programming course is a projectCourse.
	
	The answer is as below:
	
	* programming: ¬projectCourse
	* programming: ¬(course ⊓ lab)
	* programming: ¬course ⊔ ¬lab
		* programming: ¬course -> programming: course (CLASH)
		* programming: ¬lab (NO CLASH)
	

* #### Is Mary a busy instructor?

	The prerequisite is as below:

	* A = {Mary: person, teaches(Mary, programming course)}
	* Q = {Mary: busyInstructor}?

	The inference is as below:

	* Mary: person
	* (Mary, programming): teaches
	* Mary: ¬busyInstructor
	* programming: course
	* (Mary, course): teaches
	* Mary: instructor

	There is no CLASH, and it cannot be deduced that Mary is busyInstructor or programming course is a lab, so I cannot say programming course is a projectCourse.
	
	The answer is as below:
	
	* Mary: ¬busyInstructor
	* Mary: ¬(instructor ⊓ ∀teaches.projectCourse)
	* Mary: ¬instructor ⊔ ∃teaches.¬projectCourse
		* Mary: ¬instructor -> Mary: instructor (CLASH)
		* Mary: ∃teaches.¬projectCourse -> Mary: ∃teaches.¬(course ⊓ lab) -> Mary: ∃teaches.(¬course ⊔ ¬lab)
			* Mary: ∃teaches.¬course (NO CLASH)
			* Mary: ∃teaches.¬lab (NO CLASH)


### Reference

* **Transformation rules**
* https://en.wikipedia.org/wiki/Negation_normal_form
* https://en.wikipedia.org/wiki/Description_logic
