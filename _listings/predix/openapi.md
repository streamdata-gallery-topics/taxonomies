swagger: "2.0"
x-collection-name: Predix
x-complete: 1
info:
  title: VIEWS
  version: 1.0.0
host: thetaray-anomaly-service.run.aws-usw02-pr.ice.predix.io
basePath: /v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /api/v1/catalog/taxonomy:
    get:
      summary: Retrieve the full taxonomy.
      description: This operation retrieves the full taxonomy structure from the catalog.
      operationId: retrieveFullTaxonomy
      x-api-path-slug: apiv1catalogtaxonomy-get
      responses:
        2:
          description: Successful response
      tags:
      - Retrieve
      - Full
      - Taxonomy
    post:
      summary: Load a taxonomy.
      description: This operation loads the supplied taxonomy structure into catalog.
        If a taxonomy already exists in the catalog, new paths in the supplied structure
        will be added. It will not delete existing paths.
      operationId: loadTaxonomy
      x-api-path-slug: apiv1catalogtaxonomy-post
      parameters:
      - in: body
        name: body
        description: taxonomy JSON request
        schema:
          $ref: '#/definitions/holder'
      responses:
        2:
          description: Successful response
      tags:
      - Load
      - Taxonomy