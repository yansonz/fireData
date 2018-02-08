![fireData](http://frapbot.kohze.com/fireData/topImage6.jpg)

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/Kohze/fireData/master/LICENSE.txt)
[![Build Status](https://travis-ci.org/Kohze/fireData.svg?branch=master)](https://travis-ci.org/Kohze/fireData)
[![codecov](https://codecov.io/gh/Kohze/fireData/branch/master/graph/badge.svg)](https://codecov.io/gh/Kohze/fireData)


**Project Title:** FireData: Connecting R to Google Firebase

--- 

FireData integrates R Datascience with the abilities and possibilities of the Google Firebase Framework.

Firebase makes it possible to exchange in real-time information in the Cloud and thereby opening the R language to IoT hardware/data processing. Other than that it is also immensely useful for shiny application to integrate Social Authentications and persistent data & uploads.

This package was created within the framework of Google Summer of Code 2017. 

![fireData](http://frapbot.kohze.com/fireData/setup2.jpg)

**Database Setup:**
- visit at https://firebase.google.com/
- login and enter the "console"
- add new project
- find the API keys at the "overview" page clicking on add firebase to web-app

**R Package Setup:**

```
if (!require("devtools")) install.packages("devtools")
devtools::install_github("Kohze/fireData")

library(fireData)
```

![examples](http://frapbot.kohze.com/fireData/examples2.jpg)

- uploading a data.frame:

```upload(x = mtcars, projectURL = "https://firedata-b0e54.firebaseio.com/",  directory = "main")```

- download a data.frame:

```download(projectURL = "https://firedata-b0e54.firebaseio.com/", fileName = "main/-KxwWNTVdplXFRZwGMkH")```

- register a new user

```createUser(projectAPI = "AIzaSyAjZLO9-CRV3gObpwdFz-k8AiTOxHSBmdc", email = "your@email.com", password = "12341234" )```

- create token for authenticated requests (can be used for the token argument of upload/download)

```auth(projectAPI = "AIzaSyAjZLO9-CRV3gObpwdFz-k8AiTOxHSBmdc", email = "robin@kohze.com", password = "12341234")```

- resett user password

```resetPassword(projectAPI = "AIzaSyAjZLO9-CRV3gObpwdFz-k8AiTOxHSBmdc", email = "useYourOwn@email.com")```

- backup the database and save as .json

```dataBackup(projectURL = "https://firedata-efa5a.firebaseio.com", secretKey = "2bYA6k72wKna90MqPGa6yuMG7jAysoDJZwJqYXsm", "test.json")```
        

![fireData](http://frapbot.kohze.com/fireData/related2.jpg)

fireData is already integrated into a several projects. 

- SpatialMaps: A spatial proteomics platform that utilizes firebase as cross platform database.

- Cryptotrade-hq bot: A simple data collector (with shiny) that uses firebase for secure storage of API keys.


![fireData](http://frapbot.kohze.com/fireData/development2.jpg)

Milestone 3 (28-08-2017):

- [x] Added DB access via firebase DB secret
- [x] Extended class/data.frame/list support
- [x] Updated Unit Tests
- [x] Added 2 example projects for fireData (spatialmaps & cryptotrade-hq)  

Milestone 2 (24-07-2017):

- [x] integrated fireData in the spatialMaps project (currently fork is pending)
- [x] Added more secure logins by adding prompts
- [x] Extending the descriptions/documentation
- [x] added unit tests and reached 100% test coverage 

Milestone 1 (25-06-2017):

- [x] user authentication
- [x] general API functionality (upload, download)
- [x] user registration/pw resett
- [x] token generation


---

**Aknowledgements:**

I hereby want to thank my GSOC mentors L. Pedraza, S. Schmidt for their project support and especially L. Gatto for his insights and experience to make this package a reality. 
