# Skilharvest-Group-3-Project
---
## My First Group Project with Skilharvest Academy
---
### Project Overview : 
---
#### "The Evolution of Action Movies: From Explosions to Animation"

In the early 1980s, action movies were all the rage. Films like "Die Hard" (1988) and "Terminator" (1984) dominated the box office, with their high-octane action sequences, memorable one-liners, and charismatic leads. These films were made on relatively modest budgets, with "Die Hard" costing around $28 million and "Terminator" costing around $6.4 million.
As the decades passed, the action movie genre continued to evolve. The 1990s saw the rise of martial arts films, with movies like "Rush Hour" (1998) and "Enter the Dragon" (1993) showcasing impressive fight choreography. These films had slightly higher budgets, with "Rush Hour" costing around $33 million and so on.
This Project aims to showcase the trends in production of movies, budget and Revenue, and the popularity of directors of the different movies alike. To uncover the patterns and revenue gotten within the data and the growth of the impact of the movies and the directors alike and the popularity globally in order to provide valuable insight for movie lovers like myself and industry experts. Sit back and journey with me as we explore these data.

#### Data Sources: 
---
The data set used in this project was gotten from Kaggle.com

#### Tools Used:
---
- Microsoft Excel:  which can be online downloaded
- Google worksheets
- Power BI: To give reports in form of Visuals.

#### Data Cleaning:
---
Using Power query on Excel, we filtered out unwanted data, removed some unnecessary columns, errors, we removed some lines that have empty spaces. We splitted columns and removed Duplicates.


### Table Used:


