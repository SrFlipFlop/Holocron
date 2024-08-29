# OctoPaul
In the ever-evolving field of cybersecurity, staying informed is essential, but the sheer volume of information can be overwhelming. This project aims to simplify the process by aggregating open data from various sources and utilizing AI to summarize, evaluate, and organize it based on relevant keywords. The objective is to make it easier and faster to find the most important and relevant information.

*Disclaimer:On top of that, I’m using this project as a way to dive deeper into AI and sharpen my programming skills in Go. It’s a fun way to learn while building something useful!*

## Initial blueprint
As it is a learning project, I think it is important that the different components are modular so that they can be modified without affecting the whole system. The main parts will be:
- **Crawlers** (tentacles): there will be multiple crawlers to ingest information from different sources and store the data into a shared bus like Kafka or RabbitMQ (they also will have to control repeated information from different sources).
- **IA** (brain): the artificial intelligence models will process the information from the bus and store it in the DB (I would like to use multiple local or remote models for different purposes).
- **Database**: the database will contain metadata of the different blogs (source, date, tags, rating, ...) and a summary of the content in markdown format that could be consulted from a web application.

![Diagram](https://github.com/user-attachments/assets/12703e93-02f6-40c4-be3f-fdc9e9fc3aaf)

I'm still not sure if I'm going to use a workflow management platform for the crawlers or if the environment is going to be on-premise or in the cloud (for example using Lambda functions and RDS plus S3), but I want to start with the most basic functionality to make a proof of concept and keep moving forward little by little.

## Tentacles

## Brain

## Database
