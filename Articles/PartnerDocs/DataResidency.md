# Data residency and go-local support in Microsoft Kaizala

Beginning April 2019, Microsoft Kaizala will provide regional data residency support through the datacenters in Europe (EU), Asia Pacific (APAC), United States (US), and India (IN). This means Kaizala customers will have data related to organization chats and groups such as messages, attachments, and Kaizala actions stored in the datacenter of their billing region.

In addition to supporting the goals of within-region data residency, Kaizala service datacenters will also facilitate failover and disaster recovery through the datacenters.

## Global datacenter footprint with data residency support

Currently, Kaizala has eight datacenters (primary and backup) in three regions and one country:

- APAC (Serves Asia Pacific except India) - Datacenters in Singapore and Hong Kong
- EMEA (EU, MEA) - Datacenters in Dublin and Amsterdam
- AMER (North and South Americas) - Datacenters in Texas and Illinois
- India (Go-Local) - Datacenters in Chennai and Pune

In addition to providing compute and storage, Kaizala also provides data residency support, robust failover, and disaster recovery support to enterprise customers. Also, these scale units help ensure improved connectivity and messaging performance to both enterprise and general customers. 

![Graphic showing data residency and Go-Local geo boundaries in Kaizala](Images\data-residency-geo-boundaries.png)

## How is data stored in Kaizala

Kaizala stores data differently based on data types of the messages.

- **Chats, likes, and comments** - All messages, likes, and comment data belonging to organization group or org 1:1 chats are stored in a secure Office 365 and Azure powered chat service that is regionally bounded for tenants, based on their billing country.
- **Attachments** - All attachments are co-located along with chat messages in the same data boundary.
- **Kaizala Action cards** - All Kaizala Action card data, which includes metadata, action package, and response report data, are co-located with chat service in the same data boundary.
- **Calling** - Being transient, Kaizala calling data is not stored in datacenters. However, call logs follow the same data residency as chats.

### Example

Contoso has its Office 365 billing country in EU. Contoso has signed up on Kaizala in April 2019 and all of its core data including chats, attachments and action cards will be stored at rest exclusively in EU scale units (Dublin and Amsterdam).

## What is in store in future

- **Onboarding on to data location page** - For enterprises, the data location for different workloads of Office 365 is visible under Office 365 admin portal under Home\Organizational Profile. The ability to onboard Kaizala to the data location page on admin portal is forthcoming. Watch this section for updates.
- **New datacenters** - The Kaizala team is continuously looking at expansion based on providing the best user experience to users. If you have a business case, then post your questions in our [Technet community](https://techcommunity.microsoft.com/t5/Microsoft-Kaizala/ct-p/MicrosoftKaizala).

## FAQs

### What does it mean for existing enterprise customers?

Existing customers in India already have their data residency within India. Data for all non-India existing tenants however will continue to stay in the group location (based on creator’s country code). However after April 2019, all the newer organization groups and messages of existing organization groups or chats will start following data residency based on the tenant’s billing region.

### What does it mean for new enterprise customers?

Data residency will be automatically applicable for all the customers who sign up on Kaizala after April 2019. Additionally, data residency on action cards should be applicable on the latest Android or iOS app versions.
 
### I do have more questions. Who do I reach out to?

In case of more questions, contact your account team or our [Technet community](https://techcommunity.microsoft.com/t5/Microsoft-Kaizala/ct-p/MicrosoftKaizala). Additionally, you can write to [Kaizalafeedback@microsoft.com](mailto:kaizalafeedback@microsoft.com).








