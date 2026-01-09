# Technical details

A new SpringBoot application will be created, called "Technical Test"

The implementation will be done in the activation bounded context.

The request will be received using an HTTP endpoint: `POST /api/v1/activations` with body 

```json
{
  "volumeInKw": 1500,
  "date": "2024-01-01T10:00:00Z"
}
```

The answer will contain the list of selected assets with their id and the selected volume for each asset, for example

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

Assets will be stored in PostgreSQL database, no need to implement the CRUD now, assets will be manually added for testing.

The primary key for assets will be an id of type UUID.
