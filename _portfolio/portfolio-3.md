---
title: ""Resume Match" Python Application"
excerpt: "Developed a student-centered desktop application that analyzes your resume against a provided job application"
collection: portfolio
---
------

In my spare time, I created a Python program called "Resume Match." This tool aims to help individuals improve their resumes by comparing them to a job application description and suggesting relevant keywords to include.

The script uses several libraries, including tkinter for creating the graphical user interface (GUI), nltk for natural language processing tasks such as tokenization, part-of-speech tagging, and lemmatization, and fitz from the PyMuPDF library for extracting text from PDF resumes.

### Brief overview of how the algorithm works:

> **Upload Resume:** Users can upload their resume in PDF or DOCX format. The script reads the file and extracts the text content.

> **Extract Verbs and Nouns:** The script analyzes the text of the resume to extract verbs and nouns using NLTK's part-of-speech tagging and lemmatization.

> **Upload Job Application:** Users can paste a job application description into a text box. The script then extracts the verbs and nouns from the job application text.

> **Compare Texts:** The script compares the verbs and nouns extracted from the resume with those from the job application, identifying words missing from the resume. It also generates a list of the 10 most frequently used words in the job application.

> **Display Recommendations:** The script presents a list of the most common words found in the job applications, along with recommended additions to the user's resume for improved alignment with the job application.

By highlighting relevant keywords and skills, the tool can help individuals better align their resumes with the requirements of a particular job, leading to more opportunities.

### Code:

