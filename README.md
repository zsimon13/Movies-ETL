# Movies-ETL

## Purpose
This project focused on Extracting, Transforming and Loading data in order to clean it for later analysis. The data used in this project was for a wide variety of movies that came from movie webistes, wikipedia and information in .csv documents. The data was processed as follows:
- Kaggle metadata adn MovieLens_ratings.csv were read into Pandas DataFrames
- Wikipedia JSON was converted to raw data and loaded into a Pandas DataFrame

## Extract, Transform and Load
The movie data  from the 3 sources was scrubbed to first filter out anything that was not a movie, sucha s TV shows. It was then loaded into a DataFrame where null values were removed. A Regular Expression scriopt was used to remove duplicate movies based on the 'imdb_id' and loaded into another Dataframe. From there a list comprehension script was used to keep only the rows with non null values. The following data was then cleaned for analysis:
- Amount a movie mad at the Box Office
- Movie Budgets
- Movie Release Date
- Movie Running Time
This Data was isolated and cleaned using a regular expressions, lambda funtions and parse funcitons to ensure only reliable and useful data would be kept. (a piece of this scripting is shown below):

![cleaning](https://user-images.githubusercontent.com/102814578/173982282-efe1a0ed-90c2-4d65-acba-231750d2b1c4.png)

Script was the written to link data back to the original Wiki, Kaggle and MovieLens files and set them equal the respective DataFrames that were created in the above steps.
![link](https://user-images.githubusercontent.com/102814578/173982127-65413455-1821-4ddf-8a78-9e303bad730c.png)


At this point the DataFrames contained unnecessary columns that wither had missing values or duplicated information between data files, so these columns were either dropped or replaced with approprioate information from one of the 3 files. Once data was appropriately cleaned, they were merged into a 'movies' table and a 'ratings' table. These tables were linked and loaded into the PostGres SQl database in order to confirm the relevent information was present.

![load](https://user-images.githubusercontent.com/102814578/173982044-f0acf577-19e2-4918-a101-48dea1a3fcb8.png)

![movies_query](https://user-images.githubusercontent.com/102814578/173981626-b0199405-92a9-46c0-b98f-a33d6d627eef.png)
![ratings_query](https://user-images.githubusercontent.com/102814578/173981670-597c8c86-6c10-4778-aafd-06d9493a569e.png)

### Resources
JSON, pandas, numpy, SQLAlchemy, PostgreSQL
