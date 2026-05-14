# Knowledge-Engineering-Ontology-Project
This project was developed as part of the Knowledge Engineering and Ontologies course to model the semantic relationships within a university ecosystem.
# Project-Team
Ayça Selda Keskin / 220316054   
Efe Şamil Sarıgül / 220316050

# Purpose-and-Scope
The purpose of this ontology is to formalize semantic relationships such as student enrollments, faculty teaching assignments, and course prerequisite structures to enable automated academic reasoning and querying.
The scope is limited to core academic entities: 
*Persons: Students and Teachers.  
*Courses: Academic subjects and their prerequisite hierarchies. 
*Departments: Academic affiliations. 
*Academic Terms: Semesters or terms. 

# Technical-Specifications
*Ontology Language: OWL 2 (Web Ontology Language) / RDF.
*Development Tool: Protégé.  
*Reasoning Support: Designed for reasoners like HermiT or Pellet.

# Ontology-Structure
Core Classes
*person: The base class for individuals.  
*student: Individuals enrolled in courses. 
*professors: Individuals responsible for teaching. 
*course: Academic subjects. 
*department: University departments.  
*academicTerm: Specific periods of study.

# Object-Properties
*belongsTo: Connects a person to a department.  
*hasPrerequisite: Defines prerequisite relationships between courses (Transitive property).  
*isEnrolledIn: Connects a student to a course.  
*teaches: Connects a professor to a course.

# Competency-Questions (CQs)
The system is designed to answer the following questions: 
1- What are the prerequisite courses for a specific Course?  
2- Which Department does a specific Student belong to?   
3- Is a specific Student enrolled in a specific Course? 
4- Which Courses are taught by a specific Teacher?

# Example-Instances (Individuals)
The ontology includes several initial instances for testing: 
*Students: Ayca Keskin, Efe Sarıgül, Sinem, and Özgür. 
*Professors: Can, Gamze, and Nihat.  
*Courses: Automata Theory, Physics, Knowledge Engineering and Ontologies, Operating Systems, and Mathematics. 

# Usage
You can open the university-knowledge-graph.rdf file using Protégé to explore the classes, properties, and individuals, or to run SPARQL queries for data analysis.

# Ontology Requirements Specification Document (v2)

### Changelog: What has changed compared to Version 1 (v1)?

* *Expanded Class Hierarchy:* The Course class was branched into MandatoryCourse and ElectiveCourse. The Person class was expanded to include AcademicStaff, which is further divided into Professor and ResearchAssistant. The SubField class was introduced to model academic sub-departments.
* *New Object Properties:* Added worksIn (linking staff to sub-fields), hasSubField (linking departments to sub-fields), hasCourse, offeredIn, and supervises.
* *New Data Properties:* Added courseCode, courseName, semester, fullName, title, email, avesisURL, studentID, GPA, departmentName, and subFieldName to hold real-world data.
* *Disjointness Constraints:* Implemented strict disjoint rules between Professor, ResearchAssistant, and Student; as well as between MandatoryCourse and ElectiveCourse.
* *Data Source Shift:* Transitioned from dummy data to real-world academic data extracted from the Manisa Celal Bayar University (MCBU) Bologna Information System and AVESİS portal, utilizing LLMs for unstructured text parsing.

---

### ORSD Table

| Ref | Section | Content |
| :--- | :--- | :--- |
| *1* | *Purpose* | To formalize the semantic relationships within the Manisa Celal Bayar University (MCBU) Faculty of Engineering ecosystem, specifically modeling student enrollments, faculty-subfield assignments, and complex mandatory/elective course prerequisite structures to enable automated academic reasoning. |
| *2* | *Scope* | The ontology covers the MCBU Engineering Faculty (CSE, MEE, and IE departments), their academic sub-fields, academic staff (Professors and Research Assistants), students, academic terms, and course hierarchies. It excludes administrative staff, campus facilities, and financial systems. |
| *3* | *Implementation Language* | OWL 2 (Web Ontology Language) / RDF, developed using Protégé. METHONTOLOGY framework applied. |
| *4* | *Intended End-Users* | University Students, Academic Advisors, and Department Heads. |
| *5* | *Intended Uses* | Automated prerequisite validation, curriculum workload analysis, course recommendation systems, and serving as a structured knowledge base for future machine-learning-based risk analysis models. |
| *6* | *Ontology Requirements* | |
| | *a. Non-Functional Requirements* | - Must be developed using W3C Semantic Web standards (OWL).<br>- Must support automated reasoning (e.g., using HermiT) without logical conflicts.<br>- Must enforce disjointness among distinct academic roles to ensure data integrity.<br>- Must scale to accommodate new faculties. |
| | *b. Functional Requirements (CQs)* | *CQ1:* What are the mandatory courses offered in the 5th semester of the CSE department?<br>*CQ2:* What are the prerequisites for the "Automata Theory" course?<br>*CQ3:* In which sub-field does a specific Professor work, and which courses do they teach?<br>*CQ4:* Who are the Research Assistants working in the Operations Research sub-field?<br>*CQ5:* Which courses is a specific Student currently enrolled in? |
| *7* | *Pre-Glossary of Terms* | |
| | *a. Terms from CQs* | Mandatory Course, Semester, Department, Prerequisite, Sub-field, Professor, Research Assistant, Enrolled, Teach. |
| | *b. Terms from Answers* | hasPrerequisite, belongsTo, worksIn, hasSubField, teaches, isEnrolledIn, hasCourse, offeredIn (Object Properties). |
| | *c. Objects* | Student, Professor, ResearchAssistant, MandatoryCourse, ElectiveCourse, Department, SubField, AcademicTerm (Core Classes). |








