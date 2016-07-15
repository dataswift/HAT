
![Hub of All things](http://hubofallthings.com/wp-content/uploads/banner21.png)

# # Welcome to the HAT Project

Information for Developers - navigation to all relevant documents.

- If you are interested in developing something on the HAT, you may want to know [the HAT architecture](https://github.com/Hub-of-all-Things/DevInfo#architecture-diagram) first.
- We also have the [APIs](https://github.com/Hub-of-all-Things/DevInfo#api) so that you can input and ouput data from the HAT.
- If you need to build some extra services to input data into HATs, here are some existing [Data Plugs](https://github.com/Hub-of-all-Things/DevInfo#data-plugs) for you to consult.

### Who is who in the HAT Ecosystem?

![HAT Ecosystem](https://github.com/Hub-of-all-Things/DevInfo/blob/master/figures/HATeco.png)

HAT is a personal data platform developed by the HAT Project that allows a HAT user to acquire, store, transform, view, sell, rent, trade and use his or her personal data. Also known as the HAT personal Data Platform (HATPDP).

HAT ecosystem is the community of all the individuals, firms and other organisations engaged in using the open source HAT technology, regulated by the HAT Foundation in compliance with the HAT CoP HAT Foundation. The social enterprise grouping that will nurture and regulate the HAT ecosystem based on the open-sourced HAT technology.

HAT Participants are roles in the HAT Ecosystem, which include:
- **Developers**: individuals who create HAT services and who could be working for HAT Service Providers.
- **HPPs (HATPDP Providers)**: organisations (platform providers) that host users' HATs and support a community of HAT developers by developing HAT services that improve the HAT personal Data Platform (HATPDP) capabilities.
- **HAT Users**: individuals who own and use HAT data and integrate data from HAT-ready devices and services.
- **HAT Service Providers**: organisations who provide a HAT service on the HATPDP.
- **The HAT Foundation (HATDeX Foundation)**: HAT Data Exchange Foundation is an organisation that manages and regulates the HAT ecosystem. Positioned as a form of exchange, it provides regulatory rules and services for personal data (and other related personal data instruments) to be traded in the HAT- enabled ecosystem.

### Architecture Diagram
 
![Architecture Diagram](https://github.com/Hub-of-all-Things/DevInfo/blob/master/figures/hatarch.png)

HATs can be provisioned via the web interface, one of which is currently in development. It is a mechanism to deploy, run and control individual HATs in a cloud environment, built in a microservice fashion to help any organisation to become a HAT Platform Provider. The HAT Platform Providers are expected, however, to create their own HAT provisioning systems fitting their needs and infrastructure.

In the current architecture, a [Kubernetes](http://k8s.io) cluster is created to run HATs. Kubernetes is used to manage all HATs and their databases running as separate, isolated [Docker](https://docker.com) containers across a number of Elastic Compute Cloud [EC2](https://aws.amazon.com/ec2) instances. Each HAT communicates with the outside world via [APIs](https://en.wikipedia.org/wiki/Application_programming_interface) and can be accessed by the owner and authorized applications from the outside world, including Rumpel interface. HAT data is persisted in encrypted Elastic Block Store [EBS](https://aws.amazon.com/ebs) units and backed up using EBS Snapshots, to make sure individuals' data is not lost even in the case of outages.

Currently available Data Plugs are run using a separate set of cloud resources, managed by [http://hubofallthings.com](http://hubofallthings.com) using the same orchestration tools and similar infrastructure. Further Data Plugs, developed by third-parties can be hosted separately and talk to individual HATs via the provided APIs.

Each database contains a data schema, allowing for storing any individual's data from any source without loosing the structure specific to the source, at the same time allowing the individual to relate their data to the context of their personal life and provide a common semantic structure for third parties to use such data.

### <a name="api"></a>API

HAT APIs were developed to exercise user managed control of your personal data. REST APIs for the HAT schema can be used by web, mobile and other clients to interact with the HAT, allowing the user to control their data and applications benefit from it. API documentation can be found at [http://hub-of-all-things.github.io/doc](http://hub-of-all-things.github.io/doc). 

### Data Plugs 

Data Plugs are bits of software allowing to retrieve individual's data from data sources on internet (e.g. Facebook) into their HAT. For more details, please visit [here](http://forum.hatdex.org/t/what-are-the-hat-data-plugs). An initial set of Data Plugs:

- [x] Facebook: [https://github.com/Hub-of-all-Things/DataPlugFacebook](https://github.com/Hub-of-all-Things/DataPlugFacebook) 
- [x] Photos from Dropbox: [https://github.com/Hub-of-all-Things/DataPlugDropbox](https://github.com/Hub-of-all-Things/DataPlugDropbox) 
- [x] iCal Calendar: [https://github.com/Hub-of-all-Things/DataPlugCalendar](https://github.com/Hub-of-all-Things/DataPlugCalendar) 
- [x] Weather Underground
- [ ] HAT Location App (iOS location data plug) - due in Sep 2016: [https://github.com/Hub-of-all-Things/hat-mobile](https://github.com/Hub-of-all-Things/hat-mobile) 

### Rumpel

The HAT is done - it is stable to be built on and it is ready. But it is like saying, "I have a www or I have an operating system". Not exciting. So [Harriet Project](http://hubofallthings.com/Harriet) team created Rumpel - a killer app (and there can be many!) to get the HAT into a roll-out stage where it would be adopted by millions. To understand what Rumpel is, however, you should first understand what Personal Data is. 

Personal Data is a combination of various information: your location on your phone, your Facebook postings, the music you listen to, etc. But we have never seen all of this data in one place! So when we do not have a way of seeing our data, we do not feel precious about it. It is like seeing bits of your clothing all over the place, but only when they come together in your wardrobe do you realise you have some good stuff and you can mix and match for your own benefit. Rumpel therefore fulfils this important psychological function with your Personal Data - making it your own HyperData Browser (our personal data wardrobe) with good data visualisations of your own data and allowing you to create bundles and collections. And in so doing, Rumpel must be able to "spin straw to gold" - to make the human being feel her / his data has value to herself / himself.

There are many people who want to sell their data because they think it is valuable to firms. What they do not understand is that an exchange of a precious commodity can happen only when both sides value the data.  If Rumpel can make you see real value of the data to yourself, you will demand more in exchange for it. But more importantly, the firms would also find your contextualised data more valuable!

### Forum

We would like to encourage you to ask any questions you have and share your thoughts about your HAT experience. You can do this by joining [the HAT forum](http://forum.hatdex.org).

### HATs UP!

We have raised £50K and our Indiegogo campaign is a success! There are still a small number of Beta HAT available, so ...

[![Grab your HAT!](https://github.com/Hub-of-all-Things/DevInfo/blob/master/figures/indiegogo.png)](https://www.indiegogo.com/projects/hat-claim-your-data-organise-visualise-control--3#)

We would like to encourage everyone to ask any questions they have and share their thoughts about the HAT experience in our social media channels: [Facebook group](https://www.facebook.com/hubofallthings) and [Twitter](https://twitter.com/TheHATDex). 

### Background of the HAT Project

The HAT is a research project on engineering a market for personal data and, therefore, designing the economic and business models relevant for this market. As such, we do not have many of the answers. However, over the course of the research, we have done some substantial work and made decisions so that we can move forward to realising the vision. The work done is now articulated in the following six briefing papers:

- HAT Project Research Team. (2015) HAT briefing paper 1 : **Engineering a market for personal data : the Hub-of-all-Things (HAT).**  WMG Service Systems Research Group Working Paper Series (Number 01/15). Available at: [http://wrap.warwick.ac.uk/65605](http://wrap.warwick.ac.uk/65605).
- HAT Project Research Team. (2015) HAT Briefing Paper 2 : **The Hub-of-all-Things (HAT) economic model of the multi-sided market platform and ecosystem.** WMG Service Systems Research Group Working Paper Series (Number 02/15).  Available at: [http://wrap.warwick.ac.uk/65607](http://wrap.warwick.ac.uk/65607).
- HAT Project Research Team. (2015) HAT Briefing Paper 3 : **The Hub-of-all-Things (HAT) code of practice on personal data.** WMG Service Systems Research Group Working Paper Series (Number 03/15). Available at: [http://wrap.warwick.ac.uk/65608](http://wrap.warwick.ac.uk/65608). 
- HAT Project Research Team. (2016) HAT Briefing Paper 4 : **HAT personal data exchange ecosystem - technology architecture briefing.** WMG Service Systems Research Group Working Paper Series (01/16). Available at: [http://wrap.warwick.ac.uk/77855](http://wrap.warwick.ac.uk/77855). 
- HAT Project Research Team. (2016) HAT Briefing Paper 5 : **Rolling out HATs and creating the market for personal data - the HAT foundation.** WMG Service Systems Research Group Working Paper Series (02/16). Available at: [http://wrap.warwick.ac.uk/77857](http://wrap.warwick.ac.uk/77857).  
- HAT Project Research Team. (2016) HAT Briefing Paper 6 : **Personal data exchange ecosystem : code of practice release 1.** WMG Service Systems Research Group Working Paper Series (03/16). Available at: [http://wrap.warwick.ac.uk/77858](http://wrap.warwick.ac.uk/77858).