```python

from tkinter import Tk, Label, Button, Text, filedialog, Scrollbar, RIGHT, Y, BOTH, END
import ssl
import nltk
import fitz  # PyMuPDF
from nltk import pos_tag, word_tokenize
from nltk.stem import WordNetLemmatizer
import os
from collections import Counter
from nltk.corpus import stopwords
from nltk.corpus import wordnet
import webbrowser
from docx import Document

# Set NLTK data path
nltk.data.path.append("/Users/london.chamberlain/nltk_data")

# Disable SSL certificate verification
ssl._create_default_https_context = ssl._create_unverified_context

# Download the averaged_perceptron_tagger and wordnet resources
nltk.download('averaged_perceptron_tagger', download_dir="/Users/london.chamberlain/nltk_data")
nltk.download('wordnet', download_dir="/Users/london.chamberlain/nltk_data")
nltk.download('punkt')
nltk.download('stopwords')

# Set stop words
stop_words = set(stopwords.words('english'))

def upload_resume():
    global resume_content
    resume_file_path = filedialog.askopenfilename(title="Select Resume", filetypes=[("PDF files", "*.pdf"), ("Word documents", "*.docx")])
    if resume_file_path:
        if resume_file_path.endswith('.pdf'):
            resume_content = read_pdf_resume(resume_file_path)
        elif resume_file_path.endswith('.docx'):
            resume_content = read_word_resume(resume_file_path)
        submit_button.config(state="normal")  # Enable the submit button
        upload_note.config(text="File uploaded: " + os.path.basename(resume_file_path))

def read_pdf_resume(file_path):
    resume_content = []
    with fitz.open(file_path) as pdf:
        for page_num in range(len(pdf)):
            page = pdf.load_page(page_num)
            text = page.get_text()
            resume_content.append(text)
    return resume_content

def read_word_resume(file_path):
    doc = Document(file_path)
    resume_content = []
    for paragraph in doc.paragraphs:
        resume_content.append(paragraph.text)
    return resume_content

def read_resume(pdf_file):
    resume_content = []
    with fitz.open(pdf_file) as pdf:
        for page_num in range(pdf.page_count):
            page = pdf[page_num]
            text = page.get_text()
            resume_content.append(text)
    return resume_content

def is_plural(word):
    lemma = wordnet.morphy(word, wordnet.NOUN)
    if lemma:
        plural = wordnet.morphy(lemma, wordnet.NOUN)
        if plural and plural != lemma:
            return True
    return False

def extract_verbs_nouns(text):
    lemmatizer = WordNetLemmatizer()

    words = word_tokenize(text)
    verbs_nouns = [lemmatizer.lemmatize(word.lower(), 'v') for word in words if word.isalpha() and word.lower() not in stop_words]

    filtered_verbs_nouns = set()
    for word in verbs_nouns:
        if not is_plural(word):
            filtered_verbs_nouns.add(word)

    return filtered_verbs_nouns

def compare_resume(user_input, resume_content):
    resume_verbs_nouns = set()
    for text in resume_content:
        resume_verbs_nouns.update(extract_verbs_nouns(text))

    user_verbs_nouns = extract_verbs_nouns(user_input)

    missing_words = user_verbs_nouns - resume_verbs_nouns

    return list(missing_words)

def update_stop_words(job_position, company_name):
    global stop_words
    stop_words.update(word_tokenize(job_position.lower()))
    stop_words.update(word_tokenize(company_name.lower()))

# Update submit_job_application function
def submit_job_application(event=None):
    job_position = job_position_text.get("1.0", "end-1c")
    job_application = job_application_text.get("1.0", "end-1c")
    company_name = company_name_text.get("1.0", "end-1c")
    
    update_stop_words(job_position, company_name)

    words = [word for word in word_tokenize(job_application.lower()) if word.isalpha() and word not in stop_words]
    word_freq = Counter(words)
    most_common_words = word_freq.most_common(10)

    if most_common_words:
        result_text.delete(1.0, END)  # Clear previous recommendations
        result_text.insert(END, "Most frequent words in job application:\n")
        for word, freq in most_common_words:
            result_text.insert(END, f"{word}: {freq}\n")
        result_text.insert(END, "\n")

    recommendations = compare_resume(job_application, resume_content)
    if recommendations:
        result_text.insert(END, "Consider adding the following words to your resume:\n" + "\n".join(recommendations))
    else:
        result_text.insert(END, "Your resume already contains all the relevant words from the job application.")

def open_link():
    webbrowser.open_new("https://chamberlainlondon.github.io/")

# Tkinter

# Create Tkinter window
root = Tk()
root.title("Resume Match")

# Title button
title_button = Button(root, text="Welcome to Resume Match! (Made by London Chamberlain)", cursor="hand2", bd=0, fg="blue", relief="flat", highlightthickness=0)
title_button.pack(side="top", pady=10)
title_button.config(command=open_link)

# Upload resume button
upload_button = Button(root, text="Upload Resume", command=upload_resume)
upload_button.pack()

# Upload note label
upload_note = Label(root, text="")
upload_note.pack()

## Text label for job application position
job_position_label = Label(root, text="Job Title:")
job_position_label.pack(anchor='w')

# Job application position text box
job_position_text = Text(root, height=1, width=40, wrap="word")
job_position_text.pack(fill=BOTH, expand=True, anchor='w')

# Text label for job application company
company_name_label = Label(root, text="Company:")
company_name_label.pack(anchor='w')

# Job application company text box
company_name_text = Text(root, height=1, width=40, wrap="word")
company_name_text.pack(fill=BOTH, expand=True, anchor='w')

# Text label for job application description
job_application_label = Label(root, text="Job Application Description:")
job_application_label.pack(anchor='w')

# Job application description text area
job_application_text = Text(root, height=10, width=100, wrap="word")
job_application_text.pack(fill=BOTH, expand=True, anchor='w')

# Submit button
submit_button = Button(root, text="Submit for Recommendations", command=submit_job_application, state="disabled")  # Disabled initially
submit_button.pack(pady=10)

# Text label for recommendations
result_label = Label(root, text="Job application recommendations:")
result_label.pack(anchor='w')

# Result text area with scrollbar
result_text = Text(root, height=10, width=40, wrap="word")
result_text.pack(fill=BOTH, expand=True)

scrollbar = Scrollbar(root, command=result_text.yview)
scrollbar.pack(side=RIGHT, fill=Y)
result_text.config(yscrollcommand=scrollbar.set)

# Bind Enter key to submit button
root.bind('<Return>', submit_job_application)

# Start Tkinter event loop
root.mainloop()


```
