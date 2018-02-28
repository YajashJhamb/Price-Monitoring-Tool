# Price-Monitoring-Tool
This is a simple price monitor built with Scrapy and Scrapy Cloud.

It is basically a Scrapy project with one spider for each online retailer that we want to monitor prices from. 
In addition to the spiders, there's a Python Script that is scheduled to run periodically on Scrapy Cloud, checking whether the latest 
prices are the best ones in a given time span. If so, the monitor sends an email alerting you about the price drops.

## Install and Running
Installing and Running
Clone this repo:

 $ git clone git@github.com:stummjr/scrapy_price_monitor.git

Enter the folder and install the project dependencies:
```
 $ cd scrapy_price_monitor
 ```
 ```
 #$ pip install -r requirements.txt
```
Create a free forever account on Scrapy Cloud: https://app.scrapinghub.com/account/signup/.

Create a Scrapy project on Scrapy Cloud and copy the project id from the project URL.

Install Scrapinghub command line tool (shub):
```
 $ pip install shub
```
Authenticate using your Scrapinghub API key:
```
 $ shub login
```
Finally, deploy the local project to your Scrapy Cloud project:
```
 $ shub deploy <your_project_id_here>
```
This video also explains how to deploy a Scrapy project to Scrapy Cloud: https://youtu.be/JYch0zRmcgU


## How to Schedule on Scrapy Cloud

After you have deployed the project to Scrapy Cloud, it's time to schedule its execution on Scrapy Cloud.

This project has two main components:

the spiders that collect prices from the retailers' websites

the price monitor script that checks whether there's a new deal in the latest prices

You have to schedule both the spiders and the monitor to run periodically on Scrapy Cloud. It's a good idea to schedule all the spiders to run at the same time and schedule the monitor to run about 15 minutes after the spiders.

Take a look at this video to learn how to schedule periodic jobs on Scrapy Cloud: https://youtu.be/JYch0zRmcgU?t=1m51s