[Movie data cleaned.xlsx](https://github.com/user-attachments/files/17909341/Movie.data.cleaned.xlsx)


#### Exploratory Data Analysis: 
---
We plotted Bar charts, pie Charts, calculated to summation, total sum of revenue, average revenue across the genres and director counts and the top 10 directors on the data by revenue.

#### Visualizations Tools: 
---
Power BI, a  Business analytic Service/tool by Microsoft. 

#### Visualizations:
---
![Movie Visualization 1](https://github.com/user-attachments/assets/c3474c82-4865-4162-bc29-13c7bcd35ca7)
<img width="551" alt="Movie Visualization 2" src="https://github.com/user-attachments/assets/e5d38f54-ccfc-4351-b79b-848c56314493">
![Movie Visualization 3](https://github.com/user-attachments/assets/addc366b-176d-4c72-bceb-696ce0815ebc)
![Movie Visualization 4](https://github.com/user-attachments/assets/014a6241-a80d-4f5f-8f67-7f9bd9e49c07)
![Movie Visualization 5](https://github.com/user-attachments/assets/86c1ca02-2587-418e-b55c-0e079237398c)

#### Story:
---
This data-set was analysed for more enthusiast to focus on genre trends, and Revenue Analysis of movies produced in the Europe and United States of America. To analyse the budgets spent and the revenues gotten from different genre of the movies around the year, 2016 to 2019. So before we dive into the Analysis,  we cleaned the data, removing the unwanted reports and taking out empty spaces alike. The rise of animations and action movies has led to increasing budgets and revenues. 

Movie trends has changed considerably from the 90s, and even In the 2000s, the action movie landscape shifted. The success of CG I-heavy films like "The Matrix" (1999) and "Spider-Man" (2002) paved the way for more visually stunning and fantastical action movies. These films had significantly higher budgets, with "The Matrix" costing around $63 million and "Spider-Man" costing around $139 million.

And then, something unexpected happened. Animation, which was once relegated to children's entertainment, began to converge with action movies. For example,  in 2004, we have "The Incredibles"  and in 2008,  "Kung Fu Panda". They  combined stunning animation with heart-pumping action sequences. These movies had relatively high budgets, with "The Incredibles" costing around $92 million and "Kung Fu Panda" costing around $60 million.

Today, the lines between action movies and animation have increasingly gone thinner. Live-action films like "Deadpool" (2016) and "Logan" (2017) incorporate cartoon-ish humor and stylized action, while animated films like "Spider-Man: Into the Spider-Verse" (2018) push the boundaries of visual storytelling. 

But what's really driving this trend? Let's take a look at the numbers on our Data:
- The average budget for a live-action action movie has increased from around $20 million in the 1980s to over $100 million today.
- The average revenue for a live-action action movie has also increased, from around $50 million in the 1980s to over $500 million today. 
- Animated action movies have seen a similar increase in budget and revenue, with films like "The Incredibles" and "Kung Fu Panda" grossing over $1 billion worldwide.

#### The trend is clear: action movies and animation are converging, and the budgets and revenues are skyrocketing.

What's driving this trend? 

- Technological advancements: Improvements in CGI and animation software, like; 3G involving to 4G and now we have 5G Animation and Green Screen, have made it possible to create more realistic and detailed action sequences.
-  Changing audience preferences: Audiences increased sophistication, lead to them demanding more complex and visually stunning storytelling.
-  The rise of geek culture: The growing popularity of comic books, video games, and sci-fi/fantasy franchises has created a new generation of fans who crave action-packed, visually stunning entertainment.
   
As the action movie and animation genres continue to evolve, one thing is clear: the future of entertainment will be more thrilling, more visually stunning, and more converged than ever before.
 
Also, most of these movies were created in technologically advanced countries like United Kingdom, USA, China etc... but the trends shift towards the  United Kingdom and the United States of America.... There were Collaborations in some with other countries but mostly produced in these 2 countries. 

Hence, a story about the 10 most popular movies, their countries of production, and their directors:

#### Data Analysis; 
---
 
    #Source = Excel.Workbook(File.Contents("C:\Users\PObekpe\Downloads\Financial Modelling\Power BI\Group Project.xlsx"), null, true),
    #Sheet1_Sheet = Source{[Item="Sheet1",Kind="Sheet"]}[Data],
    #"Promoted Headers" = Table.PromoteHeaders(Sheet1_Sheet, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"index", Int64.Type}, {"budget", Currency.Type}, {"genres", type text}, {"homepage", type text}, {"id", Int64.Type}, {"keywords", type text}, {"original_language", type text}, {"original_title", type any}, {"overview", type text}, {"popularity", type number}, {"production_companies", type text}, {"production_countries", type text}, {"release_date", type date}, {"revenue", Currency.Type}, {"runtime", Int64.Type}, {"spoken_languages", type text}, {"status", type text}, {"tagline", type text}, {"title", type any}, {"vote_average", type number}, {"vote_count", Int64.Type}, {"cast", type text}, {"crew", type text}, {"director", type text}}),
    #"Split Column by Delimiter" = Table.SplitColumn(#"Changed Type", "production_countries", Splitter.SplitTextByEachDelimiter({","}, QuoteStyle.Csv, false), {"production_countries.1", "production_countries.2"}),
    #"Changed Type1" = Table.TransformColumnTypes(#"Split Column by Delimiter",{{"production_countries.1", type text}, {"production_countries.2", type text}}),
    #"Removed Columns" = Table.RemoveColumns(#"Changed Type1",{"production_countries.2"}),
    #"Filtered Rows" = Table.SelectRows(#"Removed Columns", each true),
    #"Split Column by Delimiter1" = Table.SplitColumn(#"Filtered Rows", "production_companies", Splitter.SplitTextByEachDelimiter({","}, QuoteStyle.Csv, false), {"production_companies.1", "production_companies.2"}),
    #"Changed Type2" = Table.TransformColumnTypes(#"Split Column by Delimiter1",{{"production_companies.1", type text}, {"production_companies.2", type text}}),
    #"Removed Columns1" = Table.RemoveColumns(#"Changed Type2",{"production_companies.2"})
    #"Removed Columns1"
    
#### Insight
---
 Come with me as we explore the 10 most popular movies, their countries of production, and the visionary directors who brought them to life.
1. Avengers: Endgame (USA, 2019) - Directed by Anthony and Joe Russo. Revenue grossing a total of $2.79 billion worldwide.
2. Avatar (USA, 2009) - Directed by James Cameron. This ground-breaking film grossed over $2.78 billion worldwide.
3. Titanic (USA, 1997) - Directed by James Cameron. This timeless classic grossed over $2.18 billion worldwide.
4. Star Wars: The Force Awakens* (USA, 2015) - Directed by J.J. Abrams. This intergalactic adventure grossed over $2.06 billion worldwide.
5. Avengers: Infinity War (USA, 2018) - Directed by Anthony and Joe Russo. This cinematic spectacle grossed over $2.05 billion worldwide.
6. The Lion King (USA, 2019) - Directed By John Favreau. This majestic film grossed over $1.73 billion worldwide.
7. Jurassic World (USA, 2015) - Directed by Colin Trevorrow. This prehistoric adventure grossed over $1.67 billion worldwide.
8. The Avengers (USA, 2012) - Directed by Joss Whedon. This superhero extravaganza grossed over $1.52 billion worldwide.
9. Black Panther (USA, 2018) - Directed by Ryan Coogler. This groundbreaking film grossed over $1.35 billion worldwide.
10. The Last Jedi (USA, 2017) - Directed by Rian Johnson. This intergalactic epic grossed over $1.33 billion worldwide.
