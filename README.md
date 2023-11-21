# Web-Scrapping-List_of_largest_companies_in_the_United_States_by_revenue

# The following steps i have followed for web scraping from the website "https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue"
step1: Import beautifulsoup
        from bs4 import BeautifulSoup
        import requests
Step2: Take the website url, use request and beautifulsoup

url= 'https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue'
page= requests.get(url)

soup = BeautifulSoup(page.text, 'html')

Step3: Find all the table from soup

soup.find('table')

Step4: From the all table we take that table where is out top priority table and store it in list

world_title =table.find_all('th')

Step5: Import pandas and make a data frame of the table title

import pandas as pd
df = pd.DataFrame(columns = world_table_title)

Step6: We target that table where all the rows datas are available

column_data = table.find_all('tr')

Step7: Store all the data in dataframe and take it in CSV.

for row in column_data[1:]:
    row_data = row.find_all('td')
    individual_row_data = [data.text.strip() for data in row_data]
    #print(individual_row_data)
    length =len(df)
    df.loc[length]= individual_row_data

Step8 : Take that data in our system

df.to_csv(r'E:\powerBI DASHBOARD\Companies.csv', index = False)

Step9: Finally made powerBi Dashboard of these data. 

![Uploading List of largest companies in US and its comparisons.png…]()


