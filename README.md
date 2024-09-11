# Netflix Movies and TV Shows Data Analysis using SQL





select * from netflix

//1)Count the Number of Movies vs TV Shows//

SELECT COUNT(*) AS NUMBER FROM netflix

//2)List All Movies Released in a Specific Year ex- 2019//

SELECT * FROM netflix
WHERE release_year = 2019;

//3)Find All Content Without a Director//

SELECT * FROM netflix
WHERE director IS NULL;

//4 Count the Number of Content Items in Each Genre//

SELECT UNNEST(STRING_TO_ARRAY(listed_in, ',')) AS genre,COUNT(*) AS no_of_content
FROM netflix
GROUP BY 1;

//5) List All Movies that are Documentaries //

SELECT * FROM netflix
WHERE listed_in LIKE '%Documentaries';
