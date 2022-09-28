# microservice_workshop

Copyright (c) 2015-2022 by Fred George  
@author Fred George  fredgeorge@acm.org  
May be copied with this notice, but not used in classroom training.

## About the Class

This is a programming workshop. You will be writing multiple MicroServices in just
a few hours. Bring your notebook computer and your favorite IDE. Multiple languages
are supported (see below). 

The techniques we cover are particularly appropriate for _"fuzzy"_ problems. That is, 
problems for which the perfect answer does not exist. Think about these domains:

- Should I loan you money?
- Is this a fraudulent transcation?
- Which stock should I buy?
- What is the most effective Google ad?

In each of these types of problems, no perfect answer exists in general. 
Thus, a highly de-coupled, experiment-friendly, rapid-deployment environment
is best. That is what we will be doing in this workshop.

We will be using _Rapids, Rivers, and Ponds_-based frameworks. These frameworks
provide a simple API to the event bus. Only relevant messages are received by the
MicroService, keeping the MicroService implementation simple and small. This
architecture is experiment-friendly and supports rapid development and deployment.

After a brief introduction, we will get the Sample MicroServices working with an 
event bus: RabbitMQ for this class. Then we will begin to layer on new requirements, 
each addressed by one or more new MicroServices. You will work with a partner initially,
although each of you should run the MicroServices on your machine, but sharing an
instance of the event bus! If your partner uses a different language, ___great___! It
doesn't matter in MicroServices.

After lunch, we will form larger teams, and start to work on harder problems. You will
design the solutions as a team, then break up to implement the various solutions.

We will stop the class periodically to check progress. Most of the key lessons are
intentially discovered in the course of writing these MicroServices.

## Before Class...

Before the class, attendees should install and compile the framework 
and sample code for the language they will be using. Libraries 
(DLL's, Gems, etc) can then be preloaded before class without
relying on spotty Internet connectivity in class. The repositories are linked here, but
are also available on http://github.com/fredgeorge directly.

Also since tools vary, detailed instructions for getting the code to run in your
chosen environment is difficult. It's best if you don't spend valuable class time
trying to get the code to run.

Occassionally attendee machines have been locked down in various ways by their company. 
Again, it is best to wrestle with these issues before class.

Optionally, RabbitMQ can be installed locally (natively or via Docker). The instructor
will provide instances of RabbitMQ if this is not feasible.

## Language Sample Setup

The starting code is designed to allow attendees to quickly begin designing and developing
new MicroServices. The following languages have a Rapids, Rivers, and Ponds
framework with two sample MicroServices:

- Kotlin (https://github.com/fredgeorge/rapids_rivers_in_kotlin)
- Java (using Kotlin engine) (https://github.com/fredgeorge/rapids_rivers_in_kotlin)
- C# (https://github.com/fredgeorge/rapids_rivers_in_csharp)
- Python 3 (https://github.com/fredgeorge/rapids_rivers_in_python)
- TypeScript (https://github.com/fredgeorge/rapids_rivers_in_typescript)
- JavaScript (using TypeScript engine) (https://github.com/fredgeorge/rapids_rivers_in_typescript)

See the README.md files in each of the language-specific directories for setup instructions.

While some attendees have tried other languages (native JavaScript and Clojure, among others),
they have never caught up to the rest of the class. I strongly recommend you adopt one of
thes supported languages for the class.

## RabbitMQ

RabbitMQ is used as the asynchronous message bus in the workshop. The instructor 
will have instances of RabbitMQ running under Docker on the instructor's
machine. This does require attendees to attach wirelessly to the instructor's machine,
and the Wifi load can be troublesome at times.

Alternatively if you have Docker installed locally, attendees can bring up their own
RabbitMQ instances. Please use the standard rabbitmq:management pull.

Also, please make sure to configure your system to allow external access to your own
RabbitMQ. Pairs share instances of RabbitMQ, and most OS will block the ports by default.

## Service operation

Regardless of language, the startup parameters for the two initial services
(Monitor and Need) are the same:

- IP address of RabbitMQ
- Port of RabbitMQ

By default, RabbitMQ uses port 5672 for access and 15672 for its management console.

The Docker instances of the instructor's machine have remapped the ports for each
instance of RabbitMQ to:

- 56xx (xx = 73-85) for RabbitMQ access, and
- 156xx (xx = 73-85) for management console

This instructor will provide the pair with which port they should be sharing.

For the admin console, RabbitMQ uses _guest_ for the user id and password.
