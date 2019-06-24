# SP Portal API Client Reference

## **Introduction**
This documentation provides the guide on how to use the API for your sportsbook data needs.

Please contact us if you have any problem.

<br>

### Authentication


#### HTTP Authentication:

API uses HTTP Bearer access authentication. You need to send the Authorization HTTP Request header:

```markdown
Authorization: Bearer <Token>
```

<!-- #### Token Based:

To authorize, use this code:

```markdown
curl "api_endpoint_here?token=YOUR-TOKEN"
```

Make sure replace YOUR-TOKEN with your real token. -->

<!-- You will get a **token** from our support. You should pass it as token= in GET query. -->

<br>

### API Endpoints

API endpoint is started with [https://api.sp-portal.com/](https://api.sp-portal.com)

<br>

### Data Limitation

Data limit is based on the **Plan** you subscribed. 

If you need to know more about our plans, please contact our support.


<br>

### Response

All responses are in JSON and has a success key to indicate it is successful or not.
You'll get **results** if everything moves well, and an (R-Errors) will be thrown if failed.



<br><br><br><br><br><!-- <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> -->



<!-- SPORTSBOOK API -->

# **Sportsbook Event API**

## Introduction
Sportsbook API includes Fixtures, Inplay and Results.

<br>

## **Inplay Events**

<br>

### HTTP Request


**Inplay with Main Market**

GET https://api.sp-portal.com/events/inplaywithmainmarket

```markdown
curl "https://api.sp-portal.com/events/inplaywithmainmarket/SPORT_ID"
```
This will generate list of inplay events with main market and latest odds.

<br>

**Inplay with All Markets**

GET https://api.sp-portal.com/events/inplaywithallmarket

```markdown
curl "https://api.sp-portal.com/events/inplaywithallmarket/SPORT_ID"
```
This will generate list of inplay events with all markets and latest odds.



<br>

### Query Parameters

Parameter | Required? | Description
--- | --- | --- 
sport_id | No | [Sport Id](#sportid)

`Note there is no pager in this API call. we just return all events.`

<br>

### HTTP Response

`Sample json file is still working in progress. Please check again later`


<br><br><br><br><br><!-- <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> -->


## **Upcoming Events**

<br>

### HTTP Request


**Upcoming with Main Market**

GET https://api.sp-portal.com/events/upcomingwithmainmarket

```markdown
curl "https://api.sp-portal.com/events/upcomingwithmainmarket/SPORT_ID/COUNTRY_CODE/LEAGUE_ID"
```
This will generate list of upcoming events with main market and latest odds.

<br>

**Upcoming with All Markets**

GET https://api.sp-portal.com/events/upcomingwithallmarket

```markdown
curl "https://api.sp-portal.com/events/upcomingwithallmarket/SPORT_ID/COUNTRY_CODE/LEAGUE_ID
```
This will generate list of upcoming events with all markets and latest odds.


<br>

### Query Parameters

Parameter | Required? | Description
--- | --- | --- 
sport_id | Yes | [Sport Id](#sportid)
country_code | No | [Country Codes](#countrycode)
league_id | No | Useful when you want to specify one league

`Note that by default, maximum data per request is 20 entries. Please contact our support for custom requests. `

`More options in this API call will be available soon.`


<br>

### HTTP Response

`Sample json file is still working in progress. Please check again later`

<br>


#### What's the format and timezone for 'time' field?

It's unix epoch. [Convert from epoch to human readable date](https://www.epochconverter.com/)

The timezone is UTC.



<br><br><br><br><br><!-- <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> -->


## **Ended Events**

<br>

### HTTP Request


**List of Ended Events**

GET https://api.sp-portal.com/events/ended

```markdown
curl "https://api.sp-portal.com/events/ended/SPORT_ID"
```
This will generate list of ended events.

<br>


### Query Parameters

Parameter | Required? | Description
--- | --- | --- 
sport_id | Yes | [Sport Id](#sportid)



`Note that currently, it will only display the last 20 results. More options in this API call will be available soon.`

<br>

### HTTP Response

`Sample json file is still working in progress. Please check again later`

<br><br><br><br><br><!-- <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> -->













## **Event Odds**

<br>

### HTTP Request


**Event Odds**

GET https://api.sp-portal.com/odds/getbyeventid

```markdown
curl "https://api.sp-portal.com/odds/getbyeventid/EVENT_ID/MARKET_KEY"
```
This will generate all latest market odds for the given event.

<br>


### Query Parameters

Parameter | Required? | Description
--- | --- | --- 
event_id | Yes | Event ID you get from events/*

`More options in this API call will be available soon.`

<br>

### HTTP Response

`Sample json file is still working in progress. Please check again later`

<br>

### Odds Markets

Market Key | Description | Market Key | Description
--- | --- | --- | --- 
1_1 | 1X2, Full Time Result | 1_2 | Asian Handicap
1_3 | 1X2, O/U, Goal Line | 1_4 | Asian Corners
1_5 | 1st Half Asian Handicap | 1_6 | 1st Half Goal Line
1_7 | 1st Half Asian Corners | 1_8 | Half Time Result
18_1 | Money Line | 18_2 | Spread
18_3 | Total Points | 18_4 | Money Line (Half)
18_5 | 	Spread (Half) | 18_6 | Total Points (Half)
18_7 | 	Quarter - Winner (2-Way) | 18_8 | Quarter - Handicap
18_9 | 	Quarter - Total (2-Way) | 3_4 | Draw No Bet
*_1 | 	Match Winner 2-Way |  | 
*_2 | 	Asian Handicap |  | 
*_3 | 	Over/Under |  | 









<br><br><br><br><br><!-- <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> -->
# Glossary

### <a name="sportid"></a>Sports Id

sport_id | Name | sport_id | Name
--- | --- | --- | --- 
1 | Soccer| 18 | Basketball
13 | Tennis | 91 | Volleyball
78 | Handball | 16 | Baseball
17 | Ice Hockey | 14 | Snooker
12 | American Football | 3 | Cricket
83 | Futsal | 15 | Darts
92 | Table Tennis | 94 | Badminton
8 | Rugby Union | 19 | Rugby League
36 | Australian Rules | 66 | Bowls
9 | Boxing/UFC | 75 | 	Gaelic Sports
90 | Floorball | 95 | 	Beach Volleyball
110 | Water Polo | 107 | Squash
151 | E-sports |  | 




### <a name="countrycode"></a>Country Codes




### <a name="timestatus"></a>time_status

Value | Description
--- | ---
0 | Not Started
1 | InPlay
2 | TO BE FIXED
3 | Ended
4 | Postponed
5 | Cancelled
6 | Walkover
7 | Interrupted
8 | Abandoned
9 | Retired
10 | Removed



<!-- 



<br><br>


You can use the [editor on GitHub](https://github.com/isystem20/sp-portal-api/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/isystem20/sp-portal-api/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
 -->