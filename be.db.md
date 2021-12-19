---
id: HQvbp0ITc7fy0AVVf2ncY
title: Db
desc: ''
updated: 1639852141889
created: 1639851497477
---

## [SQL vs NoSQL](https://www.integrant.com/when-to-use-sql-vs-nosql/)

## ElasticSearch and MongoDB

https://www.quora.com/What-are-the-main-differences-between-ElasticSearch-and-NoSQL-DBs-like-MongoDB-Do-you-think-these-two-technologies-products-would-have-more-similarities-than-differences-in-the-near-future

Elasticsearch is a standalone database. Its main use case is for searching text and text and/number related queries such as aggregations. Generally, it's not recommended to use Elasticsearch as the main database, as some operations such as indexing (inserting values) are more expensive compared to other databases.
You can use Elasticsearch along with any other database such as MongoDB or MySQL, where the other databases can act as the primary database, and you can sync Elasticsearch with your primary database for the "searchable" parts of the data.
Elasticsearch works well with a number of other products from Elastic such as Logstash for logging purposes and Kibana for visualization purposes.
Elasticsearch homepage has a well-written description of it and its main use cases.
