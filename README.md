# How I Completed My Web Scraping Project

## What I wanted to scrape

I wanted to scrape data from the Wildlife page on defenders.org. For each animal listed, I intended to collect their protection status for each of the three endangered species lists and to collect information about their population.

## How I scraped the site

###### Scraping the URLs

After importing the necessary modules, including beautifulsoup, I created the function `get_urls_from_single_page(animal_url)`, which scraped the partial URL from every animal page on defenders.org/wildlife and wrote it to a list.

###### Scraping information from each page

I used the function `scrape_one_animal(gator_url)` to scrape the information from the protection status table and text from the population section and write it to a list.

###### Writing to the csv

I used the function `write_csv(url_list)` to write the information from each page to a csv file. I used a for loop to run each URL in `scrape_one_animal(gator_url)`.

## Challenges I faced

The biggest issue with this project was scraping the text from the Protection Status tables. Most tables had three columns, but some had two or even one, and some didn't even have a table at all. To account for the page having no tables, I used a try/except statement that wrote 'Not listed' for all three categories when the page had no table. I used a series of if and elif statements to account for each possible variation of table sizes. It was a clunky method, but it was effective for this webpage.
