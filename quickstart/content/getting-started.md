---
title: "Getting Started: Setting Up A Postgres Server With Your Shopify Data"
date: 2018-03-12T08:48:34-04:00
draft: false
---

The first step 

## Postgres
PostgreSQL is an open source object-relational database system. It's extremely powerful. If you're used to Excel, you'll be blown away. 


This is the about page.

## What You'll Need

Even if you're not a developer, it's still very easy to setup a Postgres server and connect your Shopify data to it. Here is what you'll need to get started:

* [Shopify Store](https://www.shopify.com/?ref=hodi-inc&utm_campaign=Postgres%20to%20Shopify&utm_content=Getting%20Started&utm_source=Postgres%20to%20Shopify%20Site "Shopify")
* [Heroku Account](https://www.heroku.com/ "Heroku")
* [StitchData Account](http://stitchdata.com/ "Stitchdata")
* A Postgres Client (I recommend [Postico](https://eggerapps.at/postico/ "Postico"))

## Set-Up
### Shopify
Hopefully you already have a Shopify store, as performing data analysis without any data isn't very fun. If not, you can setup one [here](https://www.shopify.com/?ref=hodi-inc&utm_campaign=Postgres%20to%20Shopify&utm_content=Getting%20Started&utm_source=Postgres%20to%20Shopify%20Site "Shopify"). To reiterate, you'll need some orders (data).

### Heroku
Heroku is a "Platorm as a Service", they enable developers to build and run applications in the cloud. We're going to use Heroku's "Database as a Service" to setup our Postgres server. 

1. After you create your account, you'll be directed to create a new app within Heroku. Complete the form and select "Create app" (you do not need to *Add to pipeline*).
2. Once in your app's admin, you'll see a section titled "Installed add-ons". Click "Configure Add-ons" and begin typing "Postgres" into the search bar. Heroku Postgres will appear.
3. You'll then be shown a page to create your Postgres datadase. **Select Hobby Basic - $9/mth.** Depending on the size of your Shopify store, you'll need at a minimum of 100,000 rows. 
4. Congratulations! Your Postgres server was just created. Now navigate to Settings and click "View Credentials...". You can keep this window open, we'll need this info in a few minutes.

### StitchData
[StitchData](http://stitchdata.com/ "Stitchdata") is a cloud ETL system (ETL = ). In our instance, StitchData will be used to extract data from your Shopify store to your Postgres server. 
