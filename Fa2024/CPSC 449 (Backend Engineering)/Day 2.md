We will be using Python 3.11
- "batteries-included" programming language


# Web Architecture
client <--> server
- communications occur in HTTP(S)
- client makes **requests**
	- ie. web browser; user agent
- server creates **responses** to requests
	- may contact other **database** systems to formulate the response

The "three-tier" system:
- client
- server
- databases
Old concept; still mostly applies today
- servers typically also respond with data (JSON, XML, etc.) in addition to frontend-rendered content (HTML, CSS, JS)

<u>Framework types</u>
Model-View-Controller (MVC)
- Django
Micro-framework - handles simpler tasks
- FAST API, Flask
- ex: map a request's path directly to a Python function

<u>Backend types</u>
Monolithic: all API calls (GET /a/b/c, PUT /d/e/f, etc.) are handled by **one** application
- one program, running on one machine
Microservice: each function/API call belongs to a particular service (their own program)
- lets each service be deployed on separate hosts
- each service might have their own DB
- ***flexibility***
"Server-less": abstracts the API-call to code pipeline
- everything in the middle is handled by some service provider
- "functions as a service"
- developer has less control over deployment: a pro *and* a con