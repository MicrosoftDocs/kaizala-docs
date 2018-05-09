# Breaking Changes communication

Subscribe to [Kaizala Developer Connect](https://join.kaiza.la/g/jwoUnTyHR_Kgrd_GuDDc1w) from your mobile app to receive Breaking changes communication in Kaizala Developer Platform.

<!---

## Deprecating Mobile Number data from Kaizala APIs & Webhooks
||Details|
|--|--|
|**Impact Area**| APIs & Webhooks |
|**Impact Summary**|Kaizala APIs & Webhooks will stop returning Mobile Number as part of reponse. It will return Kaizala userIDs, which can be used to identify unique users. List of APIs & Webhook impacted:<br> <ol><li></li>|
|**Requires Action**|3rd party developers should make necessary changes to avoid break in their solutions. During the time period between 'Date of communication' & 'Date of Impact', Kaizala APIs will return both Mobile numbers and User IDs|
|**Date of Communication**| 18-04-2018 |
|**Date of Impact**| 15-05-2018|

-->
## Validation of registered callBackUrl when webhook is created

||Details|
|--|--|
|**Impact Area**| Webhooks |
|**Impact Summary**| Going ahead, during creation of Webhook ([POST /webhook](https://docs.microsoft.com/en-us/kaizala/connectors/webhooks#webhook)), registered callBackUrl would be validated. After successful validation, a webhook would be created |
|**Required Action**| Older Webhook subscriptions will continue to work beyond the Date of Impact. New Webhook subscription requests would require you to ensure your service follows the process mentioned [here](connectors/WebHookValidaton.md) |
|**Date of Communication**|09-05-2018|
|**Date of Impact**|15-06-2018|

<!---

## Webhook subscription will be cancelled, if 10 consecutive failures are received

||Details|
|--|--|
|**Impact Area**| Webhooks |
|**Impact Summary**| Subscription of WebHooks would be suspended, if Kaizala server doesn't receive success for 10 consecutive attempts. Developer will get communication regarding the same on Kaizala Developer Connect. Click here to join [Kaizala Developer Connect]()|
|**Required Action**||
|**Date of Communication**| 18-04-2018 |
|**Date of Impact**| 01-06-2018 |
-->

<!---
## Public groups can only be created using Tenant-level token in 'Create Group' API

||Details|
|--|--|
|**Impact Area**| APIs |
|**Impact Summary**| Managed Public Groups can be created through '[Create group](https://docs.microsoft.com/en-us/kaizala/connectors/groups#groups)', only when tenant user token is used in API |
|**Required Action**||
|**Date of Communication**|18-04-2018|
|**Date of Impact**|15-05-2018|

-->
