# Laugh-Out-Loud: An ETL Project

## Laugh Out Loud
The purpose of this project is to demonstrate a full ETL pipeline from primary source to database
To that end, web scraping was performed on the video channels of five popular late-night comedians: Jimmy Fallon, Seth Meyers, Trevor Noah, Jimmy Kimmel, and Stephen Colbert. The scrape was specified to include just the videos posted between January 2020 to January 2021. 
The desired data included the titles of the videos, the runtime of each video, the number of views each video had received over its lifetime, and the comedian hosting in each video. The total lifetime of the video was also available; but this was not considered relevant. 

The webpages being targeted contained the relevant information inside a CSS-label inside an HTML tag. As such extraction was performed in two stages: the first stage specified the parent tag for the relevant HTML tag; and the second stage extracted the contents of the CSS label.
The webpages being targeted contained the relevant information inside a CSS-label inside an HTML tag. As such extraction was performed in two stages: the first stage specified the parent tag for the relevant HTML tag; and the second stage extracted the contents of the CSS label. The resulting output was in string format and preliminarily placed inside a list of strings. 
## ETL 
ETL is an acronym for Extract, Transform, Load. This is a general term describingthe process of extracting data from a source, then performing operations to transform it into a useable form, then loading it into a destination (e,g. a database). This project is an example of all three in operation. Data is extracted from different webpages using web scraping, transformed using Python functions, then loaded onto MongoDB. This ETL pipeline also works in reverse with data extracted from Mongo DBl then transformed and loaded onto a webpage using Jinja via Flask.

## Extracting Data through Web Scraping
DData in string format presents a unique challenge in that most Python operations in pandas are  specifically defined to handle integer or numeric data types. To transform the data into a useable format, Regular Expression was performed to loop through each list of strings to extract the title, runtime, viewership, of each video, along with the comedian  hosting  the video. Each piece of data was defined as a variable through regular expression then put he variables were placed inside a dictionary of variables for each video, each of these dictionaries was then appended to a list for each comedian; and to a larger list for all the comedians. As such data from about 5,000 videos was scraped; then transformed

## Transforming through Pandas and Regular Expression

## Loading to Postgres
Load: the final step of the ETL pipeline involved placing the  Comedians dataframe into an SQL database through Postgres in a table rather imaginatively named “Comedians.” A SQL database was preferred due to greater familiarity with SQL operations; and the simplicity of the dataframe which negated the primary advantages of NoSQL databases

