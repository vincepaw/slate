---
title: AW  Billing  API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - php: Force(php)
  - html: External(html)

toc_footers:
  - <a href='https://github.com/advisorwebsites/d8platform/tree/master/modules/custom/aw_billing'>aw_billing Module</a>

includes:
  - errors

search: false
---

# Introduction

 Draft Outline of Billing API extrapolated from curren aw_billing module


# Subscriptions

## Get Currency
> Get Currency 

```php
	
	getCurrency('$country')

```

```html
	
	get api request returns currency type

```
 Returns Currency Type



## Update Subscription

> Update Subscription

```php
	updateSubscription($current, $subscr_params,$billing_details)

```

```html

```



## Add Addon to Subscription

> Add Addon to Subscription

```php
	
	addAddonToSubscription($site_id, $addon_name, $number = 1)
```

```html

```

## Create Subscription

> Create Subscriptions

```php

	createSubscription('Subscription Details')

```

```html

```

## Sync Plan

> Sync Plan

```php

  syncPlan(PlanDetailsInterface $plan_details, PlanInterface $plan)

```

```html
```

## Charge Setup Fee

Transaction for one-time setup/onboarding.

> Charge Setup Fee

```php
  
  chargeSetupFee($setup_fee, $account, $subscription)
  
```
```html
```

## Charge Prorated Addon Amount

Executes prorated charge on account

> Charge Prorated Addon Amount
```php

  chargeProratedAddonAmount($amount, $account, $subscription)

```

```html
```

## Update From Plan Details

> Updates plan details from external.

```php

  updateFromPlanDetails(PlanDetailsInterface $plan_details)
```

```html
```

## Cancel Subscription

> Cancel Subscription

```php

  cancelSubscription($subscr_id)

```

```html
```
















# Slate Examples

## Get All Kittens

```php
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```html
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```php
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```html
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
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

```php
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```html
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

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
ID | The ID of the kitten to delete

