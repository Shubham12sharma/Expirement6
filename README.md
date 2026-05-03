Experiment No. 2
Title

Data Collection from Social Media Platforms using Web Scraping

Aim

To collect data from a website using web scraping, crawling, and parsing with Python.

Theory (Short)

Social Media Analytics involves collecting and analyzing data like posts, comments, and reviews to gain business insights.

Web Scraping: Extracting data from websites automatically
Crawling: Navigating multiple pages using links
Parsing: Converting HTML into structured format (DOM)

Tools Used:

requests → to fetch webpage
BeautifulSoup → to parse HTML




import requests
from bs4 import BeautifulSoup

# Step 1: Connect to website
url = "https://quotes.toscrape.com"
response = requests.get(url)

# Step 2: Check status
if response.status_code == 200:
    print("Connected Successfully\n")

    # Step 3: Parse HTML
    soup = BeautifulSoup(response.text, "html.parser")

    # Step 4: Extract data
    quotes = soup.find_all("span", class_="text")
    authors = soup.find_all("small", class_="author")

    # Step 5: Display data
    for i in range(len(quotes)):
        print("Quote:", quotes[i].text)
        print("Author:", authors[i].text)
        print("-" * 40)

else:
    print("Failed to connect")


import requests
from bs4 import BeautifulSoup
import matplotlib.pyplot as plt

# Fetch data
url = "https://quotes.toscrape.com"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

# Extract authors
authors = soup.find_all("small", class_="author")

author_list = [author.text for author in authors]

# Count frequency
author_count = {}
for author in author_list:
    author_count[author] = author_count.get(author, 0) + 1

# Prepare data
names = list(author_count.keys())
counts = list(author_count.values())

# Plot graph
plt.figure()
plt.bar(names, counts)

plt.title("Quotes per Author")
plt.xlabel("Authors")
plt.ylabel("Number of Quotes")

plt.xticks(rotation=45)
plt.tight_layout()

plt.show()

Conclusion (Short)

Data was successfully collected using web scraping. The requests library fetched the webpage and BeautifulSoup parsed and extracted useful information. This method is useful in social media analytics for sentiment analysis and trend detection.
