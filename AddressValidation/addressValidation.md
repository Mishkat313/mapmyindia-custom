[<img src="https://about.mappls.com/api/img/mapmyindia-api.png" height="40"/> </p>](https://about.mappls.com/api/)

# Mappls Address Validation Plugin

**Easy To Integrate Maps & Location APIs & SDKs For Web & Mobile Applications**

Powered with India's most comprehensive and robust mapping functionalities.

## Introduction
Address verification service will help to quickly identify the match level of the GPS location against the provided address through address comparison techniques. It will provide the details with the address component to which extent the address and geo-location resembles  to each other 

Important components:
1. The text addresses will be used to determine the location.
2. The coordinates of the location required to verify against the text address.

## Input parameters

1. **`address`**: Input the text address against which the coordinate pair has to be validated.
2. **`lat`**: latitude of the location of the provided address.
3. **`lng`**: longitude of the location of the provided address.

## Response Parameters
**Mandatory parameters**

1. **`coordinateMatchLvl`** : Match level of input address versus coordinate address. e.g state, city, district etc. 
2. **`isMatch`**: boolean. Returns Match or Not Match. Match, where coordinateMatchLvl matches to addressMatchLvl 
3. **`matchResolutionDesc`**: Describes the coordinates vs address matching resolution for examples

    for Match: “Both address and coordinate pairs are resolved and matched upto subdistrict level. Address is resolved upto subdistrict level. Provided coordinate pairs are falling in that same subdistrict. Since coordinates are matching address at the most detailed level at which address was geocoded, hence this IS A MATCH AT BEST LEVEL.”

    For Not Match: “AddressAddresss is resolved upto subdistrict level. But provided coordinate pairs are not falling in that same subdistrict. The address and coordinates are matching at state level. Since coordinates are not matching address at the most detailed level at which address was geocoded, hence this is NOT A MATCH AT BEST LEVEL. It is a match at STATE level. Please reverify the address or coordinates.”

4. **`parsedAddress`** : returns matched formatted parsed address with input address. 
5. **`radialProximity`**: returns radial proximity in meters in case identified coordinates address are of POI or house Number/Name from the coordinates provided and identified matched address.
