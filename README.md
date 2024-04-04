# Biskra-nadifa-API-Docementation


# Biskra nadifa API Dcumentation
## Introduction
Welcome to Biskra nadifa API Documentation! this Documentation is Specially made for Biskra Nadifa Developers, if you don't know, Biskra nadifa platform Consist of 3 Main Actors, each one of these actors have his own custom API, these Actors Are: 

  - Dashboard
  - Driver
  - Citizen
    
in each API section we will display the information of the Actor and it's Actions, Enjoy!

currently the API's is not deployed so the Endpoint will like kind of this format: 
localhost:[your selected port]/dashboard
**if you are using the default spring boot app , the port will be one 8081 , so the Endpoint will look like this : localhost:8081/dashboard** 
                                                                                                                                              
<details>
  <summary><h2> Dashboard API </h2> 
  </summary>
  
  this API covers the necessary Operation for the Dashboard Users such as retreival of all (Tasks, Suggestions,Reports, Availlable Truck Drivers and so on)  
 
### Get all reports 
Get all reports  
Endpoint: /dashboard/reports  
Method: GET  
Description: Retrieves a list of all reports submitted by citizens.  

#### Example Response 

```json  
[
    {
        "id": 1,
        "reporterId": 44,
        "reportType": "personal trash",
        "reportDescription": "Broken glass bottles on the sidewalk",
        "reportLocation": "P9MJ+2PG، نهج الأمير عبد القادر، Tolga ،Algeria",
        "image": "picture1.png",
        "imagedata": "[binary data]",
        "createdAt": "2024-02-02T20:00:06"
    },
    {
        "id": 2,
        "reporterId": 34,
        "reportType": "too many trash",
        "reportDescription": "Overflowing trash cans on Main Street",
        "reportLocation": "P9MJ+2PG، نهج الأمير عبد القادر، Tolga ،Algeria",
        "image": "pic_001.png",
        "imagedata": "[binary data]",
        "createdAt": "2022-11-19T16:23:00"
    },
    {
        "id": 3,
        "reporterId": 20,
        "reportType": "not collected trash",
        "reportDescription": "Piles of litter in the park",
        "reportLocation": "Université de Biskra، BP 145 RP، BISKRA 07000 ،Algérie",
        "image": "pic_001.png",
        "imagedata": "[binary data]",
        "createdAt": "2023-12-25T02:47:51"
    }
]
```

<h3>Get all drivers  </h3> 
Endpoint: /dashboard/drivers  
Method: GET  
Description: Retrieves a list of all drivers. 
### Example Response 

```json
[
    {
        "id": 1,
        "name": "Aisha",
        "surName": "Touil",
        "phoneNumber": "051231758",
        "hashedPassword": "$2a$04$ZDRdT3NJfn0sxRuDQ8etDOZCo/WB2JOrm.n2aEPh7W0sFL/43S4WK",
        "status": null,
        "plateNumber": "42-199-9999",
        "dateOfBirth": "3/9/2001",
        "gender": "Female"
    },
    {
        "id": 2,
        "name": "Fatima",
        "surName": "Bouziane",
        "phoneNumber": "052173251",
        "hashedPassword": "$2a$04$w5x/MVwelubwWBdyB7pUHupWUgTnofIesh.H.K75AawwQ1PVkknlC",
        "status": null,
        "plateNumber": "06-190-6999",
        "dateOfBirth": "5/20/2002",
        "gender": "Male"
    }
]
```
<h3>Get all tasks</h3> 

Endpoint : /dahsboard/tasks \
Method : GET \
Description : Retrieves a list of all Tasks.

### Example Response 

