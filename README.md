# Holocron
In the ever-evolving field of cybersecurity, staying informed is essential, but the sheer volume of information can be overwhelming. This project aims to simplify the process by aggregating open data from various sources and utilizing AI to summarize, evaluate, and organize it based on relevant keywords. The objective is to make it easier and faster to find the most important and relevant information.

## Initial blueprint
As it is a learning project, I think it is important that the different components are modular so that they can be modified without affecting the whole system. The main parts will be:
- **Crawlers**: there will be multiple crawlers to ingest information from different sources and store the data into a shared bus like Kafka or RabbitMQ (they also will have to control repeated information from different sources).
- **IA**: the artificial intelligence models will process the information from the bus and store it in the DB (I would like to use multiple local or remote models for different purposes).
- **Database**: the database will contain metadata of the different blogs (source, date, tags, rating, ...) and a summary of the content in markdown format that could be consulted from a web application.

![Diagram](https://github.com/user-attachments/assets/12703e93-02f6-40c4-be3f-fdc9e9fc3aaf)

I'm still not sure if I'm going to use a workflow management platform for the crawlers or if the environment is going to be on-premise or in the cloud (for example using Lambda functions and RDS plus S3), but I want to start with the most basic functionality to make a proof of concept and keep moving forward little by little.

### Brain
For the content analysis I want to test different options to see which is the most optimal in performance and cost. From using an online payment model, using a local model on the same machine or distributed (for cases of less powerful graphics), an hybrid solution that uses both models for different stages of the analysis, ... In any case I would like it to be modular and at the end it could be possible to use different options for each case.

Daniel Miessler's [**fabric**](https://github.com/danielmiessler/fabric) project can be of great help as it contains a large number of prompts (*patterns*) and allows you to connect with different models. At first I'm going to manually test **fabric** to see if it can fit in the project, and then I'm going to see how it could interact programmatically with another language (either by creating a Python library or modifying the project to have an API).

### Tentacles
- LinkedIn
- Telegram
- X (Twitter)
- Email newsletter

### Database
For the database I think is best to split the content in a non-relational database (such as mongodb or elasticsearch), and use a relational database to control what content has been ingested and not repeat the analysis.

## Purpose
1) Sumarize
2) Categorize
3) Extract keywords
4) Extract take-aways
5) Rate the content
6) Relate with other content