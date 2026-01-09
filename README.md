# Technical Test

A Spring Boot Kotlin application for managing energy asset activations.

## Overview

This application handles activation requests in the activation bounded context. It selects assets based on requested volume using a greedy algorithm and returns the allocation across available assets.

## Prerequisites

- Java 17
- Maven 3.x
- Docker (optional, for containerized deployment)

## Building the Application

```bash
./mvnw clean package
```

## Running the Application

### Locally

```bash
./mvnw spring-boot:run
```

The server will start on port **8000**.

### Using Docker Compose

```bash
docker-compose up --build
```

## API

### Create Activation

**POST** `/api/v1/activations`

**Request Body:**
```json
{
  "volumeInKw": 1500,
  "date": "2024-01-01"
}
```

**Response:**
```json
[
  {
    "assetId": "asset-1",
    "activatedVolumeInKw": 1000
  },
  {
    "assetId": "asset-2",
    "activatedVolumeInKw": 500
  }
]
```

## Data Storage

Assets are stored in a PostgreSQL database with UUID primary keys.

## Documentation

- [Architecture Committee Notes](architecture-committee.md) - Technical decisions and specifications
