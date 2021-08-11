# Diabetes Incidence Around the Globe

Globally, diabetes has been on the increase due to many factors. In this project I tackle how much this disease has increased in the last decade, and how has it increased compared to population growth for each country. Being a person that suffers from this disease, it interests me how it has been on the increase globally and this project showcases this interest as well as my desire to show my results to everyone.

## Technologies Used and Complexities of the Project

The technologies used in the project were Tableau, Excel and the programming language Python, were I used many libraries. These libraries were:

- Selenium
- BeautifulSoup
- Pandas
- OS 
- Re (Regex)
- xls2xlsx

In the past, I have been working with the majority of all the libraries listed here when taking classes for my Master's degree or from online classes in Udacity, Udemy, or Coursera, but I had been wanting to get my feet wet using web scrapping tools as well. I decided that I needed to get information through verified websites that could give me accurate numbers for diabetes globally when I eventually stumbled on IDF's website. I saw that to get the information for all countries there I needed a library that could click on the search bar, place the name of the country and hit the enter button to then be able to click on the download button for the .xls file for the country. I then found that `Selenium` could be able to automate this, and therefore went straight ahead and used this library to retrieve all the .xls files for all countries in the IDF website. It took me a while until I managed to get it to work for one country and be able to reproduce that in a for loop to all the rest of the countries. It was a great introduction to web scrapping as well as an excellent way to automate repetitive tasks for future endeavors. 

Another complexity faced in the project was trying to collect the ISO 3 letter codes of all countries of the Diabetes dataset. I had to go out of my way to use this information to be able to merge the data that I retrieved from the IDF website and the population data as it had the 3 letter abbreviations for all countries. The other issue was that the country names were different from one dataset to the other, so the only way I could merge them was through the use of the ISO 3 letter codes. 

I found a page with the information required (World Population Page website) and needed to extract the table with all the information required. I used `BeautifulSoup` paired with the `Requests` library to retrieve that data. In the beginning, there were some issues trying to retrieve the data as the column names were not defined in the html so I needed to loop through all the rows to retrieve the information in order as it appeared. This therefore took some time to figure out as I was not used to handling html or any sort of webscrapping tool before this project, but it definitely fascinated me once I got the code to work as I wanted.

Once I got all the information, I needed to merge the Diabetes data to the ISO 3 letter code information I gathered but another problem emerged. The two datasets had different countries, some had more countries than the other dataset and this made it complicated to merge. Therefore, I used the `Re` (Regular Expressions package) to be able to retrieve the names of the countries that had diabetes information which where all in .xls files. First, I needed to convert the .xls files to .xlsx as `Pandas` could not be able to open the files so I found the `xls2xlsx` library to do that conversion for me. Once that was done, to access the names of the files, I used the `OS` package and looped through all of them and made a new dataframe using `Pandas`. Once I got the dataframe, I converted it to a .csv file to compare it to the .csv file with the 3 letter ISO codes. This was the only part of the project that didn't involve any coding, I manually cleaned the 3 letter ISO code .csv file to have the same countries as the diabetes dataset to be able to merge them. Once I did that, the diabetes dataset was ready with the new 3 letter country abbreviation.

The last thing which I had no experience with was using `Tableau` to create a dashboard. I had used in the past `Spotfire` as my BI software and it resembled a lot to `Tableau`. As soon as I cleaned the diabetes dataset merged with the population dataset, I exported the .csv file to `Tableau` and generated different visualizations and created new calculated columns such as the Percentage Increase of Population and Diabetes in the Last Decade and the Difference in Diabetes and Population Increase for each country in the dataset. This resulted in some map visualizations that can be seen where the Red colored countries indicate Diabetes increase is greater than the Population increase and the Blue colored ones indicated that Population increase is higher than the Diabetes increase. On average, the diabetes increased globally 64.29% as compared to the population which increased 13.09% in the last decade.

## How to Open Project

The first thing you would want to do is open the `Tableau` .twbx file where you will find the dashboard and be able to interact with the visualization. You can click on any country and the information for that particular country will show in the CrossTable below the Map visualization. Alternatively, you may want to visualize the data for a particular country by hovering on top of the country in the Map. 

If you want to see the code files where I extracted the information from the IDF page, you can download the .ipynb named "Extracting Diabetes Data". On the other hand if you want to see the rest of the code you can download the file named "Modifying XLS Files Web Scrapping and Data Cleaning".  

## References

- *IDF diabetes ATLAS 9th edition*, electronic dataset, IDF Diabetes Atlas 9th Edition, accessed 22 July 2021, <https://diabetesatlas.org/data/en/>.

## License

