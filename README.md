#Data-Representation-and-Querying-Project-2015

##Gareth Lynskey

##County Galway Libraries

###Introduction
This project provides information and the documentation for the datasets of Galway Libraries throughout the County, which i found available online at [https://data.gov.ie/dataset/county-galway-libraries](https://data.gov.ie/dataset/county-galway-libraries).
I would imagine the target user(s) for this app would be regular goers of the library such as Adults and Students. 

The idea of this app is to make it easy and convenient for users to find a library nearby around the county when they aren't close to their own local library.

###About
I downloaded the dataset from [https://data.gov.ie/dataset/county-galway-libraries](https://data.gov.ie/dataset/county-galway-libraries) in a Comma Seperated Value format(.csv). The file has 30 rows which contain the names of the individual Libraries and 24 columns which contain the information of each Library.I have decided to use 17 of the 24 columns and to leave out the rest of the columns as they don't contain relevent information needed for the app.

###Column Values

These are the 16 column values that I've selected from the 24.

Field | Value | Field | Value
------|---------|---------|-----------
**Name** | Library Name (text) | **Longitude** | Library Longitude (number)
**Address 1** | Library Location text) | **Opening Hours Monday** | Opening hours (number)
**Address 2** | Library Location (Text) | **Opening Hours Tuesday** | Opening hours (number)
**Town** | Library Location (text) | **Opening Hours Wednesday** | Opening hours (number)
**Phone** | Library Number (number) | **Opening Hours Thursday** | Opening hours (number)
**Email** | Library Email (text) | **Opening Hours Friday** | Opening hours (number)
**Website** | Library Website (text) | **Opening Hours Saturday** | Opening hours (number)
**Latitude** | Library Latitude (number) | **Opening Hours Sunday** | Opening hours (number)

###App Design

> #####Main Page

The App will have a main page with a listing of all the library name's in County Galway. When the user clicks the name of a library, it will link you to the page with all the information of that library.

> #####Single Library Page's Information

These page's will consist of each libraries information such as the data below:

> * Name (text)
> * Address 1 (text)
> * Address 2 (text)
> * Town (text)
> * Phone (number)
> * Email (text)
> * Website (text)
> * Latitude (number)
> * Longitude (number)
> * Opening Hours Monday
> * Opening Hours Tuesday
> * Opening Hours Wednesday
> * Opening Hours Thursday
> * Opening Hours Friday
> * Opening Hours Saturday
> * Opening Hours Sunday

I was also thinking, at the bottom of each page it could have a google maps live image with the latitude and longitude of each library in order to actually put the latitude and longitude to use as it's rarely used by the general user in todays world.
