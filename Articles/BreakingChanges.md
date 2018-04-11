# Breaking Changes communication

## Deprecating Mobile Number data from Kaizala APIs & Webhooks
||Details|
|--|--|
|**Impact Area**| APIs & Webhooks |
|**Impact Summary**|Kaizala APIs & Webhooks will stop returning Mobile Number as part of reponse. It will return Kaizala userIDs, which can be used to identify unique users. List of APIs & Webhook impacted:<br> <ol><li></li>|
|**Requires Action**|3rd party developers should make necessary changes to avoid break in their solutions. During the time period between 'Date of communication' & 'Date of Impact', Kaizala APIs will return both Mobile numbers and User IDs|
|**Date of Communication**| 18-04-2018 |
|**Date of Impact**| 01-06-2018|

## Mandatory Validation of registered callBackUrl when webhook subscription request is generated

||Details|
|--|--|
|**Impact Area**| Webhooks |
|**Impact Summary**| Going ahead, during subscription of Webhook ([POST /webhook](https://docs.microsoft.com/en-us/kaizala/connectors/webhooks#webhook)), registered callBackUrl would require to be validated successfully before registering a Webhook successfully |
|**Requires Action**||
|**Date of Communication**|18-04-2018|
|**Date of Impact**|01-06-2018|

## Webhook subscription will be cancelled, if 'x' failures are received

||Details|
|--|--|
|**Impact Area**| Webhooks |
|**Impact Summary**| Subscription of WebHooks would be suspended, if Kaizala server doesn't receive success for 'x' consecutive attempts |
|**Requires Action**||
|**Date of Communication**| 18-04-2018 |
|**Date of Impact**| 01-06-2018 |

## Public groups can only be created using Tenant-level token in 'Create Group' API

||Details|
|--|--|
|**Impact Area**| APIs |
|**Impact Summary**| Managed Public Groups can be created through '[Create group](https://docs.microsoft.com/en-us/kaizala/connectors/groups#groups)', only when tenant user token is used |
|**Requires Action**||
|**Date of Communication**|18-04-2018|
|**Date of Impact**|01-06-2018|

