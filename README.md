# Web-Scraping-in-Python

## Project Overview
The purpose of this project was to show web scraping techniques using the BeautifulSoup library in Python to show the ability to gather data from various sources. I was curious about what the top most common first and last names were in the US and was able to find a good website to scrape and then analyze. I was also curious to discover what names are commonly used for both males and females. After scraping the data from the website, the project uncovers various insights such as the names shared by both male and female as mentioned before as well as top 10 most common first names in both male and female demographics and more.

Review the python jupyter notebook *[HERE](https://github.com/msanders25/Data-Cleaning-in-SQL/blob/main/gym%20data%20cleaning.sql)*

The website that was scraped contains info on the top most common surnames, male first names, and female first names. Links can be found on the website to look at the names categorized in other forms. Included with the names are data containing an approximate number for the number of times the name is used, percentage of frequency, and rank.

The website can be found at this link: 
 - *[names.mongabay.com](https://names.mongabay.com/most_common_surnames.htm)*

The scraped data has been exported to an excel and can be found at the link below:
 - *[names.xlsx](https://github.com/msanders25/Data-Cleaning-in-SQL/blob/main/nc_gym_data.csv)*
 
## Project Challenges and Solutions
While this project presented various challenges, the following were particularly demanding and required additional research to achieve the desired outcomes.

### Challenge 1 - Scraping Data From Multiple Pages
The web pages containing the last names were broken across several web pages and the url for each page was non-continuous making it difficult to use loops for looping through each page and scraping the data.

### Solution 1 - Comprehensive List
The number of pages containing the last names was not long, so I inspected the urls for each page to determine a unique identifier for each page. The number at the end of each url jumped around but I made a list with these numbers in the notebook. From there, I wrote code that would loop through each page using each item in the list of unique web page identifiers. This way I was able to get hold of the data needed for each page and add it to a data frame.

### Challenge 2 - Common Male and Female Names
I wanted to create a table that would show the names found in both the common male and female first names and how many times the names were used by both demographics. Various attempts to create lists of the male and female names and combine them to find duplicates produced errors.

### Solution 2 - Duplicate List
To create the data frame, I created a duplicate list that was updated for each item in a male name list if the name was also found in the female list. The duplicated list contained the names common to both male and females. From there, I used the isin function to create new filtered male and female lists that I could use to extract the number of uses for each duplicate name and then store in another usage list for both demographics. From there I was able to create a dictionary of the duplicate list and each accompanying male and female usage of each duplicate name to then convert to a data frame.

## Project Insights
- Top 10 Last Names - Smith, Johnson, Williams, Jones, Brown, Davis, Miller, Wilson, Moore, Taylor.
- Top 10 Male First Names - James, Joh, Robert, Michael, William, David, Richard, Charles, Joseph, Thomas
- Top 10 Female First Names - Mary, Patricia, Linda, Barbara, Elizabeth, Jennifer, Maria, Susan, Margaret, Dorothy
- Average Use of Last Names Starting with Each Letter - Last names starting with the letter J had the highest usage. W was second.
- Average Use of Male First Names Starting with Each Letter - Male first names starting with the letter J had the highest usage. P was second.
- Average Use of Female Last Names Starting with Each Letter - Female first names tarting with the letter P had the highest usage. B was second.
- Top 10 Male First Names Shared with Females - James, John, Robert, Michael, William, David, Richard, Charles, Joseph, Thomas
- Top 10 Female First Names Shared with Males - Mary, Patricia, Maria, Carol, Shirley, Frances, Jean, Joan, Ashley, Kelly

The visualizations displaying these insights are column charts found in step 4 in the jupyter notebook.

## Methods and Processes
The process I followed for this project consisted of 4 main steps:
- Scraping the data
- Cleaning the data
- Creating data frames for visualizations
- Plotting graphs

Various functions in python were used such as:
- loops
- def functions
- if, elif
- lists
- dictionaries
- BeautifulSoup
- isin
- tolist
- str.startswith

More functions were used but the above list provides an example of the type of python code used in this project.




