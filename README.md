# README

## Overview
This repository contains a study guide for the Control Science and Engineering Comprehensive Exam.

## Source Data
The content is derived from two sources provided by the user:
1.  `exam_chapters.zip`: This archive contained structured Markdown and JSON files with real exam questions, answers, and analyses. These files were unzipped into the `extracted_content/` directory.
2.  `同等学力人员申请硕士学位控制科学与工程学科综合水平全国统一考试大纲（第二版）.pdf`: This PDF provided the syllabus and outline of fundamental concepts.

## Generation Process
The `guide.md` file was manually synthesized by:
1.  Extracting the syllabus topics from the PDF to form the "Fundamental Concepts" sections.
2.  Selecting representative real exam questions from the `extracted_content` (specifically chapters 3, 4, 5, and 6 which correspond to "Real Exam Selections").
3.  Analyzing the provided solutions to extract "Generic Rules" for solving similar problems.

## File Structure
-   `guide.md`: The main study guide artifact.
-   `extracted_content/`: Directory containing the raw chapters extracted from the zip file.
-   `extract_pdf.py`: A utility script used to read the text from the PDF syllabus.
