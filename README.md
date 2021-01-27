# Amazon Scraper: Webscraper for Amazon Products

This scraper you can use without any programming skills. By using a Docker container, you can also integrate it into an existing application ecosystem.

pl

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

```

## Legal Issues

- Please check [Amazon's robots.txt](https://www.amazon.com/robots.txt) and the [Terms of Service Usage](https://www.amazon.com/gp/help/customer/display.html?nodeId=202140280) regularly to ensure what you allowed to do with the data
- Never use the data against Amazon e.g. by building competive services etc.
- Don't use the scraper to earn money with data in way it damages Amazon
