---
title: "CFPB Open Source Documentation"
---

Since it's formation in 2011, the Consumer Financial Protection Bureau (CFPB) has produced several open source projects that not only serve the needs of their team, but allow for easy re-use by sister agencies.  A number of these projects are highlighted at their [Open Tech hub](http://cfpb.github.io/).  One notable example is the [API documetation](http://cfpb.github.io/api/hmda/) for the agency's Home Mortgage Disclosure Act (HMDA) data.  The team responsible for this API knew that it needed to offer simple yet functional documentation to developers who were interested in using the web service.  Traditionally, this documentation is offered as html pages within the agency’s normal content process (e.g. via the same content management system used by the rest of the website).  But the CFPB team literally open-sourced the website content itself, making it quick and easy for others to suggest improvements or re-use their good work.  

The [HMDA API documentation](http://cfpb.github.io/api/hmda/) is correctly seen as a model for others to follow.  It offers the full range of [common elements of API documentation](http://18f.github.io/API-All-the-X/pages/api_release_kit), organized with a clean, user-friendly design.  During usability testing, several outside developers directly stated that they wished that other agencies would just follow this example.  Notably, CFPB made this simple to do.  CFPB kicked off this project by first creating a [simple, well-designed template](http://cfpb.github.io/DOCter/index.html) that could be employed for this project and others.  CFPB’s important decision was to not just opensource the code for their API docuementation but to literally host it as an open source project in GitHub pages.   As a result, the code maintained [in the relevant repository](http://github.com/cfpb/api) is instantly applied to what users see on CFPB.GitHub.io.  If any site visitor saw a typo, they could issue a pull request to correct it and CFPB could easily accept the edit.  Furthermore, this model allows for any other user to copy the entire site and instantly see their version hosted in realtime via github pages.  

At the General Services Administration, a team working on SAM.gov was preparing the release of an API to that program’s data.  The original documentation took the form of a lengthy and unweildy word document that would be hosted for download.  Initial feedback quickly drove the SAM.gov team to see the need for more user-friendly, html-based documentation.  The CFPB example was not just an inspiration or a model to imitate.  The SAM.gov team literally forked CFPB's documentation and modified it to match their API's specifics.  The [end product](http://gsa.github.io/sam_api/sam/) perfectly suits their needs and has received solid reviews from outside developers.  By re-using the good work of others, GSA was able to save time and money while still delivering a top-quality product.  

**Updates:** 

* The GSA Auctions API team followed the same path in publishing [their new API](http://gsa.github.io/auctions_api/), further increasing the savings from this re-use project.  
* The Regulations.gov API team is now [using this project as well](http://regulationsgov.github.io/developers/).  
* This topic is covered in further detail in [this Digital Government University session](http://youtu.be/ZRhRU5y0jEk?t=36m33s).  



