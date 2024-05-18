# Netflix-Dashboard (EXCEL, SQL,POWER BI)
There is two dashboard one is Overview and other is Single title view.
## About Data:

This is the real data of Netflix.

##Problem Statement:

The Netflix dataset problem statement typically involves analyzing a large dataset of movies and TV shows available on the streaming platform to gain insights and answer specific business questions. 


### Context
Netflix is one of the leading streaming platforms globally, offering a wide variety of TV shows, movies, documentaries, and other content. The company's extensive library includes content across multiple genres and languages. To maintain its competitive edge and improve user experience, Netflix continually analyzes data related to its content library, user interactions, and viewing habits.

### Objective
The objective of this analysis is to explore and analyze the Netflix dataset to extract valuable insights that can help in making data-driven decisions. These insights could be used for content acquisition, personalized recommendations, marketing strategies, and understanding viewer preferences and trends.

### Dataset Description
The Netflix dataset contains information about movies and TV shows available on the platform. The key attributes of the dataset include:

Title: The name of the movie or TV show.
Director: The director of the movie or TV show.
Cast: The main actors in the movie or TV show.
Country: The country where the movie or TV show was produced.
Date Added: The date when the movie or TV show was added to the platform.
Release Year: The year when the movie or TV show was originally released.
Rating: The rating given to the movie or TV show (e.g., PG, TV-MA).
Duration: The duration of the movie (in minutes) or the number of seasons for a TV show.
Genres: The genres associated with the movie or TV show.
Description: A brief description of the movie or TV show.

This Project is done by using EXCEL, SQL AND POWER BI.

### Steps followed 

- Step 1 : Open the data in excel file.

- Step 2 : All the data is messed up as in one column of cast, director, country and listed_in there are n number of values in each row of these column separated by ',' so, first work is to split the data into a standard from. For this all the columns of cast, director, listed in, country are splitted by ',' so that in each row of a column cast, director, listed in, country have only one value. This can be done to each column one by one first select one column for ex- cast and then click Data--> Data Tools--> Text to column--> delimited--> Next--> In delimited, choose comma--> Next--> Finish and repeat the same for other columns director, country and listed_in.

- Step 3 : It has been observed that director column has been splitted into 13 columns, country into 12 columns, cast into 50 columns, and listed_ in into 3 columns. Give column name to all the splitted column (For ex- cast_1, cast_2, cast_3,............., cast_50)
- Step 4: It is notice that the splitted column have blank spaces before the values so we have to trim all the columns of cast, director, country and listed_in by using Trim() function.

- Step 4 : Then 6 sheets with the name netflix_title, cast, director, country, listed_in, description were made and save as (.csv)file . And all the columns of cast will be cut paste values to cast sheet, column of directors will be cut paste values to directors sheet, columns of country will be cut and paste values to country sheet, all the column of listed_in will be cut and paste values to listed_in sheet and description column will be cut paste values to description sheet and remaining column, i.e., show_id, type, title, date_added, release year, rating, duration will be remain to netflix_title.

- Step 5 : As Netflix_title has show_id column is unique and had a relation with each of the column in other sheets, we copy and paste the show_id as the first column to all the other 5 sheets to make a relationship with each column of other sheets.

- Step 6 : In netflix_title sheet, it observed that duration is in two forms minutes or seasons so we split the duration column with delimited space. so, we get duration column as values and we name the splitted column as duration_type. Also, it has been noticed that there are 3 blank values in duration and duration_type and there values are in rating column so, as there are only 3 values so rewrite the values of duration and duration_type manually from the rating column and delete the values from rating column.

- Step 7: Separate all the sheets into different workbooks and save by the name netflix_title , cast, director, country, listed_in, description.

- Step 8 : Now, in workbook cast, director, country and listed_in , there is a blank space in rows of each column, so, replace the blank space by NULL and for that in Home tab, go to Editing--> Find and selection---> Replace--> replace the blank space by NULL. 

- Step 9 : While importing the csv file, it has been noticed that all the rows are not imported because some special characteristic are present in the data, so open the excel file with notepad and save as encoding- ANSI. And then import all the 6 csv files into Netflix database in MySQL.

