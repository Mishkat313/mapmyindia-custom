![MapmyIndia APIs](https://www.mapmyindia.com/api/img/mapmyindia-api.png)
# MapmyIndia Aeon Merchant Nearby API

**MapmyIndia Custom API for Aeon Credit**

Powered with India's most comprehensive and robust mapping functionalities. This API can be used to extract the Aeon Merchant outlets near a position on map referenced by a geo-coordinate (lat-long pair) within a certain defined radius, by a specific product type in a paginated
response.



## Document Version History

| Version | Last Updated | Author |
| ---- | ---- | ---- |
| 0.0.1 | 25 December 2020 | MapmyIndia API Team ([MH](https://github.com/mishkat313)) |



## Introduction

The custom API offered by MapmyIndia for Aeon Credit is based on Nearby API. It enables to search nearby Aeon Merchant outlets for a given geographical coordinates (pair of lat-long ) on map within a defined radius, by a specific product categiry type in a paginated response.  

## Security Type
This APIs follow OAuth2 based security. To know more on how to create your authorization tokens, please use our authorization token URL. More details available [here](https://www.mapmyindia.com/api/advanced-maps/doc/authentication-api.php)

## Request Headers
The API leverages OAuth 2.0 based security. Hence, the developer would need to send a request for access token using their client_id and client_secret to the OAuth API. Once validated from the OAuth API, the access_token and the token_type need to be sent as Authorization header with the value: “{token_type} {access_token}”.

## Input Method

GET

## Input URL
The API URL should be of the following construct –
```html
https://app.mapmyindia.com/AeonNearByAPI/getMerchantData?
```

## Response Type
Output format will be JSON.

## Request Parameters
The following input parameters will be supported in the Aeon Merchant Nearby API request
1. Mandatory Parameters:

    - **`refLocation`** (string): The geo-coordinate (lat,long) of the location near which outlets are
being searched.

2. Optional Parameters
    - **`radius`** (integer): Provides range of distance to search (default=1000,min=100,max=10000).
    - **`productType`** (string): Type of product user need to search.
    - **`itemCount`** (integer): Provides number of data per page.
Max. 20 items per page.
    - **`page`** (integer): Provides number of page to provide results from.

## Response Parameters
1. **code**: Status code of the response.
2. **message**:
3. **results**: array of results, each consisting of the following parameters
    - **`distance`** (integer): locality ID of the place which is referred by the coordinates.
    - **`productType`** (string): The type of product.
    - **`email`** (string): email of the outlet.
    - **`latitude`** (double): Latitude of the outlet.
    - **`longitude`** (double): Longitude of the outlet.
    - **`contactNo`** (string): Phone number of the outlet.
    - **`orderIndex`** (integer): Sort order of the outlet.
    - **`placeAddress`** (string): Address of the outlet.
    - **`placeName`** (string): Name of the outlet.
    - **`area`** (string): Area of the outlet.
    - **`pincode`** (string): PIN of the outlet.
4. **pageInfo**: Page information for the response.
    - **`totalPages`** (integer): Total pages applicable in the response.
    - **`dataSize`** (integer): Total results applicable in the response.

## Response Codes {as HTTP response code}


- 200: To denote a successful API call.
- 201: No result found for searched query (Failure).
- 400: Bad Request, User made an error while creating a valid request.
- 412: Precondition Failed, i.e. Mandatory parameter is missing
- 500: Internal Server Error, the request caused an error in our systems.
- 503: Service Unavailable, during our maintenance break or server down-times.

## Performance
The Aeon Nearby API must respond within 300 ms under all circumstances.

## Sample Input
http://app.mapmyindia.com/AeonNearByAPI_v1/getMerchantData?refLocation=19.1193831,72.8859725&radius=10000&productType=TwoWheeler&itemCount=10&page=1
## Sample Response

```
{
    "code": 200,
    "message": "SUCCESS",
    "results": [
        {
            "distance": "678.93",
            "productType": "TwoWheeler",
            "email": "babauto2017@gmail.com",
            "latitude": 19.116971,
            "longitude": 72.880036,
            "contactNo": "9167114815",
            "orderIndex": "1",
            "placeAddress": "SHOP NO.5, EDWARD SOARES HOUSE, H N 119, RAUTHERI MAROL VILLAGE M M RD ANDHERI EAST, MUMBAI-400059",
            "placeName": "BABA AUTO - ANDHERI (EAST)",
            "area": "ANDHERI EAST",
            "pincode": "400059"
        },
        {
            "distance": "1304.56",
            "productType": "TwoWheeler",
            "email": "GOODLUCKMOTORS513@GMAIL.COM",
            "latitude": 19.1302,
            "longitude": 72.890781,
            "contactNo": "7045291392",
            "orderIndex": "2",
            "placeAddress": "GALANO.5,TIWARICHAWL,MILINDNAGARJ.V.LINKROAD,OPP.L&T,MUMBAI-400072",
            "placeName": "GOODLUCKMOTORS-POWAI",
            "area": "POWAI"
        },
        {
            "distance": "1643.86",
            "productType": "TwoWheeler",
            "email": "arunhmaurya@gmail.com",
            "latitude": 19.110284,
            "longitude": 72.873641,
            "contactNo": "9324490019",
            "orderIndex": "3",
            "placeAddress": "NEXT TO ROYAL PETROL, PUMP, NR.HOTEL LEELA,A.K ROAD, MAROL, ANDHERI (EAST), MUMBAI-400059",
            "placeName": "FRIENDS AUTO - ANDHERI (EAST)",
            "area": "ANDHERI EAST",
            "pincode": "400059"
        },
        {
            "distance": "1682.77",
            "productType": "TwoWheeler",
            "email": "a.k.motors2407@gmail.com",
            "latitude": 19.10431562,
            "longitude": 72.8844784,
            "contactNo": "8691966000",
            "orderIndex": "4",
            "placeAddress": "SHOPNO.2,KOHINOORCOMPOUND,NEAR21HONDAOPP,B.M.CSCHOOL,A.G.LINKROAD,SAKINAKA,MUMBAI-400072",
            "placeName": "A.K.MOTORS-SAKINAKA",
            "area": "SAKINAKA",
            "pincode": "400072"
        },
        {
            "distance": "1788.90",
            "productType": "TwoWheeler",
            "email": "LUCKYAUTO7861@GMAIL.COM",
            "latitude": 19.1056,
            "longitude": 72.894754,
            "contactNo": "9821816338",
            "orderIndex": "5",
            "placeAddress": "GALA NO. 5, B. N. D'SOUZA COMPOUND, NEAR LUCKY HOTEL, KHERANI ROAD, SAKINAKA, MUMBAI - 400072",
            "placeName": "LUCKY MOTORS - SAKINAKA",
            "area": "SAKINAKA"
        },
        {
            "distance": "2068.60",
            "productType": "TwoWheeler",
            "email": "DHIRAJPANDEY1@YAHOO.COM",
            "latitude": 19.1013,
            "longitude": 72.890596,
            "contactNo": "9022782829",
            "orderIndex": "6",
            "placeAddress": "SHOPNO.5,DHANLAXMIBUILDING,GHATKOPAR-ANDHERILINKROAD,NEARBMCSCHOOL,SAKINAKA,MUMBAI-400072",
            "placeName": "CITYMOTORS-SAKINAKA",
            "area": "SAKINAKA",
            "pincode": "400072"
        },
        {
            "distance": "2245.18",
            "productType": "TwoWheeler",
            "email": "dhirajpandey1@yahoo.com",
            "latitude": 19.1000382,
            "longitude": 72.89209498,
            "contactNo": "9022782829",
            "orderIndex": "7",
            "placeAddress": "SHOPNO.5,DHANLAXMIBUILDING,GHATKOPAR-ANDHERILINKROAD,NEARBMCSCHOOL,SAKINAKA,MUMBAI-400072",
            "placeName": "CITYMOTORS-SAKINAKA",
            "area": "SAKINAKA",
            "pincode": "400072"
        },
        {
            "distance": "2374.56",
            "productType": "TwoWheeler",
            "email": "autodenindia@gmail.com",
            "latitude": 19.12511239,
            "longitude": 72.8641991,
            "contactNo": "9892633316",
            "orderIndex": "8",
            "placeAddress": "SHOP NO. 1 , RAJENDRA SINGH SETHI COMPOUND, OLD HEK COMPOUND, MAHAKALI CAVES ROAD, OPP.INDIAN BANK, ANDHERI (EAST) MUMBAI -400093",
            "placeName": "LUCKY MOTORS - SAKI NAKA",
            "area": "SAKI NAKA",
            "pincode": "400093"
        },
        {
            "distance": "2381.53",
            "productType": "TwoWheeler",
            "email": "CHOUDHARYMOTORS33@GMAIL.COM",
            "latitude": 19.0989,
            "longitude": 72.892595,
            "contactNo": "8655465500",
            "orderIndex": "9",
            "placeAddress": "SHOPNO.2,DHANLAXMI,MOHILIVILLAGE,ASALPHA-GHATKOPAR,LINKROAD,SAKINAKA,MUMBAI-400072",
            "placeName": "CHOUDHARYMOTORS-SAKINAKA",
            "area": "SAKINAKA",
            "pincode": "400072"
        },
        {
            "distance": "2434.40",
            "productType": "TwoWheeler",
            "email": "motors@kalchuri group.com",
            "latitude": 19.09834917,
            "longitude": 72.89239967,
            "contactNo": "8080888001",
            "orderIndex": "10",
            "placeAddress": "SHOP NO. 2, GUPTA NIWAS, OPP. DHANLAXMI BLDG, A.G. LINK ROAD, SAKINAKA, MUMBAI - 400072",
            "placeName": "KALCHURI MOTORS - SAKINAKA",
            "area": "SAKINAKA",
            "pincode": "400072"
        }
    ],
    "pageInfo": {
        "totalPages": 16,
        "dataSize": 158
    }
}
```




That's All !


For any queries and support, please contact: 

[<img src="https://www.mapmyindia.com/images/logo.png" height="40"/> </p>](https://www.mapmyindia.com/api)
Email us at [apisupport@mapmyindia.com](mailto:apisupport@mapmyindia.com)


![](https://www.mapmyindia.com/api/img/icons/support.png)
[Support](https://www.mapmyindia.com/api/index.php#f_cont)
Need support? contact us!

<br></br>

[<p align="center"> <img src="https://www.mapmyindia.com/api/img/icons/stack-overflow.png"/> ](https://stackoverflow.com/questions/tagged/mapmyindia-api)[![](https://www.mapmyindia.com/api/img/icons/blog.png)](http://www.mapmyindia.com/blog/)[![](https://www.mapmyindia.com/api/img/icons/gethub.png)](https://github.com/MapmyIndia)[<img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/API-Team/npm-logo.one-third%5B1%5D.png" height="40"/> </p>](https://www.npmjs.com/org/mapmyindia) 



[<p align="center"> <img src="https://www.mapmyindia.com/june-newsletter/icon4.png"/> ](https://www.facebook.com/MapmyIndia)[![](https://www.mapmyindia.com/june-newsletter/icon2.png)](https://twitter.com/MapmyIndia)[![](https://www.mapmyindia.com/newsletter/2017/aug/llinkedin.png)](https://www.linkedin.com/company/mapmyindia)[![](https://www.mapmyindia.com/june-newsletter/icon3.png)](https://www.youtube.com/user/MapmyIndia/)




<div align="center">@ Copyright 2020 CE Info Systems Pvt. Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://www.mapmyindia.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://www.mapmyindia.com/about/privacy-policy">Privacy Policy</a> | <a href="https://www.mapmyindia.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://www.mapmyindia.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://www.mapmyindia.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>