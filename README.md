# Actor - App Store Scraper

## App Store scraper

Since Apple Store doesn't provide a good and valid API, this actor should help you to retrieve data from it.

The App Store data scraper supports the following features:

-   Search any keyword - You can search any keyword you would like to have and get the results

-   Scrape and media types - Scrape any type of media type that you need to get it from Apple Store

-   Scrape iTunes or App Store URLs - Get any iTunes or App Store URLs from their detail page.

-   Scrape publishers - You can gather intelligence from your rivals by gather the information from them

-   Scrape by filters - Media type, country or keyword. You can customize the results

-   Lookup by multiple ids - If you need to scrape multiple media, or multiple competitors you can retrieve them at onces.

## Bugs, fixes, updates and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/tugkan/appstore-scraper/issues).

## Setup & Usage

You can see how this actor works these videos:

### Using Search

[![Apify - XXXXX Scraper - Using Search](https://img.youtube.com/vi/7rpRBlIE--o/0.jpg)](https://www.youtube.com/watch?v=7rpRBlIE--o)

You can check the output of this example [here](https://api.apify.com/v2/datasets/AVTdGvcS2iOjDgAaV/items?clean=true&format=json).

### Using Start URLs

[![Apify - XXXXX Scraper - Using Start URLs](https://img.youtube.com/vi/ProePJ_1pwA/0.jpg)](https://www.youtube.com/watch?v=ProePJ_1pwA)

You can check the output of this example [here](https://api.apify.com/v2/datasets/yiZ9wm15WMTdmdH8L/items?clean=true&format=json).

## Input Parameters

The input of this scraper should be JSON containing the list of pages on XXXXX that should be visited. Required fields are:

| Field                | Type    | Description                                                                                                                                                                                                    |
| -------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| term               | String  |  Keyword that you want to search on App Store.                                                                                                                                                       |
| country       | String (Enum) | Country of the App Store that you'd like to scrape on. |
| mediaType            | Array   |  Media Type of the assets that you will get from the App Store                                                                                                        |
| mode              | String (Enum) | Mode of the actor. It can be "search" or "lookup".                                                          |
| startUrls            | Array   | (optional) List of Apple Store URLs. You should only provide detail URLs from iTunes or App Store                                                                                                                 |
| maxItems             | Integer | (optional) You can limit scraped products. This should be useful when you search through the big subcategories.                                                                                                |
| proxy                | Object  | Proxy configuration                                                                                                                                                                                            |
| customMapFunction | String  | (optional) Function that takes each objects handle as argument and returns object with executing the function                                                                                                                     |

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Compute Unit Consumption

The actor optimized to run blazing fast and scrape many as listings as possible. Therefore, it forefronts all listing detail requests. If actor doesn't block very often it'll scrape 100 listings in 2 minutes with ~0.01-0.02 compute units.

### App Store Scraper Input example

```json
{
  "startUrls":[
    "https://itunes.apple.com/us/movie/inception/id400763833",
    "https://apps.apple.com/us/app/angry-birds-2/id880047117"
  ],
  "term": "game dev",
  "country": "us",
  "mediaType": "all",
  "mode": "search",
  "maxItems":3
}


```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with failure state and output an explanation of what is wrong.

## App Store Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any languague (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this XXXXX actor.

## Scraped App Store Media

The structure of each item that you'll receive from App Store looks like this:

### Item Detail

```json
{
  "wrapperType": "track",
  "kind": "podcast",
  "collectionId": 1043547750,
  "trackId": 1043547750,
  "artistName": "Game Dev Unchained",
  "collectionName": "Game Dev Unchained",
  "trackName": "Game Dev Unchained",
  "collectionCensoredName": "Game Dev Unchained",
  "trackCensoredName": "Game Dev Unchained",
  "collectionViewUrl": "https://podcasts.apple.com/us/podcast/game-dev-unchained/id1043547750?uo=4",
  "feedUrl": "https://anchor.fm/s/651ae57c/podcast/rss",
  "trackViewUrl": "https://podcasts.apple.com/us/podcast/game-dev-unchained/id1043547750?uo=4",
  "artworkUrl30": "https://is5-ssl.mzstatic.com/image/thumb/Podcasts125/v4/3e/ea/04/3eea0406-7b9f-30f6-c626-6b9a4cef5597/mza_16385274979335913443.jpg/30x30bb.jpg",
  "artworkUrl60": "https://is5-ssl.mzstatic.com/image/thumb/Podcasts125/v4/3e/ea/04/3eea0406-7b9f-30f6-c626-6b9a4cef5597/mza_16385274979335913443.jpg/60x60bb.jpg",
  "artworkUrl100": "https://is5-ssl.mzstatic.com/image/thumb/Podcasts125/v4/3e/ea/04/3eea0406-7b9f-30f6-c626-6b9a4cef5597/mza_16385274979335913443.jpg/100x100bb.jpg",
  "collectionPrice": 0,
  "trackPrice": 0,
  "trackRentalPrice": 0,
  "collectionHdPrice": 0,
  "trackHdPrice": 0,
  "trackHdRentalPrice": 0,
  "releaseDate": "2021-11-02T23:11:00Z",
  "collectionExplicitness": "cleaned",
  "trackExplicitness": "cleaned",
  "trackCount": 332,
  "country": "USA",
  "currency": "USD",
  "primaryGenreName": "Video Games",
  "contentAdvisoryRating": "Clean",
  "artworkUrl600": "https://is5-ssl.mzstatic.com/image/thumb/Podcasts125/v4/3e/ea/04/3eea0406-7b9f-30f6-c626-6b9a4cef5597/mza_16385274979335913443.jpg/600x600bb.jpg",
  "genreIds": [
    "1509",
    "26",
    "1502"
  ],
  "genres": [
    "Video Games",
    "Podcasts",
    "Leisure"
  ]
}
```
