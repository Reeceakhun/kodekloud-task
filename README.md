# Project Nautilus

## Overview
Project Nautilus is the Naval subdivision of the xFusionCorp Industries. Nautilus Application helps the Naval forces to make smart procurement decisions of their manned or unmanned maritime systems while ensuring that the operational requirements are met. It also aims to provide the best-in-class operational support, improving the safety and life extension of existing machines and reducing the cost of ownership.

## Current Repertoire
- Sonar Technology and Systems
- LUSV - Large Unmanned Surface Vehicles
- Autonomous Unmanned Undersea Pods
- Nuclear Submarines
- Laser Guidance Systems

## Application Architecture
Nautilus deployment architecture can be viewed [here]([link_to_architecture](https://lucid.app/lucidchart/58e22de2-c446-4b49-ae0f-db79a3318e97/view?page=0_0#)).
https://lucid.app/lucidchart/58e22de2-c446-4b49-ae0f-db79a3318e97/view?page=0_0#
- **Data Tier:** The Data tier is the layer that stores data with the retrieval storage and execution methods made by the application layer. We are making use of MariaDB which is one of the most popular open-source relational databases.
- **Application Tier:** Makes use of a LAMP stack (Linux, Apache, MySQL, PHP) for web application development.
- **Client Tier:** Utilizes web browser software for processing and displaying HTML resources and managing HTTP requests and responses.
- **Load Balancer:** Nginx is used for HTTP Load Balancing to distribute requests through multiple application servers.

## Shared Services
- **Storage Filer:** A NAS (Network Attached Storage) filer is used to provide reliable and stable external storage for the application tier servers.
- **SFTP Server:** Utilized for transferring data among remote systems securely.
- **Backup Server:** A staging backup system used for short-term archival.
- **Jump Server:** Acts as an intermediary host or SSH gateway to a remote network hosting the Nautilus application.
