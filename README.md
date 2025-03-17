### **Web Scraping and Data Extraction: How It Was Done**  

Web scraping is a powerful technique used to extract data from websites, and in this project, I successfully retrieved a list of wetlands consultants from the **Michigan Department of Environment, Great Lakes, and Energy (EGLE)** website. Below is an overview of how I accomplished this task using Python.  

#### **1. Setting Up the Web Scraper**  
- I used the **`requests`** library to send an HTTP request to the webpage and retrieve its HTML content.  
- To prevent my request from being blocked, I added a **User-Agent header**, making the request appear as if it came from a real web browser.  

#### **2. Parsing the Webpage Content**  
- I used **BeautifulSoup**, a popular Python library for parsing HTML and extracting relevant elements.  
- The script searched for a **table element**, assuming the data was structured in a table format.  
- If the table was not found, the program displayed an error message and exited.  

#### **3. Extracting Data from the Table**  
- I identified the **rows (`<tr>`)** and **columns (`<td>`)** within the table.  
- Skipped the **header row** to avoid including column names in the extracted data.  
- Extracted key details such as:  
  - **Consultant Name**  
  - **Contact Information**  
  - **Email Address** (checked if an email link existed)  
  - **City**  
- If a row contained missing values, it was **skipped** to ensure data integrity.  

#### **4. Storing Data in an Excel File**  
- After extracting the data, I used **Pandas** to create a **DataFrame**, which organizes data in a tabular format.  
- The DataFrame was then saved as an **Excel file (`wetlands_consultants.xlsx`)** for easy access and analysis.  

#### **5. Error Handling and Validations**  
- If the **webpage request failed**, the script displayed an error message and stopped execution.  
- If **no data was extracted**, it alerted the user that the webpage structure might have changed.  
- The script ensured at least **four columns** were present in each row to prevent extraction errors.  

### **Conclusion**  
This project demonstrates an efficient method for automating data collection from a public website. By combining **requests, BeautifulSoup, and Pandas**, I was able to extract, clean, and store relevant information in a structured format. This approach can be extended to other web scraping tasks, making data retrieval faster and more efficient.# Data-Scrapping
