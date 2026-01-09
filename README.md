# Technical Test

A Spring Boot application for managing energy asset activations.

## Overview

This application handles activation requests in the activation bounded context. It selects assets based on requested volume and returns the allocation across available assets.

## API

### Create Activation

**POST** `/api/v1/activations`

**Request Body:**
```json
{
  "volumeInKw": 1500,
  "date": "2024-01-01T10:00:00Z"
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
