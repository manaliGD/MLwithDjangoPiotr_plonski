The demand for Machine Learning (ML) applications is growing. Many resources show how to train ML algorithms. However, the ML algorithms work in two phases:

the training phase - in which the ML algorithm is trained based on historical data,
the inference phase - the ML algorithm is used for computing predictions on new data with unknown outcomes.
The benefits for business are in the interference phase when ML algorithms provide information before it is known. There is a technological challenge on how to provide ML algorithms for inference into production systems. There are many requirements which need to be fulfilled:

ML algorithms deployment automation,
continuous-integration,
reproducibility of algorithms and predictions,
diagnostic and monitoring of algorithms in production,
governance and regulatory compliance,
scalability,
users collaboration.
There are many ways of how ML algorithms can be used:

The simplest approach is to run the ML algorithm locally to compute predictions on prepared test data and share predictions with others. This approach is easy and fast in implementation. However, it has many drawbacks. It is hard to govern, monitor, scale and collaborate.
The second, similar approach, is to hard-code the ML algorithm in the system's code. This solution is rather for simple ML algorithms, like Decision Trees or Linear Regression (which are easy to implement independently of the programming language). This solution behaves similar to the first approach - it is easy to implement with many drawbacks.
The third solution, it to make the ML algorithm available by REST API, RPC or WebSockets. This method requires the implementation of the server which handles requests and forwards them to ML algorithms. In this approach, all requirements for the ML production system can be fulfilled.
The last solution is to use a commercial vendor for deploying ML algorithms - it can be in the cloud or on-premise. Sometimes, this can be a good solution. When you have a standard ML algorithm so the vendor can handle it and you have money to pay to the vendor (it can be pricy).
This tutorial provides code examples on how to build your ML system available with REST API. In this book, for building the ML service I will use Python 3.6 and Django 2.2.4. This book is the first part that covers the basics which should be enough to build your ML system which:

can handle many API endpoints,
each API endpoint can have several ML algorithms with different versions,
ML code and artifacts (files with ML parameters) are stored in the code repository (git),
supports fast deployments and continuous integration (tests for both: server and ML code),
supports monitoring and algorithm diagnostic (support A/B tests),
is scalable (deployed with containers),
has a user interface.
There are many ways in which this tutorial can be extended, for example:

running long jobs for batch predictions or algorithm training with Celery,
running scheduled jobs with Celery,
WebSocket interface for Internet-of-Things applications (with Django Channels),
authentication and user management.
Right now, the above topics are not covered in this tutorial. I will consider writing them in the future based on the reader's feedback. You can send me feedback using this form.

In my opinion, building your ML system has a great advantage - it is tailored to your needs. It has all features that are needed in your ML system and can be as complex as you wish.

This tutorial is for readers who are familiar with ML and would like to learn how to build ML web services. Basic Python knowledge is required. The full code of this tutorial is available at: https://github.com/pplonski/my_ml_service.
