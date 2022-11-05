# System Design Notes

These notes started when I was looking for a way to keep up a diary from my readings about computer science topics when working as an associate researcher at [Northeastern University](https://www.northeastern.edu/).

During that time we were in need to scale up a system to serve more users than we were used to. However, before throwing money into cloud services, we first needed to find a solution to to simulate multiple requests and check how our solution would handle that level of stress. 

We ended up using [Apache JMeter](https://jmeter.apache.org/). It allowed us to control the request simulation as we would by scripting user's performance. We could check the path the requests were taking inside the cloud provider machines, the API services it was using and the reasons behind eventual crashes. 

In this process, many of my notes were lost. I then decided to restart this habit and keep them here for data persistence, distribution, easy access and learning.
