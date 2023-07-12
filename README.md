# Codeflix: Video Streaming System Architecture

This repository showcases the software architecture diagram for a video streaming system called Codeflix. The architecture diagram provides an overview of the system's components and their interactions, helping to understand the system's structure and flow of data.

## Architecture Diagram

The architecture diagram is created using PlantUML and follows the C4 model, which provides a simple and concise way to visualize software architecture. The diagram illustrates the main components of the Codeflix system and their relationships.

![codeflix-diagram](https://github.com/jmtosto/codeflix-system-architecture/assets/48574634/b425195c-2351-4c85-a9de-dde54197cd11)

## Components

The Codeflix system consists of the following main components:

### Catalog Management
The Catalog Management component handles the management of the video catalog, including video categories. It comprises the following containers:
- **Catalog Admin Web**: A React-based web application that allows catalog administrators to manage the video catalog.
- **Catalog Admin API**: A Node.js-based API that manages the video catalog. It communicates with the Catalog Admin Web and the Catalog Admin DB.
- **Catalog Admin DB**: A MySQL database that stores catalog data.
- **Encoder Service**: A Go-based service responsible for encoding videos to MPEG-DASH format.
- **Raw Catalog Storage**: A GCP Bucket that stores raw videos.
- **Encoded Catalog Storage**: A GCP Bucket that stores encoded videos.

### Codeflix
The Codeflix component provides the main functionality of the video streaming platform for subscribers. It includes the following containers:
- **Codeflix Web**: A React-based web application that allows subscribers to search the catalog and play videos.
- **Codeflix Catalog API**: A Node.js-based API that provides catalog search and video playback functionality. It interacts with the Codeflix Catalog DB.
- **Codeflix Catalog DB**: An Elasticsearch database that stores Codeflix catalog data.
- **Codeflix Catalog Sync Service**: A Kafka Connect-based service responsible for syncing Codeflix catalog data. It interacts with the Catalog Admin DB and the Codeflix Catalog DB.
- **Codeflix Catalog Message Broker**: An Apache Kafka-based message broker that stores and serves data provided by the catalog sync service.

### Subscription Management
The Subscription Management component handles the management of subscribers and subscription plans. It consists of the following containers:
- **Subscription Management API**: A Node.js-based API that manages subscriptions. It communicates with the Subscription Management DB.
- **Subscription Management DB**: A PostgreSQL database that stores subscriber and plan data.

### Authentication
The Authentication component provides authentication functionality for all system users. It includes the following container:
- **Auth Service**: A Keycloak-based service responsible for authenticating all system users. It is used by the Subscription Management API, Codeflix Web, and Catalog Admin Web.

## Usage

You can use the diagram to gain a high-level understanding of the Codeflix video streaming system's architecture, including its components and their interactions.

## Contributing

If you would like to contribute to this project, please follow the standard guidelines for pull requests and contributions. Contributions may include bug fixes, improvements to the diagram, or additional documentation.

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use the architecture diagram for personal or commercial purposes.
