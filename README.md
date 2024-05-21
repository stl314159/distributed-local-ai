# README.md

## Project Structure

This project is structured as follows:

```
.env
.env.example
.gitignore
conf/
	litellm/
		config.yaml
		config.yaml.example
data/
	litellm/
	postgres/
	redis/
		log/
docker-compose.yml
```

## Description

This project uses Docker to manage its services, including `litellm`, `postgres`, and `redis`. The configuration for these services is stored in the `conf/` directory, and persistent data is stored in the `data/` directory.

### litellm

`litellm` is a key component of this project. It is a custom service designed to manage and distribute local AI models across different nodes in a network. 

The primary goal of `litellm` is to facilitate the use of AI models in a distributed manner, allowing for efficient use of resources and improved performance. It does this by managing the lifecycle of AI models, including their distribution, updates, and usage tracking.

`litellm` works in conjunction with other services in this project, such as `postgres` for data storage and `redis` for caching, to provide a comprehensive solution for distributed AI model management.

Use cases for `litellm` include but are not limited to:

- Distributing AI models to edge devices in an IoT network for local inference, reducing the need for constant communication with a central server.
- Managing updates to AI models in a distributed system, ensuring all nodes are using the most recent and accurate models.
- Tracking usage and performance of AI models across different nodes, providing valuable data for model improvement and system optimization.

In this project, `litellm` is configured via the `config.yaml` file in the `conf/litellm/` directory. This configuration file allows you to specify details about the AI models being used, the nodes in the network, and other settings related to the operation of the `litellm` service.

## Usage

1. Copy the `.env.example` file to `.env` and fill in any necessary environment variables.

```sh
cp .env.example .env
```

2. Copy the `config.yaml.example` file to `config.yaml` and fill in any necessary configuration.

```sh
cp conf/litellm/config.yaml.example conf/litellm/config.yaml
```

3. Start the services with Docker Compose.

```sh
docker-compose up
```

Please note that you need to have Docker and Docker Compose installed on your machine to run this project.