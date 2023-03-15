---
# layout: page
title: PostgreSQL, strategic platform
permalink: /postgres/
---

PRODATA Ltd. strategically incorporated PostgreSQL into its enterprise data management platform and solutions, recognizing the numerous benefits that come with utilizing open source software (OSS) when implementing a new system.

By adopting PostgreSQL, PRODATA Ltd. has gained access to a powerful, reliable, and feature-rich object-relational database system that has undergone over 35 years of active development. This robust system not only enhances the functionality and performance of the software solution but also provides a cost-effective and scalable solution for managing data.

The decision to use PostgreSQL in the development of the software solution reflects PRODATA Ltd.'s commitment to providing the highest quality service to its growing customer base. The utilization of OSS allows the company to be agile and responsive to the evolving needs of its customers while maintaining a high level of security, stability, and data integrity.

In summary, PostgreSQL plays a strategic role in the development of PRODATA Ltd.'s software solution by providing a reliable and feature-rich database system that enhances the solution's functionality and performance. By choosing to use OSS, the company can remain agile and responsive to its customers' needs while maintaining a high level of security, stability, and data integrity.

As part of its strategic platform, PRODATA Ltd. proposes to implement an open-source DBMS PostgreSQL for the persistent data layer of its software solution. This DBMS is capable of ensuring high robustness, scalability, and security, thereby increasing the availability of persistent data.

To implement the database solution, PRODATA Ltd. also proposes to use an indirect model maintenance approach based on Object-Relational Mapping (ORM) using the web application framework Django. ORM is a technique that allows users to query and manipulate data from a database using an object-oriented paradigm. By using ORM, the company can interact directly with objects in the same language of choice, rather than using SQL and DBMS-dependent primitives. This provides a higher degree of re-usability for the implementation of REST API services.

Overall, the combination of PostgreSQL and ORM-based indirect model maintenance provides an effective and efficient solution for the persistent data layer implementation of PRODATA Ltd.'s software solution. This approach enables the company to benefit from the robustness, scalability, and security of PostgreSQL while also simplifying the interaction with the database through the use of ORM. The resulting solution is highly adaptable and reusable, providing a solid foundation for future development and expansion of the software solution.

![DB High Availability (HA) using continuous archiving, log-shifting, and streaming replication](/assets/images/postgres/db_reliability.png "DB High Availability (HA) using continuous archiving, log-shifting, and streaming replication")

PostgreSQL's continuous archiving feature provides a reliable and effective means of creating a high availability (HA) cluster configuration. By utilizing one or more standby servers, this approach ensures that if the primary server fails, the standby servers can quickly take over operations. This capability is commonly referred to as warm standby or log shipping.

As part of its strategic platform, PRODATA Ltd. recognizes the importance of high availability and reliability for its software solutions. To achieve this, the company proposes to utilize PostgreSQL's continuous archiving and streaming replication features to implement a HA cluster configuration.

By utilizing continuous archiving, PRODATA Ltd. can create standby servers that are ready to take over operations if the primary server fails, ensuring minimal downtime and uninterrupted business continuity. Additionally, by incorporating streaming replication, standby servers can stay more up-to-date than is possible with file-based log shipping. This approach allows standby servers to be kept up-to-date in real-time, providing a more reliable and robust solution for high availability.

Overall, the use of continuous archiving and streaming replication features in PostgreSQL as a strategic platform provides PRODATA Ltd. with a highly effective and reliable solution for achieving high availability and minimizing downtime. By implementing these features, the company can ensure business continuity, minimize the risk of data loss, and provide its customers with a high-quality and dependable software solution.

More about PostgreSQL DBMS you can find at [www.postgresql.org](https://www.postgresql.org/)
