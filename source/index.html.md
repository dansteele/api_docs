---
title: eola API

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby

toc_footers:
  - <a href='mailto:hello@eola.co.uk'>Ask us for a developer key</a>

includes:
  - errors

search: true
---

<!-- # frozen_string_literal: true

class PublicApi < ApplicationController

  before_action :authenticate_integrated_partner!
  before_action :add_request_to_integrated_partner

  private

  def authenticate_integrated_partner!
    @integrated_partner = IntegratedPartner
      .find_by(token: request.headers['Authorization'])
    :abort unless @integrated_partner
  end

  def add_request_to_integrated_partner
    @integrated_partner.increment!(:requests_made)
  end

end
 -->



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

eola expects for the API key to be included in all API requests to the server
in a header that looks like the following:

`Authorization: your_api_key`

<aside class="notice">
  You must replace <code>your_api_key</code> with your personal API key,
  which follows a standard UUID format.
</aside>

# Outlets

## Retrieve An Outlet

```shell
curl "https://eola.co.uk/public_api/outlets/1"
  -H "Authorization: your_api_key"
```


> The above command returns JSON structured like this:

```json
{  
  "name": "Waffle",
  "description": null,
  "updated_at": "2018-10-25T12:32:34.844Z",
  "slug": "waffle",
  "minimum_notice_hrs": 24,
  "link_to_site":  "https://eola.co.uk",
  "phone_number": "01231 231214",
  "child_age": 16,
  "default_currency": "gbp",
  "address": {  
    "id": 406,
    "street_name": "Green Lanes",
    "city": "London",
    "country": "GB",
    "post_code": "N4 1AJ",
    "created_at": "2018-03-29T18:47:52.923Z",
    "updated_at": "2018-03-29T18:47:52.923Z",
    "latitude": 51.5803495,
    "longitude": -0.099535,
    "building_name": "475"
  },
  "profile_picture":"image/upload/v1522917781/eola/profile_pictures/1522917780waffle.jpg"
}
```

This endpoint retrieves the information for a given outlet.

### HTTP Request

`GET https://eola.co.uk/public_api/outlets/1`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_offers | false | Should the result also include offers.
include_cancellation_policy | false | Should the result include cancellation policy information. Note that all outlets fall back to a default, generic policy if they have not set one themselves.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
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
