[https://apify.com/epctex/appstore-scraper](https://apify.com/epctex/appstore-scraper?fpr=yhdrb)

# Actor - App Store Scraper

## App Store scraper

Since Apple Store doesn't provide a good and valid API, this actor should help you to retrieve data from it.

The App Store data scraper supports the following features:

-   Get reviews - Get reviews of anything from iTunes! No limits, extremely fast!

-   Search any keyword - You can search any keyword you would like to have and get the results

-   Scrape and media types - Scrape any type of media type that you need to get from the Apple Store

-   Scrape iTunes or App Store URLs - Get any iTunes or App Store URLs from their detail page.

-   Scrape publishers - You can gather intelligence from your rivals by gathering information from them

-   Scrape by filters - Media type, country, or keyword. You can customize the results

-   Lookup by multiple ids - If you need to scrape multiple media or multiple competitors you can retrieve them at once.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/appstore-scraper/issues).

## Input Parameters

The input of this scraper should be JSON containing the list of pages on the App Store that should be visited. Possible fields are:

- `term`: (Optional) (String) Keyword that you want to search on App Store.

- `startUrls`: (Optional) (Array) List of Apple Store URLs. You should only provide detailed URLs from iTunes or App Store.

- `country`: (Optional) (String) Country of the App Store that you'd like to scrape on.

- `mediaType`: (Optional) (String) Media Type of the assets that you will get from the App Store.

- `mode`: (Optional) (String) Mode of the actor. It can be "search" or "lookup".

- `includeReviews`: (Optional) (Boolean) If you want to include the reviews per each of the applications, you can enable this option. Please keep in mind that reviews will be retrieved in a paginated manner. Therefore the number of requests proportionally increases.

- `endPage`: (Optional) (Number) Final number of page that you want to scrape. The default is `Infinite`. This applies to all `search` requests and `startUrls` individually.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `customMapFunction`: (Optional) (String) Function that takes each object's handle as an argument and returns the object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

If you want to scrape a specific id or media, always use Lookup mode. Lookup mode is suggested for searching up specific values or assets on the App Store or iTunes. For example; if you want to search for the id of `400763833`, then select Lookup mode and enter `400763833` into the `Term` section.

On the other hand, if you want to search over specific keywords or filters, Search mode will do the job for you.

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape many listings as possible. Therefore, it forefronts all listing detail requests. If the actor doesn't block very often it'll scrape 100 listings in 2 minutes with ~0.01-0.02 compute units.

### App Store Scraper Input example

