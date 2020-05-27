# yuchingcheng.github.io
# My Python codes for the project on biotech IPOs evaluations 

# Import libraries
import requests
from bs4 import BeautifulSoup

# Collect data from an evaluation webpage
evaluation = requests.get('https://www.bostonglobe.com/business/2016/02/02/edit$

# Create a BeautifulSoup object
soup = BeautifulSoup(evaluation.text,'html.parser')

# Remove unwanted terms
last_terms = soup.find(class_="html-render")
last_terms.decompose()

# Pull all text from the article body div
biotech_evaluation_text = soup.find(class_='body | gutter_16--desktop gutter_16$

# Pull text from all instances of <p> tag within the article body div
biotech_evaluation_text_items = biotech_evaluation_text.find_all('p')

# Print all the text
for biotech_evaluation in biotech_evaluation_text_items:
        print(biotech_evaluation.prettify())


