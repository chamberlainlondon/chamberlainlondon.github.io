---
title: "'Resume Match' Software (2024)"
excerpt: "Developed a student-centered desktop application that analyzes your resume against a provided job application"
collection: portfolio
toc: true
tags:
  - python
---
------

During the Spring 2024 Semester, I developed a Python program called "Resume Match." This tool aims to help individuals (primarily college students) improve their resumes by comparing them to a job application description and suggesting relevant keywords to include.

The script uses several libraries, including [tkinter](https://docs.python.org/3/library/tkinter.html) for creating the graphical user interface (GUI), [nltk](https://www.nltk.org/) for natural language processing tasks such as tokenization, part-of-speech tagging, and lemmatization, and fitz from the [PyMuPDF](https://github.com/pymupdf/PyMuPDF) library for extracting text from PDF resumes.

<style>
  blockquote {
    padding: 10px;
    background-color: #f0f0f0;
    border-left: 5px solid #31708f;
    margin: 20px 0;
  }
</style>

### Brief overview of algorithm:

> - **Upload Resume:** Users can upload their resume in PDF or DOCX format. The script reads the file and extracts the text content.
> - **Extract Verbs and Nouns:** The script analyzes the text of the resume to extract verbs and nouns using NLTK's part-of-speech tagging and lemmatization.
> - **Upload Job Application:** Users can paste a job application description into a text box. The script then extracts the verbs and nouns from the job application text.
> - **Compare Texts:** The script compares the verbs and nouns extracted from the resume with those from the job application, identifying words missing from the resume. It also generates a list of the 10 most frequently used words in the job application.
> - **Display Recommendations:** The script presents a list of the most common words found in the job applications, along with recommended additions to the user's resume for improved alignment with the job application.

This software was inspired by my experience applying for summer internships, where I spent hours sifting through each application for keywords to enhance my resume. By highlighting relevant keywords and skills, the tool helps individuals better-align their resumes with job descriptions, demonstrating to employers that they are a good fit for the position.

### Example Results:

<br>

[ ![Example: Data Analyst - Texas Democratic Party](https://chamberlainlondon.github.io/images/ResumeMatch1.png) ](https://chamberlainlondon.github.io/images/ResumeMatch1.png) 

<br>

[ ![Example: Summer Analyst - Locust Walk](https://chamberlainlondon.github.io/images/ResumeMatch2.png) ](https://chamberlainlondon.github.io/images/ResumeMatch2.png)

<br>

In the future, I aim to incorporate JavaScript, HTML, and CSS to make this software accessible to more users via the web, and I would like to supply users additional feedback regarding their resume's content.
