---
title: "'Resume Match' Software (2024)"
excerpt: "Developed a student-centered desktop application that analyzes your resume against a provided job application"
collection: portfolio
toc: true
toc_sticky: true
toc_label: "Content"

---
------

{% include toc.html html=content %}

During the Spring 2024 Semester, I developed a Python program called "Resume Match" that compares student resumes to a job description, suggesting relevant keywords to include.

This software was inspired by my experience applying for summer internships, where I spent hours sifting through applications for keywords to enhance my resume. By highlighting relevant keywords and skills, the tool helps individuals better-align their resumes with job descriptions, demonstrating to employers that they are a good fit for the position.

# Project Details

## Libraries Used

The script uses several libraries, including [tkinter](https://docs.python.org/3/library/tkinter.html) for creating the graphical user interface (GUI), [nltk](https://www.nltk.org/) for natural language processing tasks such as tokenization, part-of-speech tagging, and lemmatization, and fitz from the [PyMuPDF](https://github.com/pymupdf/PyMuPDF) library for extracting text from PDF resumes.

## Overview of Algorithm

- **Upload Resume:** Users can upload their resume in PDF or DOCX format. The script reads the file and extracts the text content.
- **Extract Verbs and Nouns:** The script analyzes the text of the resume to extract verbs and nouns using NLTK's part-of-speech tagging and lemmatization.
- **Upload Job Application:** Users can paste a job application description into a text box. The script then extracts the verbs and nouns from the job application text.
- **Compare Texts:** The script compares the verbs and nouns extracted from the resume with those from the job application, identifying words missing from the resume. It also generates a list of the 10 most frequently used words in the job application.
- **Display Recommendations:** The script presents a list of the most common words found in the job applications, along with recommended additions to the user's resume for improved alignment with the job application.

# Example Results

<br>

[ ![Example: Data Analyst - Texas Democratic Party](https://chamberlainlondon.github.io/images/ResumeMatch1.png) ](https://chamberlainlondon.github.io/images/ResumeMatch1.png) 

<br>

[ ![Example: Summer Analyst - Locust Walk](https://chamberlainlondon.github.io/images/ResumeMatch2.png) ](https://chamberlainlondon.github.io/images/ResumeMatch2.png)

<br>

# Future Development

In the future, I aim to incorporate JavaScript, HTML, and CSS to make this software accessible to more users via the web. I would also like to supply users additional feedback regarding their resume's content.
