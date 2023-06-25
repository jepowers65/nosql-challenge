# nosql-challenge
_____

## Scenario
#### The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

____

## Part 1: Setup Database in Jupyter Notebook
#### 1. Import the establishments.json file from your Terminal. 
#### 2. Name the database and the collection. 
#### 3. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.
#### 4. Import the libraries needed into the Jupyter Notebook: PyMongo and Pretty Print (pprint).
#### 5. Create an instance of the Mongo Client.
#### 6. Confirm the database was created and data loaded properly.
    *List the databases you have in MongoDB. Confirm that uk_food is listed.
    *List the collection(s) in the database to ensure that establishments is there.
    *Find and display one document in the establishments collection using find_one and display with pprint.
    *Assign the establishments collection to a variable to prepare the collection for use.
____

## Part 2: Update the Database
### The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them. The following changes were made to the establishments collection:
#### 1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked to include it in the analysis. 
#### 2. The BusinessTypeID for "Restaurant/Cafe/Canteen" was found and all of the Business' that matched the TypeID were returned.
#### 3. The new restaurant's BusinessTypeID was updated to the identified Type ID.
#### 4. The magazine is not interested in Dover establishments, so all resturaunts with the the Dover Local Authority were identified and removed. The database was checked to ensure they were deleted.
#### 5. Some of the number values were stored as strings, when they should be stored as numbers.
    *The'update_many' was used to convert latitude and longitude to decimal numbers.
    *The'update_many' was used to convert RatingValue to integer numbers.
____

## Part 3: Exploratory Analysis

### Eat Safe, Love has specific questions they want answered, which will help them find the locations they wish to visit and avoid.

#### The NoSQL_analysis_starter.ipynb was used for this section of the challenge.

##### *RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.
##### *Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.
##### *The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.
### Questions to explore the database, and find the answers for the magazine editors.

##### Unless otherwise stated, for each question:

##### *The count_documents was used to display the number of documents contained in the result.

##### *The first document in the results was displayed using pprint.

##### *The results were converted to a Pandas DataFrame, with the number of rows printed, and the first 10 rows displayed.

#### Which establishments have a hygiene score equal to 20?

#### Which establishments in London have a RatingValue greater than or equal to 4?

##### *Hint: The London Local Authority has a longer name than "London" so the $regex was used as part of the search.

#### What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

##### *Hint: The geocode was used to find the nearest locations. A search of restaurants within 0.01 degree on either side of the latitude and longitude of the "Penang Flavours" was completed.

#### How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

##### *Hint: The aggregation method was used to answer this question.





