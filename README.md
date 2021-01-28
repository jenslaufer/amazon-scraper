# Amazon Scraper: Webscraper for Amazon Products

This scraper saves you time as it's ready to use without complicated installation. It's for everybody from non-programmers to professionals who want to integrate the scraper into their existing application ecosystem.

You can perform product scraping based on a search query through a REST API or a Web UI. The results you can dowload as CSV or JSON for further analysis.

These features are retrieved:

- Title
- ASIN
- URL
- Categories
- Average Rating
- Number of Ratings
- Price
- Best Seller Rank
- Dimensions
- Weight

## Installation

**1. Install Docker**

The scraper is packed into a Docker container, to minimise the setup. You don't need to be a docker expert to get the scraper working.

[Install Docker on your machine](https://docs.docker.com/get-docker/)

**2. Register for a Scraper API key**

To use the a scraper you need a service that sends requests through rotating proxies to avoid getting blocked by sending too many requests from one IP address.

The scraper uses Scraper API.

[Register for a Scraper API key](https://www.scraperapi.com?fpr=scrapers)

Go to the dashboard to copy the API key. You need it for your scraping setup.

**3. Get the docker-compose.yml to run the application**

Get the docker-compose.yml to run the application by copying the code fragment and saving into a file named
docker-compose.yml or by cloning the whole project.

```yaml
version: '3.0'

services:
  amazon-scraper:
    image: jenslaufer/amazon-scraper:latest
    container_name: amazon-scraper
    ports:
      - 8085:5000
    environment:
      - MONGODB_URI=mongodb://amazon-db/amazon
      - SCRAPER_API_KEY=<YOUR-SCRAPER-API-KEÝ>
    depends_on:
      - amazon-db

  amazon-scraper-webapp:
    image: jenslaufer/scraper-webapp:latest
    container_name: amazon-scraper-webapp
    ports:
      - 8089:8080
    depends_on:
      - amazon-scraper-webapp

  amazon-db:
    image: mongo:4
    container_name: amazon-db
    ports:
      - 27017 #27017:27017 in case you want to access the mongodb from outsite
```

**4. Insert your Scraper API key**

Replace <YOUR-SCRAPER-API-KEÝ> with your Scraper API key which you can get from their dashboard.

**5. Start scraper application**

Start the application by executing the docker-compose command in the directory where your docker-compose file is located.

```shell
docker-compose -d up
```

Compose fetches all containers which are needed to start the application. This takes a while and is depending on your internet connection.

**6. Happy scraping**

Once all containers are up and running get the following

[http://localhost:8089](http://localhost:8089)

Type in the keyword you want to scrape Amazon products for. You are able to dowload the results as CSV/JSON.

## Legal Issues

- Please check [Amazon's robots.txt](https://www.amazon.com/robots.txt) and the [Terms of Service Usage](https://www.amazon.com/gp/help/customer/display.html?nodeId=202140280) regularly to ensure what you allowed to do with the data
- Never use the data against Amazon e.g. by building competive services etc.
- Don't use the scraper to earn money with data in way it damages Amazon