```json

[
    {
        "id": 1,
        "report": {
            "id": 35,
            "reporterId": 35,
            "reportType": "too many trash",
            "reportDescription": "Overflowing trash cans on Main Street",
            "reportLocation": "RPWW+FV8 ،Biskra ،Algeria",
            "image": "picture1.png",
            "imagedata": "MHhGRkQ4RkZFMDAwMTA0QTQ2NDk0NjAwMDEwMTAwMDAwMTAwMDEwMDAw",
            "createdAt": "2023-06-15T18:46:19"
        },
        "status": "done",
        "createdAt": "2020-11-01T12:55:29",
        "finishedAt": "2020-09-02T11:46:24",
        "assingerSystemUser": {
            "id": 11,
            "name": "Ali",
            "surName": "Bouzeghoubi",
            "phoneNumber": "079140622",
            "hashedPassword": "$2a$04$paBsF4Yvv/UF8MqlJ9NHaeuzGwWynioRmh3s8LEVWJS4V7Ev99Qa6",
            "dateOfBirth": "5/18/2023",
            "gender": "Male"
        }
    },
    {
        "id": 2,
        "report": {
            "id": 36,
            "reporterId": 2,
            "reportType": "not collected trash",
            "reportDescription": "Broken glass bottles on the sidewalk",
            "reportLocation": "RPWW+FV8 ،Biskra ،Algeria",
            "image": "picture1.png",
            "imagedata": "MHhGRkQ4RkZFMDAwMTA0QTQ2NDk0NjAwMDEwMTAwMDAwMTAwMDEwMDAw",
            "createdAt": "2023-07-17T17:02:45"
        },"status": "done",
        "createdAt": "2022-03-08T03:25:01",
        "finishedAt": "2020-07-24T21:18:30",
        "assingerSystemUser": {
            "id": 35,
            "name": "Ali",
            "surName": "Ait Ali",
            "phoneNumber": "051397260",
            "hashedPassword": "$2a$04$cJLdun3HPpi4WMnjeQK/JeCf1bQaYbSGgNnwnCOnagzzijocIdvUG",
            "dateOfBirth": "3/26/2024",
            "gender": "Female"
        }
    }
]
```

Endpoint : /dahsboard/tasks/{taskId} \
Method : GET \
Description : Retrieves task by id .
Example : /dahsboard/tasks/5
### Example Response 
```json
{
    "id": 5,
    "report": {
        "id": 6,
        "reporterId": 4,
        "reportType": "not collected trash",
        "reportDescription": "Overflowing trash cans on Main Street",
        "reportLocation": "RPWW+FV8 ،Biskra ،Algeria",
        "image": "pic_001.png",
        "imagedata": "MHhGRkQ4RkZFMDAwMTA0QTQ2NDk0NjAwMDEwMTAwMDAwMTAwMDEwMDAw",
        "createdAt": "2023-12-07T11:58:29"
    },
    "status": "done",
    "createdAt": "2021-06-20T03:12:45",
    "finishedAt": "2020-12-11T05:26:28",
    "assingerSystemUser": {
        "id": 23,
        "name": "Mohammed",
        "surName": "Ait Ali",
        "phoneNumber": "078352326",
        "hashedPassword": "$2a$04$/szV8GPrCM2/tcw7fJdLKe4rGlRWnD.OWlziZO/eLXbVFE8OrYPGu",
        "dateOfBirth": "12/8/2023",
        "gender": "Female"
    }
}
```


### Get all suggestions
Endpoint : /dahsboard/suggestions \
Method : GET \
Description : Retrieves a list of all suggestions.
### Example Response 

```json
[
    {
        "id": 1,
        "normalUser": {
            "id": 32,
            "name": "Omar",
            "surName": "Ait Ouali",
            "phoneNumber": "053565286",
            "hashedPassword": "$2a$04$OnyWMjxoViu0pWtPOkRcle6qI.w3CaPigA9COgcZ9Y3xL3OOicLDq",
            "dateOfBirth": "1990-01-01",
            "gender": "Female"
        },
        "suggestionTitle": "Plastic Alternatives",
        "suggestionDescription": "Educate others on proper waste disposal practices",
        "creatAt": "2022-06-11T00:03:49"
    }
]


```
### Create Task 
Endpoint : /dashboard/tasks?reportId=123&assignerId=456&assignedId=789
Method : POST \
Description : Creates a task \
where : reportId = report of the id \
        assignerId = system user id \
        assignedID = driver id 
### Example Request 
```
/dashboard/tasks/?reportId=12&assignerId=42&assignedId=19
```
### Example Response
```
creation of task done with success 
```

### Modifiy task Driver
### Create Task 
Endpoint : /dashboard/tasks/{taskId}/modify-driver?assignedid=15
Method : Patch \
Description : Change the Driver assigned to task \
where : taskId = the task you want to change the driver to 
        assignedID = id of new driver
### Example Request 
```
/dashboard/tasks/6/modify-driver?assignedid=16
```
### Example Response
```
update of driver task done with success
```
### Get all citizens 
Endpoint: /dashboard/citizens \
Method: GET \
Description: Retrieves a list of all citizens.
#### Example Response 
```json
[
    {
        "id": 1,
        "name": "Mohammed",
        "surName": "Zerrouk",
        "phoneNumber": "057293386",
        "hashedPassword": "$2a$04$5ZbWjCpCbjs2hATpZaWobOAXWLh4gGhU4HZ54n73ty3IZm0Pge3zO",
        "dateOfBirth": "1990-01-01",
        "gender": "Male"
    },
    {
        "id": 2,
        "name": "Ali",
        "surName": "Belkadi",
        "phoneNumber": "059394539",
        "hashedPassword": "$2a$04$f1zorCM4jkCFYsha6I1H/OvG0heJRpXp5WOMrn8bh8VadbabFsL1m",
        "dateOfBirth": "1990-01-01",
        "gender": "Male"
    }
]
```
</details>


