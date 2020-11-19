# BMI estimation from images

Project scope is to estimate the BMI of a person from pictures of the face. 

This repository contains a data collection project for using inmate mug photos. This pictures are used to train a deep learning algorithm to obtain the BMI from the image of a person's face

# Contents

## US County Prison/Jails mugshot and biometric info (weight, height)
- ```Inmate Data Mining.ipynb```
  - class ```PageParser``` - base class for page parsers, abstracts  ```beautifulsoup``` internals and wraps content retrieval
    - class ```PolkCountyInmatesScraper``` - scraper for [Polk County Inmates](https://apps.polkcountyiowa.gov/PolkCountyInmates/CurrentInmates/)
    - class ```MarionCountyInmatesScraper``` - scraper for  [Marion County Correctional Facility Inmate Roster](https://apps.co.marion.or.us/jailrosters/mccf_roster.html)
  -  class ```Person``` - POJO
  -  class ```Scrapper``` - converts from scrape result to a ```Person``` object
  -  class ```MarionCountyInmatesCrawler``` - crawler that uses the parser to obtain new leads and to scrape those urls
     -  class ```MarionCountyInmatesLocalDb``` - sqlite3 wrapper, acts as crawler state
  -  class ```PolkCountyInmatesCrawler``` - crawler that uses the parser to obtain new leads and to scrape those urls
     -  class ```PolkCountyInmatesLocalDb``` - sqlite3 wrapper, acts as crawler state
   -  class ```BMILocalDb``` - sqlite3 and file system wrapper, holds ```Person``` objects (including images)
   -  class ```ResponseStream``` - wrapper for handling image downloads
`
#### A collection of ~4000 images with biometric information are available in the [v1.0 release](https://github.com/raducrs/bmi-image-estimation/releases/tag/v1.0)

  
 ## IMDB 
- ```Untitled.ipynb```

  Explores an IMDB dataset containing weight and height of celebrities
  
