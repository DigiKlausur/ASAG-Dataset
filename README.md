# ASAG-Dataset
Assisted ~Automated~ Short Answer Grading Dataset

The repository contains the dataset collected for short answer grading, we have created a dataset for Assistive short answer grading from an exam of neural network course. The course was taken by graduate students of University of Applied Sciences Bonn-Rhein-Sieg. For each question the answers were collected via jupyter notebooks.  38 students took the examination and each exam had 17 questions. Thus the dataset has a total of 646 question answers.
The answers were graded by a single human judge, using an integer scale from 0(completely incorrect), 1(partially correct) and 2(perfect answer).

## Contents

* The notebook folder contains student notebooks with answers to the questions in a .ipynb format.  
 
* asag_dataset.csv has all the student answers for every question, the reference answer and other features which might be used for further research. The column headings and their descriptions are as follows:

	- question: the original question of the exam
	- student_answer : students answer
	- grades_round: grade for the student's answer
	- student_modified: student's answer after NLP preprocessing like lowercase conversion and lemmatization
	- ref_answer: correct answer for the question
	- qn_modified: question after NLP preprocessing like lowercase conversion and lemmatization
	- ref_modified: correct answer after NLP preprocessing like lowercase conversion and lemmatization
	- student_demoted: student's answer after removing words from the corresponding question
	- ref_demoted: correct answer after removing words from the corresponding question
	- length_ratio: student answer length divided by the reference answer length
	- embed_ref: word2vec embedding of reference answer
	- embed_stud: word2vec embedding of student answer
	- embed_ref_demoted: word2vec embedding of demoted reference answer
	- embed_stud_demoted: word2vec embedding of demoted student answer
	- aligned: word alignment pairs between student answer and reference answer
	- aligned_demoted: word alignment pairs between the demoted versions of student and reference answer
	- cos_similarity: cosine similarity between the embeddings of student and reference answer
	- cos_similarity_demo: cosine similarity between the embeddings of demoted versions of student and reference answer
	- aligned_score: word alignment score between student answer and reference answer
	- aligned_score_demo: word alignment score between the demoted versions of student and reference answer
	- question_id: question number

Features such as length ratio, cos_similarity, cos_similarity_demo, aligned_score, and aligned_score_demo were based on the works of [Sultan et al., 2016](https://www.semanticscholar.org/paper/Fast-and-Easy-Short-Answer-Grading-with-High-Sultan-Salazar/17a474f02d9a3793d13dfe2984151d694863fbb4)

* grades.csv file tabulates the actual scores achieved by every student for every question.