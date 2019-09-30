## Project Report


### Concepts and Relations
![class-diagram](../diagram/class-diagram.png)

### Knowledge Base TBox in DL

Each course is taught by at least one lecturer
```
Course ⊑ ∃IsTaughtBy.Lecturer
```

The course is taught on exactly two different days
```
Course ⊑ =2isTaughtOn.Day
```

Each lecturer teaches at most one course every period
```
Lecturer ⊑ ≤1teachesInPeriod1.Course ⊔ ≤1teachesInPeriod2.Course ⊔ ≤1teachesInPeriod3.Course ⊔ ≤1teachesInPeriod4.Course
```

Each course is on a set of topics
```
Course ⊑ ∃covers.Topic
```

Each course uses exactly one research methodology
```
Course ⊑ =1usesMethodology.ResearchMethodology
```

A course might be a prerequisite for a course
```
∀prerequisiteFor.Course ⊑ Course
```

A course is considered similar to another course if there is an overlap on topics and the same research methodology is used
```

```

Topics are organized in a hierarchy
```

```

two topics could be disjoint or have overlaps
```
Topic ⊑ Agent ⊔ ArtificialIntelligence ⊔ ... ⊔ Graphics
Agent ⊑ ¬Graphics
ArtificialIntelligence ⊑ ¬Graphics
IntelligentAgent ⊑ Agents ⊓ MachineLearning
```

A student might prefer (not) to take a course by a certain lecturer, or on a certain day, or on a certain topic
```
```

At any given period, a student can take at least two and at most three courses
```
Student ⊑ (≥2takesInPeriod1.Course ∩ ≤3takesInPeriod1.Course) ⊓ (Student ⊑ ≥2takesInPeriod2.Course ∩ ≤3takesInPeriod2.Course) ⊓ (Student ⊑ ≥2takesInPeriod3.Course ∩ ≤3takesInPeriod3.Course) ⊓ (Student ⊑ ≥2takesInPeriod4.Course ∩ ≤3takesInPeriod4.Course)
```

A student cannot register for a course more than once
```
```

A student can take a course only if she has taken the prerequisite
```
```

When a student has an option between two courses that are equally preferable, the student would like to take a course that her friend takes
```
```
 
The prerequisite DL
```
Person ⊑ Lecturer ⊔ Student
```
