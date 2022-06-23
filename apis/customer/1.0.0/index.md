---
# NOTICE: Copyright 2022 Talend SA, Talend, Inc., and affiliates. All Rights Reserved. Customer’s use of the software contained herein is subject to the terms and conditions of the Agreement between Customer and Talend.
layout: "apiDefinition_1.1.0"
api-definition:
  specVersion: "4.1.0"
  info:
    name: "Customer"
    version: "1.0.0"
    description: "No description"
  contract:
    mediaTypes:
    - "application/json"
    sections:
    - name: "customer"
      elementOrder:
      - "#/contract/types/b9f400c8-0b0a-490c-8bcf-ae8a64427bec"
      - "#/contract/types/1877b79d-f7b6-4226-a0f2-e0633e9b4843"
      - "#/contract/resources/4fadbc0f-76a5-4bf2-97d4-6f83b5218e14"
    resources:
      "4fadbc0f-76a5-4bf2-97d4-6f83b5218e14":
        path: "/customer/{id}"
        section: "#/contract/sections/5497d6fe-c429-4c89-bb30-6ad429c60b39"
        pathVariables:
        - name: "id"
          type: "STRING"
          required: true
        operations:
          fb77194d-35b3-48f4-88f5-215bcc317935:
            name: "Get customer by ID"
            method: "GET"
            description: "Get customer information by its ID"
            headers:
            - name: "Content-Type"
              type: "STRING"
              required: false
              examples:
              - value: "application/json"
            responses:
              "321bf2c7-fcad-4de7-b12d-b45d7ef0bb2a":
                status: "200"
                description: "Status Code 200"
                headers:
                - name: "Content-Type"
                  type: "STRING"
                  required: false
                  examples:
                  - value: "application/json"
                bodies:
                - type: "#/contract/types/1877b79d-f7b6-4226-a0f2-e0633e9b4843"
                  examples:
                  - value: "{\"customer\":{\"AverageResolutionDays\":2,\"Priority\":\"Low\",\"SFDC_accountId\":100001,\"OpenTickets\":0,\"CreditCard\":\"1212-1221-1121-1234\",\"Name\":\"Abernathy-Bernier\",\"BillingState\":\"Virginia\",\"BillingPostalCode\":75565,\"Phone\":\"740-714-1041\",\"Industry\":\"Agriculture & Forestry\",\"CreatedDate\":\"15-03-2021\",\"LastDelivery__c\":\"21-01-2021\",\"EmailContact__c\":\"dexter.yundt@yahoo.com\"}}"
                  mediaTypes:
                  - "application/json"
              "35bd4730-978f-4daf-a7e6-2287081e7f02":
                status: "404"
                description: "Status Code 404"
                bodies:
                - type: "OBJECT"
                  properties:
                  - name: "customer"
                    type: "OBJECT"
                    required: false
                    properties:
                    - name: "message"
                      type: "STRING"
                      description: "Error message"
                      required: false
    types:
      b9f400c8-0b0a-490c-8bcf-ae8a64427bec:
        name: "Priority"
        type: "STRING"
        description: "Priority level"
        section: "#/contract/sections/5497d6fe-c429-4c89-bb30-6ad429c60b39"
        enum:
        - "Low"
        - "Moderate"
        - "High"
      "1877b79d-f7b6-4226-a0f2-e0633e9b4843":
        name: "customer"
        type: "OBJECT"
        description: "Customer generic JSON document"
        section: "#/contract/sections/5497d6fe-c429-4c89-bb30-6ad429c60b39"
        required: false
        properties:
        - name: "customer"
          type: "OBJECT"
          required: false
          properties:
          - name: "AverageResolutionDays"
            type: "NUMBER"
            description: "Average number of days support resolved open issues for the given customer"
            required: false
          - name: "Priority"
            type: "#/contract/types/b9f400c8-0b0a-490c-8bcf-ae8a64427bec"
            required: false
          - name: "SFDC_accountId"
            type: "NUMBER"
            required: false
          - name: "OpenTickets"
            type: "NUMBER"
            required: false
          - name: "CreditCard"
            type: "STRING"
            required: false
          - name: "Name"
            type: "STRING"
            required: false
          - name: "BillingState"
            type: "STRING"
            required: false
          - name: "BillingPostalCode"
            type: "NUMBER"
            required: false
          - name: "Phone"
            type: "STRING"
            required: false
          - name: "Industry"
            type: "STRING"
            required: false
          - name: "CreatedDate"
            type: "STRING"
            required: false
          - name: "LastDelivery__c"
            type: "STRING"
            required: false
          - name: "EmailContact__c"
            type: "STRING"
            required: false
        examples:
        - value: "{\"customer\":{\"AverageResolutionDays\":2,\"Priority\":\"Low\",\"SFDC_accountId\":100001,\"OpenTickets\":0,\"CreditCard\":\"1212-1221-1121-1234\",\"Name\":\"Abernathy-Bernier\",\"BillingState\":\"Virginia\",\"BillingPostalCode\":75565,\"Phone\":\"740-714-1041\",\"Industry\":\"Agriculture & Forestry\",\"CreatedDate\":\"15-03-2021\",\"LastDelivery__c\":\"21-01-2021\",\"EmailContact__c\":\"dexter.yundt@yahoo.com\"}}"
  components: {}
api-tryin: |-
  {
    "version" : 6,
    "entities" : [ {
      "entity" : {
        "type" : "Project",
        "name" : "Customer 1.0.0",
        "description" : "No description",
        "importedFrom" : "fe01eaee-62c3-4a4f-b249-2c58d8ebcca4"
      },
      "children" : [ {
        "entity" : {
          "type" : "Service",
          "name" : "customer"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "fb77194d-35b3-48f4-88f5-215bcc317935",
            "name" : "Get customer by ID",
            "description" : "Get customer information by its ID",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/customer/{id}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form"
          }
        } ]
      } ]
    } ],
    "environments" : [ {
      "name" : "Customer 1.0.0",
      "importedFrom" : {
        "projectId" : "fe01eaee-62c3-4a4f-b249-2c58d8ebcca4"
      },
      "variables" : {
        "7526e0d0-8e08-4c5b-9220-e2025d2dd418" : {
          "name" : "BaseUrl",
          "value" : "https://example.com",
          "enabled" : true,
          "private" : false
        }
      }
    } ]
  }
---
