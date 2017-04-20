
![Hub of All things](http://hubofallthings.com/wp-content/uploads/banner21.png)

# Welcome to the HAT Project

Information for Developers - navigation to all relevant documents.

- If you are interested in developing something on the HAT, you may want to know [the HAT architecture](https://github.com/Hub-of-all-Things/HAT#architecture-diagram) first.
- We also have the [APIs](https://github.com/Hub-of-all-Things/DevInfo#api) so that you can input and ouput data from the HAT.
- If you need to build some extra services to input data into HATs, here are some existing [Data Plugs](https://github.com/Hub-of-all-Things/DevInfo#data-plugs) for you to consult.

## Who is who in the HAT Ecosystem?

![HAT Ecosystem](https://github.com/Hub-of-all-Things/HAT/blob/master/figures/Architecture.L0.png)

HAT is a personal data platform developed by the HAT Project that allows a HAT user to acquire, store, transform, view, sell, rent, trade and use his or her personal data. Also known as the HAT personal Data Platform (HATPDP).

HAT ecosystem is the community of all the individuals, firms and other organisations engaged in using the open source HAT technology, regulated by the HAT Foundation in compliance with the HAT CoP HAT Foundation. The social enterprise grouping that will nurture and regulate the HAT ecosystem based on the open-sourced HAT technology.

HAT Participants are roles in the HAT Ecosystem, which include:
- **Developers**: individuals who create HAT services and who could be working for HAT Service Providers.
- **HPPs (HATPDP Providers)**: organisations (platform providers) that host users' HATs and support a community of HAT developers by developing HAT services that improve the HAT personal Data Platform (HATPDP) capabilities.
- **HAT Users**: individuals who own and use HAT data and integrate data from HAT-ready devices and services.
- **HAT Service Providers**: organisations who provide a HAT service on the HATPDP.
- **The HAT Foundation **: The HAT Foundation is an organisation that manages and regulates the HAT ecosystem. Positioned as a form of exchange, it provides regulatory rules and services for personal data (and other related personal data instruments) to be traded in the HAT- enabled ecosystem, stimulate innovation around HAT, and grow the HAT community..

## Architecture Diagram
 
![Architecture Diagram](https://github.com/Hub-of-all-Things/HAT/blob/master/figures/Architecture.L1.png)

HATs can be provisioned via the web interface, one of which is currently in development. It is a mechanism to deploy, run and control individual HATs in a cloud environment, built in a microservice fashion to help any organisation to become a HAT Platform Provider. The HAT Platform Providers are expected, however, to create their own HAT provisioning systems fitting their needs and infrastructure.

#Tools available to get your started in the HAT ecosystem

## The most up to date stable version of HAT core is [HAT 2.0] (https://github.com/Hub-of-all-Things/HAT2.0)

In the current architecture, a [Kubernetes](http://k8s.io) cluster is created to run HATs. Kubernetes is used to manage all HATs and their databases running as separate, isolated [Docker](https://docker.com) containers across a number of Elastic Compute Cloud [EC2](https://aws.amazon.com/ec2) instances. Each HAT communicates with the outside world via [APIs](https://en.wikipedia.org/wiki/Application_programming_interface) and can be accessed by the owner and authorized applications from the outside world, including Rumpel interface. HAT data is persisted in encrypted Elastic Block Store [EBS](https://aws.amazon.com/ebs) units and backed up using EBS Snapshots, to make sure individuals' data is not lost even in the case of outages.

Currently available Data Plugs are run using a separate set of cloud resources, managed by [http://hubofallthings.com](http://hubofallthings.com) using the same orchestration tools and similar infrastructure. Further Data Plugs, developed by third-parties can be hosted separately and talk to individual HATs via the provided APIs.

Each database contains a data schema, allowing for storing any individual's data from any source without loosing the structure specific to the source, at the same time allowing the individual to relate their data to the context of their personal life and provide a common semantic structure for third parties to use such data.

## <a name="api"></a>API

HAT APIs were developed to exercise user managed control of your personal data. REST APIs for the HAT schema can be used by web, mobile and other clients to interact with the HAT, allowing the user to control their data and applications benefit from it. API documentation can be found at [http://hub-of-all-things.github.io/doc](http://hub-of-all-things.github.io/doc). 

## Data Plugs 

Data Plugs are bits of software allowing to retrieve individual's data (well basically our personal data) from data sources on internet (e.g. Facebook) into the HAT. Some already existing HAT Data Plugs:

**Facebook Data Plug**

[https://github.com/Hub-of-all-Things/DataPlugFacebook](https://github.com/Hub-of-all-Things/DataPlugFacebook)

Facebook Data Plug uses the Graph API to get data out of Facebook’s platform to the individual’s HAT. The Graph API is a “social graph”, which represents all data on Facebook as:
- nodes, which are Things like, for example, a user or a page;
- fields, which contain info about the Things like, for example, user’s name or birthday;
- edges, which connect the Things like, for example, comments on user’s photos
Currently supported nodes within the HAT are: Facebook user’s profile (such as name, age, etc), posts and events. Future development will feature more updates from a user's such as likes, check-ins, travels and other connect services like Spotify. More information about Facebook Graph API can be found [here](https://developers.facebook.com/docs/graph-api/reference).

**Dropbox Photo Data Plug**

[https://github.com/Hub-of-all-Things/DataPlugDropbox](https://github.com/Hub-of-all-Things/DataPlugDropbox)

Dropbox Data Plug currently uses Dropbox API to create metalinks to individual’s photos on Dropbox. This allows user to view his/her photos directly from the HAT, while the photos themselves are kept in the Dropbox storage. More information about the Dropbox API can be found [here](https://www.dropbox.com/developers/documentation/http/documentation).

**iCal Calendar Data Plug**

[https://github.com/Hub-of-all-Things/DataPlugCalendar](https://github.com/Hub-of-all-Things/DataPlugCalendar)

Calendar Data Plug employs iCalendar file format allowing individuals to collect their calendar information back into their hats. iCalendar Data synchronisation within the HAT is initialised by entering user’s ics calendar url into the form and submitting it. It depends on your calendar provider how you can obtain the URL. For example, for Google calendar visit [this](https://support.google.com/calendar/answer/37648?hl=en). Currently iCal Celendar Data Plug extracts a simple set of individual’s calendar event information, using ical.js (https://github.com/mozilla-comm/ical.js) library: event name, event start and end dates, “last updated” timestamp, event location, attendees, summary, description and organiser. For more information about iCalendar, please visit [this](https://en.wikipedia.org/wiki/ICalendar).

**Weather Data Plug**

The weather data plug is a Rumpel built-in function. It collects weather conditions at individual’s live location or a pre-defined location. It calls weather services from Weather Underground. Weather underground API documentation can be found [here](https://www.wunderground.com/weather/api/d/docs).


## Rumpel

[Harriet Project](http://hubofallthings.com/Harriet) team initiated the creation of [RUMPEL](https://github.com/Hub-of-all-Things/rumpel) - a hyper data browser for your HAT data. No one else can use RUMPEL to view your HAT data except yourself, as the HAT owner. It is compatible with all computer Operating Systems and it excludes all third parties, advertisements and ‘hard selling’. It is also being made available as an open source programme, under Mozilla Public License.
Personal Data is a combination of various information: your location on your phone, your Facebook postings, the music you listen to, etc. But we have never seen all of this data in one place! So when we do not have a way of seeing our data, we do not feel precious about it. It is like seeing bits of your clothing all over the place, but only when they come together in your wardrobe do you realise you have some good stuff and you can mix and match for your own benefit. Rumpel therefore fulfils this important psychological function with your Personal Data - making it your own HyperData Browser (our personal data wardrobe) with good data visualisations of your own data and allowing you to create bundles and collections. And in so doing, Rumpel must be able to "spin straw to gold" - to make the human being feel her / his data has value to herself / himself.

There are many people who want to sell their data because they think it is valuable to firms. What they do not understand is that an exchange of a precious commodity can happen only when both sides value the data.  If Rumpel can make you see real value of the data to yourself, you will demand more in exchange for it. But more importantly, the firms would also find your contextualised data more valuable!

To find out more about Rumpel, click [here](https://rumpel.hubofallthings.com/#/about)

## RumpelLite 
RumpelLite is the dashboard for your HAT on iOS. You can do with Rumpel Lite to
- Download and configure a HAT - private, personal data containers for storing consumer information generated on the internet  #### Securely store and maintain your own personal information
- Gather and capture information that's created about you by internet services like Facebook and Twitter
- Monitor and retain iOS sensor data about your location • Store and publish text-based notes and updates

## MarketSquare

MarketSquare is the service provided by HATDeX so that HATs can come together as a community and engage with the wider stakeholder community of the HAT ecosystem. On Marketsquare, HAT users can browse data offers, and build sub groups of HATs interested to engage with a cause or build new functionalities on the HAT. HAT users can keep up to date with the latest news , and chat with other HAT users.

MarketSquare is also where data shoppers sign up to ask for HAT data and HAT users can browse these offers and decide which are relevant and if they are willing to exchange their data in return for the benefits. 

Developers also go to MarketSquare to get their data plugs validated and published. Data plugs are services created by developers who wish to bring more and different types of data into the HAT. If a data plug has been created by a developer, they come into Marketsquare and register it for approval. Once approved, HAT users can use these data plugs to bring their data into their HATs. HAT users can also vote for the quality of the data plug by voting on it.

Click [here](https://marketsquare.hubofallthings.com/about) to find out more about MarketSquare

## Forum

We would like to encourage you to ask any questions you have and share your thoughts about your HAT experience. You can do this by joining [the HAT forum](http://forum.hatcommunity.org).