<details>
  <summary>
    <h2>Driver API</h2>
  </summary>
   this API is for Truck Drivers, it allows them to retrieve the list of all assinged tasks to them , as well as Update the status of their tasks 
  
  ### Get all Assigned Tasks 
Endpoint: /drivers/{driverId}/tasks \
Method: GET \
Description: Retrieves a list of all Tasks assigned for the driver. \
  driverId = the id that  Corresponds to the driver
  ### Example Request 
```
/drivers/9/tasks
```
#### Example Response 
```json
[
    {
        "id": 2,
        "report": {
            "id": 36,
            "reporterId": 2,
            "reportType": "not collected trash",
            "reportDescription": "Broken glass bottles on the sidewalk",
            "reportLocation": "RPWW+FV8 ،Biskra ،Algeria",
            "image": "picture1.png",
            "imagedata": "MHhGRkQ4RkZFMDAwMTA0QTQ2NDk0NjAwMDEwMTAwMDAwMTAwMDEwMDAw",
            "createdAt": "2023-07-17T17:02:45"
        },
        "status": "done",
        "createdAt": "2022-03-08T03:25:01",
        "finishedAt": "2020-07-24T21:18:30",
        "assingerSystemUser": {
            "id": 35,
            "name": "Ali",
            "surName": "Ait Ali",
            "phoneNumber": "051397260",
            "hashedPassword": "$2a$04$cJLdun3HPpi4WMnjeQK/JeCf1bQaYbSGgNnwnCOnagzzijocIdvUG",
            "dateOfBirth": "3/26/2024",
            "gender": "Female"
        }
    },
    {
        "id": 26,
        "report": {
            "id": 8,
            "reporterId": 15,
            "reportType": "too many trash",
            "reportDescription": "Piles of litter in the park",
            "reportLocation": "RPWW+FV8، Biskra، Algeria",
            "image": "picture1.png",
            "imagedata": "MHhGRkQ4RkZFMDAwMTA0QTQ2NDk0NjAwMDEwMTAwMDAwMTAwMDEwMDAw",
            "createdAt": "2022-11-15T09:28:59"
        },
        "status": "not done",
        "createdAt": "2021-11-14T08:26:39",
        "finishedAt": "2022-08-31T16:27:38",
        "assingerSystemUser": {
            "id": 6,
            "name": "Omar",
            "surName": "Bouzid",
            "phoneNumber": "058345065",
            "hashedPassword": "$2a$04$8nUV6SvHirRg4OWg1rLUeOzir.UC4gjkuXYy7U1w4fMA3m5anAvvC",
            "dateOfBirth": "1/29/2024",
            "gender": "Male"
        }
    }
]
```

### Update Task Status 
### Get all citizens 
Endpoint: /drivers/{driverId}/{taskId}/update-task-status  
Method: Patch 
Description: Update the status of the assigned Task
driverId = id of the driver
taskId = id of the task
### Example Request 
```
/drivers/8/9/update-task-status?status=done
```
### Example Response
```
task update status operation done with success
````
</details>



<details>
  <summary>
    <h2>
      Citizen API 
    </h2>
  </summary>
  
### Submit a Report
Endpoint: /citizens/report
Method: Post
Description: report Submission

### Example of Body Request 
```
{
    "report": {
        "id": 1,
        "reporterId": 123,
        "reportType": "Type A",
        "reportDescription": "Description of the report",
        "reportLocation": "Location of the report"
        "createAt: date of task creation "
    },
    "image": "<base64-encoded image data>"
}
```
### Submit a Suggestion
Endpoint: /citizens/suggestion
Method: Post
Description: Suggestion Submition

### Example of Body Request 
```
[
    "suggestion": {
        "id": 1 ,
        "reporterId": 123,
        "suggestionTitle": "Suggestion title",
        "suggestionDescription": "Description of the suggestion",
        "creatAt": "date of suggestion creation"
      
    }
    
```

```
report created successfully
```

### Response of Reqeust

```
Suggestion saved succesffully 
```
  
</details>


