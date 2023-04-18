# Transcription Analysis Using AWS Textract

## Introduction

### Motivation
In the modern age of technology, computers and other digital devices have become ubiquitous in daily life. Many people rely on keyboards and touchscreens to communicate, work, and learn, leading to a decrease in the amount of time spent handwriting. As college students, the increasing use of technology in the classroom means that many of us rarely touch pen and paper.

As a result, our QTM 350 group has become interested in studying the effect of computer use on handwriting. They aim to identify any changes in handwriting style, legibility, and consistency that may have occurred due to decreased handwriting practice.

To conduct such a study, researchers may collect handwriting samples from individuals who have varying levels of computer usage. Since we will be collecting samples from Emory students, we decided it would be best to classify samples by major. Since each major has a different course flow and thus varying computer usage, we can see if the students’ selected major has an effect on the legibility of handwriting. 

### Choosing an AWS ML Service
Analyzing a large number of handwriting samples manually can be tedious and time-consuming, requiring specialized training in handwriting analysis. To streamline the process, we plan to use AWS Textract, a machine-learning service that can detect and extract text and handwriting from scanned documents and images.

With Textract, we can easily upload scanned documents containing handwriting samples from individuals with different majors and extract the handwriting data automatically. Textract can also analyze handwriting samples for various characteristics, such as letter height, spacing, and slant. These characteristics could be key in identifying features that affect overall handwriting legibility.

By using Textract, we can quickly and efficiently analyze a large dataset of handwriting samples and identify any significant differences in handwriting style, legibility, and consistency between individuals of different majors. In analyzing the level of computer usage between different majors, our handwriting analysis could provide valuable insights into how computers have affected handwriting and inform the design of handwriting programs for individuals who may need to improve their handwriting skills.

### Why Does Good Handwriting Matter
Good, legible handwriting can be a vital tool in a successful academic and post-academic career. From the paper “Handwriting: A Matter of Affairs” (https://files.eric.ed.gov/fulltext/EJ1078742.pdf) it can be argued that good handwriting has several benefits, such as: 
Cognitive benefits: Handwriting engages the brain in ways that typing does not, which can lead to better memory retention and information processing.

Educational benefits: Good handwriting is important for success in school, as it is necessary for taking notes, completing assignments, and taking exams.

Social benefits: Handwriting is a personal and intimate form of communication that allows for greater creativity and personal expression than typing. It is also tied to personal identity and cultural heritage.

Professional benefits: Good handwriting is important in many professions, such as medicine and law, where clear and legible handwriting is necessary for accuracy and precision.

Good handwriting is important for both personal and professional success and is a skill that should be cultivated- even in our increasingly digital world. In analyzing the differences in handwriting between majors we hope to not only explore AWS Textract in-depth but also find valuable insights that Emory could use to increase handwriting legibility at a campus-wide level.

## Data-Collection Workflow
The data that we used was gathered from the Emory undergraduate student body. The sample was taken by asking students to complete a standardized writing task. Each student wrote with their dominant hand (indicated on form) and copied a short sentence that featured each letter of the alphabet. Students were also asked to provide information such as name, school/major, and graduating class year. A picture of the form can be found below:

![Form](/images/Form.png)

Upon completion of this form, handwriting was compiled into a single PDF with each page being a subsequent individual's response. These PDF's were filed into an S3 bucket for loading and data analysis. Once this was done, SageMaker as well as notebooks in the .ipynb format with access to Textract API were used for analysis.

## Analysis workflow
The project required an asynchronous Textract algorithm which allowed us to extract up to 5000 pages of PDF (although our data did not require this). The json was then filtered for lines of interest as well as metrics that would aid in the analysis. This was then used for separate detailed analyses that will be detailed along with the rest of code segments in the blog (Link) as well as directly available in the markdown ([Link](https://github.com/jlinschool/TranscriptionAnalysisProject/blob/main/FinalMarkdown.ipynb))

## Sample output
The following is a sample extracted

## Architectural Overview
![Roadmap](/images/Map.jpeg)

The user will first open Amazon Sagemaker where Textract API will be able to be called and subsequent data analysis will use structures from the S3 buckets possessed by the user. 
