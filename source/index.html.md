---
title: eola API

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='mailto:hello@eola.co.uk'>Ask us for a developer key</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the eola API!
This API will allow you to integrate with eola and the businesses busing eola.
You'll be able to get the latest business, time slot and booking information.
Looking to make bookings entirely via the API? That's possible too!


# Authentication

> To authorize, pass your authorization token as an Authorization header:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: your_api_key"
```

> Make sure to replace `your_api_key` with your API key.

eola uses API keys to allow access to the API.
If you haven't already, [ask us for a developer key](mailto:hello@eola.co.uk).

eola expects for the API key to be included in **all** API requests to the server
in a header that looks like the following:

`Authorization: your_api_key`

<aside class="notice">
  You must replace <code>your_api_key</code> with your personal API key,
  which follows a standard UUID format.
</aside>

# Outlets

## Retrieve An Outlet

```shell
curl "https://eola.co.uk/api/outlets/perranporth-surf-school"
  -H "Authorization: your_api_key"
```


> The above command returns JSON structured like this:

```json
{
  "description": null,
  "updated_at": "2018-10-25T12:32:34.678Z",
  "slug": "perranporth-surf-school",
  "minimum_notice_hrs": 24,
  "link_to_site": "https://www.perranporthsurfschool.co.uk",
  "phone_number": "+447974550823",
  "child_age": 16,
  "default_currency": "gbp",
  "profile_picture": {
    "thumb": "https://res.cloudinary.com/eola/image/...",
    "fb_friendly": "https://res.cloudinary.com/eola/image/...",
    "wide": "https://res.cloudinary.com/eola/image/...",
    "fullscreen": "https://res.cloudinary.com/eola/image/...",
    "large": "https://res.cloudinary.com/eola/image/...",
    "square": "https://res.cloudinary.com/eola/image/...",
    "preview": "https://res.cloudinary.com/eola/image/...",
    "profile_card": "https://res.cloudinary.com/eola/image/...",
    "tiny_profile_pic": "https://res.cloudinary.com/eola/image/...g"
  },
  "cancellation_policy": {
    "name": "not_set"
  },
  "address": {
    "id": 434,
    "street_name": "19 St. Piran’s Road",
    "city": "Perranporth",
    "country": "GB",
    "post_code": "TR60DE",
    "created_at": "2018-10-15T15:44:23.443Z",
    "updated_at": "2018-10-15T15:44:23.443Z",
    "latitude": 50.345734,
    "longitude": -5.15174,
    "building_name": "Bathsheba Surf"
  }
}
```

This endpoint retrieves the information for a given outlet.

### HTTP Request

`GET https://eola.co.uk/api/outlets/perranporth-surf-school`


### Response notes
Field | Note
--------- | ------- | -----------
description | Rich text field.
cancellation_policy  |  When the `name` value is `custom`, then `custom_text` fields will also be sent. These will be in rich text.

<aside class="warning">
  The majority of this information is set by the customer and can change without warning.
  We will cache your request for you for optimal response times, but caching this information
  yourself will need careful consideration.
</aside>

<!-- ## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete -->