- Step 10 : Now, it is observed that in cast table, there is 50 columns of cast, so we union all the cast columns while ignoring the NULL values and make a single column of netflix_cast. The query is in the doc file below- 
[netflix_cast query.docx](https://github.com/anchal765/Netflix-Dashboard/files/15365817/netflix_cast.query.docx)

- Step 11 :Now, it is observed that in director table, there is 13 columns of directors , so we union all the director columns while ignoring the NULL values and make a single column of netflix_director. The query is in the doc file below- 
[netflix_directors query.docx](https://github.com/anchal765/Netflix-Dashboard/files/15365819/netflix_directors.query.docx)

- Step 12 :Now, it is observed that in country table, there is 12 columns of country, so we union all the country columns while ignoring the NULL values and make a single column of country_released. The query is in the doc file below- 
[netflix_country_released query.docx](https://github.com/anchal765/Netflix-Dashboard/files/15365823/netflix_country_released.query.docx)

- Step 13 : Now, it is observed that in listed_in table, there is 3 columns of listed_in, so we union all the listed_in columns while ignoring the NULL values and make a single column of netflix_listed_in as category. The query is in the doc file below- 
  [netflix_listed_in query.docx](https://github.com/anchal765/Netflix-Dashboard/files/15365824/netflix_listed_in.query.docx)

- Step 14 : Now, the data is all set to load in Power BI. Get the data from MySQL database in Power BI by connecting to ODBC connector and then then Transform all the tables present in Netflix database.

- Step 15 : Change the datatype of date added column in netflix_titles as date from text and load the data.

- Step 16 : Two dashboard have been made, First is Overview which represent the analysis of all the data and the Second is Single title view in which we can analyse all the information of all the titles of Movie/TV show once at a time.

- Step 17 :In overview and single title view dashboard, one rectangle shape have been added to represent the logo of Netflix by inserting logo image.
<img width="86" alt="Shape box with logo image" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/805a7e59-6c9b-4988-a36a-410363e685d6">

- Step 18 :Then, an area chart is added to represent the shows by date, so on x-axis add date_added(year) and on y-axis add count of show_id and in legend add type so the line on area chart divided into the type, i.e.,Movie and TV show.
<img width="183" alt="area chart" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/f0e8edc4-864c-48df-873f-eb81a6748131">

- Step 19 :A stacked column chart is added in overview dashboard to represent the shows by rating. Add rating on x-axis and count of show_id on y-axis and type as legend. Stacked Column Chart is divided into two group Movie and TV show by their rating.
<img width="182" alt="stacked column chart" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/97de9617-25de-4f12-a35b-beadba5db268">

- Step 20 :A clustered bar chart is added to visualise the top 10 Genres. Add category on y-axis and count of show id on x-axis.
<img width="182" alt="clustered bar chart" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/6b337ca3-4d84-49ba-91a2-78921bc481e4">

- Step 21 : A map is added to both overview and single title view dashboards represent all the countries with the count of show_id. Add the country column in location.
<img width="182" alt="map" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/2ab33581-7598-4d8d-ab40-c0302042ab62">

- Step 22 :Now, In Single title view dashboard, three cards are added one is to represent Rating by adding first rating in fields, second is to represent Release_year by adding sum of release_year in field and third is to represent the description of Movie/TV show by adding description in field.
 <img width="86" alt="rating card" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/5eccf285-544c-4e8a-8f0d-81272471c76e">
<img width="85" alt="release_year card" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/1df43c67-30cc-4d88-a01a-36d8e92b35ca">
<img width="187" alt="description card" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/03186bf6-d00e-4a90-9f31-a2cad10f3c33">

- Step 23 : A Slicer is used to visualize the title of Movie/TV shows by adding title in field section.
<img width="186" alt="slicer" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/3c2a2173-e25e-4300-8629-f31e2fc2cd9b">

- Step 24 :Three Multi-row cards are added to represent cast, directors and Genres or listed_in by adding cast, director and category in field section.
<img width="64" alt="cast multi-row card" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/cacf25e9-b788-4705-b1de-cbed4d8ccf3c">
<img width="61" alt="directed by multi-row card" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/3bbaf0d5-6c9d-47ad-97af-e631e89b6627">
<img width="62" alt="listed_in multi-row card" src="https://github.com/anchal765/Netflix-Dashboard/assets/105012057/9158bd60-7114-43de-a814-4e0ff22e63c2">


