# Movies ETL
Perform the Extract Transform Load process on data about movies.

### Purpose 

I wanted to standardize the way movie data can be found, and store it in a searchable database. I followed the ETL process to create a function that could take in any data file about movies, and transform it into a usable database. I used files from Wikipedia and Kaggle to collect information on the movies and how people rated them. 

### Creating the Function

My first file, ETL_function_test, was created to make sure I could load files and turn them into pandas DataFrames using a function. 

### Cleaning the Wiki Data

Next I tackled the wikipedia data. There were TV shows that got in our list, so I removed them. Then there were many columns that only held data for a very small amount of movies, so those columns were removed as well. From there, I convered the data type of several columns, and used regular expressions to make the money and date columns consistent. 

### Cleaning the Kaggle Data

The kaggle data was overall more consistent, which makes sense considering that is a data analysis specific site, and wikipedia allows for user edits. But there were still some columns that needed formatting. 

Once the data was clean, I could merge the two dataframes to give a complete picture of the movie. For the most part, I kept the kaggle data where there were duplicate columns. It was overall more complete and consistent, but I analyzed column by column to make sure that the wiki data wasn't better. 

### Creating the Database

Once all of the dataframes were merged, I needed to upload the data to a PostgresSQL database. I chunked the data, and uploaded to an engine. To confirm the upload was successful, I quearied the tables in SQL to check the number of columns. 
