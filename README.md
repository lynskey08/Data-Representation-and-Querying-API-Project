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

###Api Design

> #####Main Page

The Api will have a main page with a listing of all the library name's in County Galway in a dropdown button called Libraries. When the user clicks the name of a library, it will link you to the page with all the information of that library.

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
> * Opening Hours Monday (number)
> * Opening Hours Tuesday (number)
> * Opening Hours Wednesday (number)
> * Opening Hours Thursday (number)
> * Opening Hours Friday (number)
> * Opening Hours Saturday (number)
> * Opening Hours Sunday (number)

I was also thinking, at the bottom of each page it could have a google maps live image with the latitude and longitude of each library in order to actually put the latitude and longitude to use as it's rarely used by the general user in todays world.

> #####The following is an example responce from the dataset in JSON format.
```json
[
  {
        "Name": "WESTSIDE LIBRARY",
        "Address1": "SEAMUS QUIRKE ROAD",
        "Address2": "",
        "Town": "GALWAY City",
        "Phone": "+353 (0) 91 520616",
        "Email": "westside@galwaylibrary.ie",
        "Website": "http://www.galway.ie/en/Services/Library/",
        "WGS84Latitude": "53.27739",
        "WGS84Longitude": "-9.07447",
        "Opening_Hours_Monday": "Closed",
        "Opening_Hours_Tuesday": "11.00am to 8.00pm",
        "Opening_Hours_Wednesday": "1.00am to 8.00pm",
        "Opening_Hours_Thursday": "11.00am to 5.00pm",
        "Opening_Hours_Friday": "11.00am to 5.00pm",
        "Opening_Hours_Saturday": "11.00am to 1.00pm and 2.00pm to 5.00pm",
        "Opening_Hours_Sunday": "Closed",
    },
]
```

###Api's Uniform Resource Locator's



**Creating an Admin using POST method**

The admin will need to be able to update,delete and query the dataset using HTTP methods.

```json
{
   "name" : "username",
   "full-name" : "name",
   "email" : "admin@example.ie",
   "password" : {
      "value" : "my_password"
   },
   "active" : true
}
```

#####Get Method

The HTTP GET request method is designed to retrieve information from the server.
You can receive a list of all the libraries in County Galway with the HTTP GET method, by using the following URL: *http://galway.ie/en/Services/Library/(all)*

By typing "all" without the brackets, after "../Library/ will return a list of all the libraries in County Galway.
The GET method retrieves data from a web server by specifying parameters in the URL of the request.
```json
[
  {
        "Name": "WESTSIDE LIBRARY",
        "Address1": "SEAMUS QUIRKE ROAD",
        "Address2": "",
        "Town": "GALWAY City",
        "Phone": "+353 (0) 91 520616",
        "Email": "westside@galwaylibrary.ie",
        "Website": "http://www.galway.ie/en/Services/Library/",
        "WGS84Latitude": "53.27739",
        "WGS84Longitude": "-9.07447",
        "Opening_Hours_Monday": "Closed",
        "Opening_Hours_Tuesday": "11.00am to 8.00pm",
        "Opening_Hours_Wednesday": "1.00am to 8.00pm",
        "Opening_Hours_Thursday": "11.00am to 5.00pm",
        "Opening_Hours_Friday": "11.00am to 5.00pm",
        "Opening_Hours_Saturday": "11.00am to 1.00pm and 2.00pm to 5.00pm",
        "Opening_Hours_Sunday": "Closed",
    },
  {....},
  {....},
  {....}
]
```

To request a library by name you can use:
*http://galway.ie/en/Services/Library/(name)
Where you replace (name) with the name of a place 
such as (Tuam) like so:
*http://galway.ie/en/Services/Library/TUAM

```json
[
    {
        "Name": "TUAM LIBRARY",
        "Address1": "HIGH STREET",
        "Address2": "null",
        "Town": "TUAM",
        "Phone": "+353 (0) 93 24287",
        "Email": "tuam@galwaylibrary.ie",
        "Website": "http://www.galway.ie/en/Services/Library/Tuam",
        "WGS84Latitude": "53.514413",
        "WGS84Longitude": "-8.854173",
        "Opening_Hours_Monday": "Closed",
        "Opening_Hours_Tuesday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Wednesday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Thursday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Friday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Saturday": "10:30 to 13:00 and 14:00 to 17:00 (Closed on Bank Holiday Weekends)",
        "Opening_Hours_Saturday": "Closed"
    },
]
```

#####POST Method

A POST request is used to send data to the server to be processed.For example, customer information, file upload, etc.

**HTTP request using POST method by admin**

POST *http://admin/password@galway.ie/en/Services/Library/Tuam/?Email=tuamlibrary@galway.ie*

Before update:
```json
[
    {
        "Name": "TUAM LIBRARY",
        "Address1": "HIGH STREET",
        "Address2": "null",
        "Town": "TUAM",
        "Phone": "+353 (0) 93 24287",
        "Email": "tuam@galwaylibrary.ie",
        "Website": "http://www.galway.ie/en/Services/Library/Tuam",
        "WGS84Latitude": "53.514413",
        "WGS84Longitude": "-8.854173",
        "Opening_Hours_Monday": "Closed",
        "Opening_Hours_Tuesday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Wednesday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Thursday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Friday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Saturday": "10:30 to 13:00 and 14:00 to 17:00 (Closed on Bank Holiday Weekends)",
        "Opening_Hours_Saturday": "Closed"
    },
]
```

After update:
```json
[
    {
        "Name": "TUAM LIBRARY",
        "Address1": "HIGH STREET",
        "Address2": "null",
        "Town": "TUAM",
        "Phone": "+353 (0)93 24287",
        "Email": "tuamlibrary@galway.ie",
        "Website": "http://www.galway.ie/en/Services/Library/Tuam",
        "WGS84Latitude": "53.514413",
        "WGS84Longitude": "-8.854173",
        "Opening_Hours_Monday": "Closed",
        "Opening_Hours_Tuesday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Wednesday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Thursday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Friday": "10:30 to 13:00 and 14:00 to 17:00",
        "Opening_Hours_Saturday": "10:30 to 13:00 and 14:00 to 17:00 (Closed on Bank Holiday Weekends)",
        "Opening_Hours_Saturday": "Closed"
    },
]
```




