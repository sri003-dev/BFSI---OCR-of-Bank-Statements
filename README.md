## Objective

The primary goal of this application is to process documents such as bank statements, payslips, and balance sheets by extracting key information using Optical Character Recognition (OCR) and Natural Language Processing (NLP). The app also provides visualizations for the extracted data, allowing users to analyze financial documents effectively. The application supports both uploaded image files and images fetched from Cloudinary.

## Overview of Tools Used

1. **PIL (Python Imaging Library)**:
   - Used for image processing tasks such as opening, converting, and manipulating images.

2. **PaddleOCR**:
   - A deep learning-based OCR tool used to extract text from images of documents. It supports multiple languages and is used to recognize printed text from document images.

3. **Cohere**:
   - A Natural Language Processing (NLP) API used to generate text responses for extracting specific information from OCR results. It is utilized to parse the text and extract relevant data like account details, employee information, or financial values.

4. **OpenCV**:
   - A computer vision library used for image manipulation, such as converting images between formats (from PIL to OpenCV format), and performing any additional preprocessing required for OCR.

5. **Cloudinary**:
   - A cloud-based service used for storing and retrieving images. The app integrates with Cloudinary to fetch image URLs for processing, making it easier to manage large image datasets.

6. **Gradio**:
   - A Python library used for building the user interface. It allows users to upload files or select Cloudinary images, view extracted information in a tabular format, and see visualizations (bar plots or pie charts).

7. **Matplotlib**:
   - A plotting library used to create visualizations such as bar charts and pie charts for the extracted numerical data.

8. **Pandas**:
   - A data manipulation library used for organizing and displaying the extracted information in tabular format.

## Application Workflow

1. **Input Handling**:
   - The user can either upload document images directly from their device or fetch images from Cloudinary by specifying a folder prefix and selecting the number of images to process.

2. **Document Processing**:
   - The uploaded or fetched images are processed using PaddleOCR to extract textual content from the document.
   - The extracted text is passed to the Cohere API, which analyzes the content and extracts specific fields based on the selected document type (e.g., Bank Statement, Payslip, Balance Sheet).

3. **Data Extraction**:
   - Based on the document type selected (e.g., "Bank Statement"), Cohere generates a prompt to extract key pieces of information from the text, such as account holder name, transaction details, or salary breakdowns.

4. **Visualization**:
   - The extracted information is displayed in a tabular format using Pandas, showing fields such as "Account Number", "Transaction Date", "Gross Salary", etc.
   - The app can also generate visualizations (bar plots or pie charts) based on numeric data extracted from the documents, like balances or transaction amounts.
   - The visualizations are created using Matplotlib and displayed to the user.

5. **Results Display**:
   - The extracted data is displayed in an HTML table format.
   - If valid numerical data is found, visualizations (bar plots or pie charts) are generated and displayed.
   - If no text is detected or errors occur, the user is notified through error messages.

## Key Features

1. **Multi-Source Document Processing**:
   - Supports both uploaded document images and images fetched from Cloudinary, making the application versatile for different types of users.

2. **OCR Integration**:
   - Utilizes PaddleOCR for text extraction from document images, supporting various document types and languages.

3. **NLP-Powered Data Extraction**:
   - Integrates Cohere API to intelligently extract relevant information from the OCR text, such as account details, employee salaries, and financial figures.

4. **Dynamic Visualizations**:
   - The user can choose between bar charts and pie charts for visualizing extracted numeric data (e.g., transaction amounts, balances, etc.).

5. **Error Handling**:
   - In case of missing or unreadable text, the application returns clear error messages to inform the user of the issues.

6. **User-Friendly Interface**:
   - Gradio provides an easy-to-use web interface for uploading documents, selecting plot types, and viewing results with minimal setup.

7. **Cloud Integration**:
   - Integration with Cloudinary allows users to fetch document images stored in the cloud, reducing the need to manually upload files.

## Results

- **Extracted Data**: The app returns a list of fields such as account names, balances, and transactions for bank statements, net salary and deductions for payslips, and financial values for balance sheets. Each document type has a customized extraction logic.
- **Visualizations**: Depending on the document's content, the app generates either a bar plot or a pie chart, visualizing the extracted financial data for easy analysis.

## Conclusion

This document OCR, analysis, and visualization application combines advanced OCR technology with NLP and data visualization tools to process and analyze financial documents. It supports multiple input sources, integrates with cloud services, and provides a flexible, interactive user interface for both document processing and result visualization. The app is highly useful for professionals dealing with financial documents such as accountants, HR personnel, or anyone needing to automate the extraction and analysis of document data.


