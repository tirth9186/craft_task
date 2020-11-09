# craft_task
Mule application created to transform data in particular form.
```
Introduction
  -> In this mule application two mule flows have been created for two different usecases. 
  -> To listen for events HTTP listener is being used, two **REST endpoints** are created.
  -> The REST endpoints are as follows: **i) /task/usecase1, ii) /task/usecase2.**
  -> Both of the endpoints are accepting only **POST** requests.
  -> The application is being hosted in localhost on the **port 8081.**


Usecase 1:
sample input:
[{"id":"101","name":"Ted1","company":"google"},
 {"id":"102","name":"Ted2","company":"microsoft"}, 
 {"id":"103","name":"Ted3","company":"craft"},
 {"id":"104","name":"Ted4","company":"google"}, 
 {"id":"105","name":"Ted5","company":"craft"},
 {"id":"106","name":"Ted6","company":"ibm"},
 {"id":"107","name":"Ted7","company":"microsoft"},
 {"id":"108","name":"Ted8","company":"google"}
]
sample output:
[{"company":"google","no_employees":"3"},
{"company":"craft","no_employees":"2"},
{"company":"microsoft","no_employees":"2"},
{"company":"ibm","no_employees":"1"}]


UseCase 2:
sample input:
[{"id":"101","name":"Ted1","company":"google"},
 {"id":"102","name":"Ted2","company":"microsoft"},
 {"id":"103","name":"Ted3","company":"craft"}, 
{"id":"104","name":"Ted4","company":"google"},
 {"id":"105","name":"Ted5","company":"craft"},
{"id":"106","name":"Ted6","company":"ibm"},
{"id":"107","name":"Ted7","company":"microsoft"},
{"id":"108","name":"Ted8","company":"google"},
]
sample output:
google:101|Ted1*104|Ted4*108|Ted8~
microsoft:102|Ted2*107|Ted7~
craft:103|Ted3*105|Ted5~
ibm:106|Ted6~```
