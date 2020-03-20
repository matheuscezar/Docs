# Collabore

##### A project to help fight against covid19



## API Description (_Version_: 0.0.1)

Important: _**Base**_ below is the base url for any endpoint presented here for Collabore.

|      | URL                                     | HTTP Method | Media Type                                    | Collection   | Response                                                     | Action                                                       |
| ---- | --------------------------------------- | ----------- | --------------------------------------------- | ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | _Base_/Collabore/Citizen                | POST        | application/json<br />to request and response | Citizens     | success status code: 201;<br />body: Citizen (with UID setted) | Register new object of class Citizen in DB                   |
| 2    | _Base_/Collabore/Citizen                | PUT         | application/json<br />to request and response | Citizens     | success status code: 200;<br />body: Citizen updated         | Update existing object of class Citizen in database          |
| 3    | _Base_/Collabore/Citizen/{username}     | GET         | application/json<br />to response             | Citizens     | success status code: 200;<br />body: 0 or  1 Citizen         | Read a existing object of class Citizen in database by its username |
| 4    | _Base_/Collabore/Citizens               | POST        | application/json<br />to request and response | Citizens     | success status code: 200;<br />body: 0 or  more objects of class Citizen | Read existing objects according to the filter placed in the body of the request post message |
| 5    | _Base_/Collabore/Merchant               | POST        | application/json<br />to request and response | Merchants    | success status code: 201;<br />body: Merchant (with UID setted) | Register new object of class Citizen in DB                   |
| 6    | _Base_/Collabore/Merchant               | PUT         | application/json<br> to request and response  | Merchants    | success status code: 200;<br />body: Merchant updated        | Update existing object of class Merchant in database         |
| 7    | _Base_/Collabore/Merchant/{username}    | GET         | application/json<br />to response             | Merchants    | success status code: 200;<br />body: 0 or  1 Citizen         | Read a existing object of class Merchant in database by its username |
| 8    | _Base_/Collabore/Merchants              | POST        | application/json<br />to request and response | Merchants    | success status code: 200;<br />body: 0 or  more objects of class Merchant | Read existing objects according to the filter placed in the body of the request post message |
| 9    | _Base_/Collabore/HealthAgent            | POST        | application/json<br />to request and response | HealthAgents | success status code: 201;<br />body: HealthAgent (with UID setted) | Register new object of class HealthAgent in DB               |
| 10   | _Base_/Collabore/HealthAgent            | PUT         | application/json<br> to request and response  | HealthAgents | success status code: 200;<br />body: Merchant updated        | Update existing object of class HealthAgent in database      |
| 11   | _Base_/Collabore/HealthAgent/{username} | GET         | application/json<br />to response             | HealthAgents | success status code: 200;<br />body: 0 or  1 Citizen         | Read a existing object of class HealthAgents in database by its username |
| 12   | _Base_/Collabore/HealthAgents           | POST        | application/json<br />to request and response | HealthAgents | success status code: 200;<br />body: 0 or  more objects of class HealthAgent | Read existing objects according to the filter placed in the body of the request post message |
| 13   | _Base_/Collabore/Beacon                 | POST        | application/json<br />to request and response | Beacons      | success status code: 201;<br />body: Beacon (with UID setted) | Register new object of class Beacon in DB                    |
| 14   | _Base_/Collabore/Beacon                 | PUT         | application/json<br />to request and response | Beacons      | success status code: 200;<br />body: Beacon updated          | Update existing object of class Beacon in database           |
| 15   | _Base_/Collabore/Beacon/{uid}           | GET         | application/json<br />to response             | Beacons      | success status code: 200;<br />body: 0 or  1 Beacon          | Read a existing object of class Beacon in database by its uid |
| 16   | _Base_/Collabore/Beacons                | POST        | application/json<br />to request and response | Beacons      | success status code: 200;<br />body: 0 or  more objects of class Beacon | Read existing objects according to the filter placed in the body of the request post message |
|      |                                         |             |                                               |              |                                                              |                                                              |
|      |                                         |             |                                               |              |                                                              |                                                              |
|      |                                         |             |                                               |              |                                                              |                                                              |

