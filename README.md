# web-scraping-with-python-using-scrapy

>## To create a scrapy project we need the command:
>#### scrapy startprojct [project_name]



## First Project
> Scrap the website worldometer
scrapy genspider countries www.worldometers.info/world-population/population-by-country


### <i>Section 04 lesson 01</i>
```python
def parse(self, response):

    # gets all the countries 
    countries = response.xpath("//td/a")

    #for each country get the country name and country link
    for country in countries:
        name = country.xpath(".//text()").get()
        link = country.xpath(".//@href").get()

        yield {
            'country_name': name,
            'country_link': link
        }
```
