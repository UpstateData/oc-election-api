## Onondaga County Polling Location API

Onondaga County doesn't provide easy access to information on polling locations. You can either [read a PDF document](http://www.ongov.net/elections/documents/2015WEBSITEPOLLINGPLACELIST.pdf) to get polling locations, or use an outdated and not very user friendly [web application](http://vic.ntsdata.com/onondagaboe/pollingplacelookup.aspx).

I built this very simple API in the hopes that it would encourage people to think about the different ways that polling location information might be used. I also hope to show county officials that there are limitless possibilities for engaging people and enhancing the quality of services and information we get from government if they [release open data](http://opendata.guide/).

Much of the information provided by the existing County web application can also be obtained through the [Google Civic Information API](https://developers.google.com/civic-information/?hl=en). However, a polling location API specific to Onondaga County can provide more detailed, more accurate, and more recently updated information for voters. It can also act as an invitation to local technologists and software developers to build new ways to explore this important data and help ensure more people find their way to the polls on Election Day.

## Example usage

Request

```
curl -s -X POST -H 'Content-type: application/json' \
-H 'Accept: application/json' \
-d '{"house_num": 4738, "street_name": "Lawsher Drive", "zip": 13215}' \
http://apis.opensyracuse.org/elections/ \
| jq .
```

Response 

```json
{
  "otherDistrict4": null,
  "otherDistrict3": null,
  "otherDistrict2": "11th County Legislative District",
  "otherDistrict1": null,
  "assembly": "128th Assembly District",
  "senate": "50th Senatorial District",
  "name": "ST MICHAEL & ST PETER CHURCH",
  "fullAddress": "(BASEMENT) 4791 W SENECA TPKE SYRACUSE NY 13215",
  "disabled": "This Polling Place is Accessible to the disabled",
  "town": "Onondaga",
  "ward": "000",
  "district": "003",
  "school": null,
  "congress": "24th Congressional District"
}
```