```json
{
    "startUrls": [
        "https://itunes.apple.com/us/movie/inception/id400763833",
        "https://apps.apple.com/us/app/angry-birds-2/id880047117"
    ],
    "term": "game dev",
    "country": "us",
    "mediaType": "all",
    "mode": "search",
    "includeReviews":true,
    "maxItems": 3
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## App Store Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Appstore actor.

## Scraped App Store Media

The structure of each item that you'll receive from the App Store looks like this:

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
    "genreIds": ["1509", "26", "1502"],
    "genres": ["Video Games", "Podcasts", "Leisure"],
    "reviews": [
        {
            "id": "9519350766",
            "userName": "ultrageoffe",
            "userUrl": "https://itunes.apple.com/us/reviews/id212958678",
            "version": "2.3",
            "score": 1,
            "title": "Ad nightmare",
            "text": "Ads every few seconds. Don’t waste your time",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9519118710",
            "userName": "blake42059",
            "userUrl": "https://itunes.apple.com/us/reviews/id1241179837",
            "version": "2.3",
            "score": 1,
            "title": "To many adds and pop ups trash game don’t recommend to anyone.",
            "text": "To many adds and pop ups trash game don’t recommend to anyone.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9518589385",
            "userName": "Skinny1K",
            "userUrl": "https://itunes.apple.com/us/reviews/id1339960005",
            "version": "2.3",
            "score": 1,
            "title": "Found a bug😂",
            "text": "The game stopped working before I could finish level 1",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9516124853",
            "userName": "Epictrollcreeper",
            "userUrl": "https://itunes.apple.com/us/reviews/id351259271",
            "version": "2.3",
            "score": 3,
            "title": "Rating",
            "text": "Good concept, too many ads.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9515904349",
            "userName": "ORION THA GREAT",
            "userUrl": "https://itunes.apple.com/us/reviews/id1400556177",
            "version": "2.3",
            "score": 1,
            "title": "No sound.",
            "text": "The app has no sound ? Why ?",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9515358167",
            "userName": "aj12ski",
            "userUrl": "https://itunes.apple.com/us/reviews/id1159671746",
            "version": "2.3",
            "score": 1,
            "title": "Not good",
            "text": "So many ads and it bothers you and says you gotta click on these little things that bring you to a obvious scam for a gift card. Also, pistons don’t all fire at the same time. Very bad game.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9512381960",
            "userName": "86spence",
            "userUrl": "https://itunes.apple.com/us/reviews/id889838843",
            "version": "2.3",
            "score": 5,
            "title": "I thought this would be bad but it’s way better than that",
            "text": "i genuinely think this game is fun!",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9512157356",
            "userName": "K.video",
            "userUrl": "https://itunes.apple.com/us/reviews/id1320845055",
            "version": "2.3",
            "score": 3,
            "title": "Wow",
            "text": "A fun game but to much ads",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9511169577",
            "userName": "bruh dis is broke",
            "userUrl": "https://itunes.apple.com/us/reviews/id455293667",
            "version": "2.3",
            "score": 1,
            "title": "Crazy ads",
            "text": "This game is absolutely an ad farm. It feeds you a ridiculous amount of ads. Most games it gives you the option to receive a reward for watching an ad and some ads mixed in here and there. This game forces you to watch an ad every few seconds, no option to pay for no ads, i wonder how much they make for selling your data. I deleted this game after 5 minutes, its a shame because it is really fun.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9510639374",
            "userName": "Zeus Zeus 1",
            "userUrl": "https://itunes.apple.com/us/reviews/id532959786",
            "version": "2.3",
            "score": 1,
            "title": "less pop ups to make the game fun",
            "text": "to many pops of stuff we can see along side to even enjoy the game cause after all that we have ads to watch",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9509057238",
            "userName": "fhfhghhhhg fun",
            "userUrl": "https://itunes.apple.com/us/reviews/id1395367311",
            "version": "2.3",
            "score": 5,
            "title": "Fun",
            "text": "I like it",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9507809623",
            "userName": "boodclaws0",
            "userUrl": "https://itunes.apple.com/us/reviews/id874642291",
            "version": "2.3",
            "score": 2,
            "title": "eh",
            "text": "way too many ads",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9504616350",
            "userName": "Fell in love with a girl",
            "userUrl": "https://itunes.apple.com/us/reviews/id363783248",
            "version": "2.3",
            "score": 2,
            "title": "Stupid ad's",
            "text": "This game has way to many pop ups/ad's and makes the games a little ridiculous to play and I don't recommend. They are just looking for their money.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9504002907",
            "userName": "gcpwilson",
            "userUrl": "https://itunes.apple.com/us/reviews/id261803549",
            "version": "2.3",
            "score": 1,
            "title": "Way too many ads",
            "text": "For too many ads for anyone’s liking, in my opinion. The app is development and the game is seemingly repetitive to other games out there.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9503418821",
            "userName": "Regulator1988",
            "userUrl": "https://itunes.apple.com/us/reviews/id114773095",
            "version": "2.3",
            "score": 1,
            "title": "Just ads",
            "text": "Nothing more than an ad generator",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9502409312",
            "userName": "isyounoob",
            "userUrl": "https://itunes.apple.com/us/reviews/id1269971507",
            "version": "2.3",
            "score": 4,
            "title": "Good",
            "text": "It’s good but it’s not a online game if it was it would be better",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9500880396",
            "userName": "Ahmet İkbal Adlığ",
            "userUrl": "https://itunes.apple.com/us/reviews/id1281714308",
            "version": "2.3",
            "score": 5,
            "title": "Engine pistons",
            "text": "Watching engine pistons has never been this fun 😍",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9500687874",
            "userName": "Honest review of games",
            "userUrl": "https://itunes.apple.com/us/reviews/id1487869741",
            "version": "2.3",
            "score": 2,
            "title": "It’s meh",
            "text": "Very pushy with “2x speed for 15 seconds” and similar boosts, the buttons are already on the side, and covering the screen while you need to tap to go fast and “be satisfying” is just a bit irritating. Another problem is how some upgrades have a level cap and cannot upgrade further other than pistons and cars from then on. I do not know if this changes on further levels because after level one, my car turned invisible, has infinite nitro, and cannot pass cars. The floating pistons just keeps passing the same place of a rival car over and over. Other than that, the game is alright with designs and the engine “building” is quite fun. Overall, not worth investing a lot of time into and seems like this game was just made with the sole purpose to have people watch ads rather than have more of a balance between a fun game and watching ads like the game “Mob Control” or “Cats and Soup” and other games I love where things aren’t shoved in my face and are more of an option. Then again, I am not the target audience of a young child.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9499867302",
            "userName": "Noahthegamer5",
            "userUrl": "https://itunes.apple.com/us/reviews/id428324534",
            "version": "2.2",
            "score": 1,
            "title": "Cool concept",
            "text": "This game is fun but literally not 10 seconds passes between ads. It’s unplayable due to how greedy the devs are.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9497199859",
            "userName": "berrymckokner",
            "userUrl": "https://itunes.apple.com/us/reviews/id104183840",
            "version": "2.2",
            "score": 1,
            "title": "Not good",
            "text": "This game is terrible nothing is correct and it’s nothing like the ads",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9496484784",
            "userName": "Mk//z06",
            "userUrl": "https://itunes.apple.com/us/reviews/id1487454997",
            "version": "2.1",
            "score": 1,
            "title": "Too many ads",
            "text": "Game is an ad-trap. The game is even insistent that it needs Wi-Fi to be played. Constant pop-ups with videos that you have to watch. Then, even in-game, constant pop ups and buttons all over the side that get you to watch an ad. Giant waste of time, with little developer effort.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9491770410",
            "userName": "×͜× ☻︎",
            "userUrl": "https://itunes.apple.com/us/reviews/id1314706716",
            "version": "2.1",
            "score": 1,
            "title": "Ads",
            "text": "Way to many ads barely even playable because every 30 seconds there’s a ad",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9491177174",
            "userName": "Kennyotter",
            "userUrl": "https://itunes.apple.com/us/reviews/id1451044140",
            "version": "2.1",
            "score": 1,
            "title": "Ads the game",
            "text": "Not even one minute into the game I got ten different pop ups asking if I wanted to increase my speed, or have auto tap, or merge for free. Right after clicking away from all of those an ad force played. Don’t forget the ad at the bottom either.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9486738863",
            "userName": "BrennanXSMax",
            "userUrl": "https://itunes.apple.com/us/reviews/id596576786",
            "version": "2.1",
            "score": 1,
            "title": "Ads",
            "text": "Yet another game on the App Store that fills games with so many ads the game is rendered unplayable.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9482862225",
            "userName": "daniel casaus",
            "userUrl": "https://itunes.apple.com/us/reviews/id1258520205",
            "version": "2.1",
            "score": 5,
            "title": "Anazing game",
            "text": "Ive always loved how pistons moved up and down and this game pretty much answered that and i knew i had to download it",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9482806686",
            "userName": "TheKnight2468",
            "userUrl": "https://itunes.apple.com/us/reviews/id446572279",
            "version": "2.1",
            "score": 2,
            "title": "Levels break after level 1",
            "text": "The game was great until I finished level 1 and it wouldn’t let me get the reward and move to level 2. I then tried closing and re-opening the game but then I was just sent to the end of the next level where I still had the same issue.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        },
        {
            "id": "9425759392",
            "userName": "BOOMXD8642",
            "userUrl": "https://itunes.apple.com/us/reviews/id482243206",
            "version": "1.0",
            "score": 2,
            "title": "Waste of time",
            "text": "Wasted 40mins to get to the end and not be able to beat the 1st place car.",
            "url": "https://itunes.apple.com/us/review?id=1660464064&type=Purple%20Software"
        }
    ]
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
