<h1 id="contenta-jsonapi-project">
  Contenta JSON API Project
  <img align="right" src="./logo.svg" alt="Contenta logo" title="Contenta logo" width="100">
</h1>

This repository is used in order to create a Contenta CMS project using Composer.

If you want to learn how to install Contenta CMS visit http://www.contentacms.org/#install. If you
want documentation about Contenta CMS visit http://www.contentacms.org.

# Prerequisite
This project requires Lando. See https://docs.lando.dev/basics/installation.html for installation.

# Installation
* Clone this repository
* Navigate to the code directory
* Run: `lando start`
* Import the database: `lando db-import assets/content.sql.gz`

# Contenta Address
After running `lando start` the address should be available in the last part of the logs. Take note that the port is random.
![image](https://user-images.githubusercontent.com/820842/136503532-4ed89c17-0fa4-47b6-b38c-4cdba0fb41c0.png)


# Accessing the API
Once you're logged in you can access the API page here: http://localhost:[PORT]/admin/api

# Example of endpoints

## `GET`
Get all articles - http://localhost:[PORT]/api/articles

Get all pages - http://localhost:[PORT]/api/pages

Get all content types - http://localhost:[PORT]/api/contentTypes

## For getting specific content: `GET`
Get specific article - http://localhost:[PORT]/api/articles/{entity}

entity = The uuid of the node article

## `POST`
Create new article - http://localhost:[PORT]/api/articles

Payload:
 ```
 {
  "data": {
    "type": "articles",
    "id": "string",
    "attributes": {
      "internalId": 0,
      "isPublished": true,
      "title": "string",
      "createdAt": "string",
      "updatedAt": "string",
      "isPromoted": true,
      "revision_default": true,
      "path": "string",
      "body": {
        "value": "string",
        "format": "string",
        "summary": "string"
      }
    },
    "relationships": {
      "contentType": {
        "data": {
          "type": "contentTypes",
          "id": "string"
        }
      },
      "owner": {
        "data": {
          "type": "users",
          "id": "string"
        }
      },
      "image": {
        "data": {
          "type": "images",
          "id": "string"
        }
      },
      "tags": {
        "data": [
          {
            "type": "tags",
            "id": "string"
          }
        ]
      }
    },
    "links": {
      "property1": {
        "href": "string",
        "meta": {}
      },
      "property2": {
        "href": "string",
        "meta": {}
      }
    },
    "meta": {}
  },
  "meta": {},
  "links": {
    "property1": {
      "href": "string",
      "meta": {}
    },
    "property2": {
      "href": "string",
      "meta": {}
    }
  },
  "jsonapi": {
    "version": "string",
    "meta": {}
  }
}
```

## `DELETE`
Delete an article - http://localhost:[PORT]/api/articles/{entity}

entity = The uuid of the node article

## `PATCH`
Update the article - http://localhost:[PORT]/api/articles/{entity}

entiy = The uuid of the node article

Payload:
```
{
  "data": {
    "type": "articles",
    "id": "string",
    "attributes": {
      "internalId": 0,
      "isPublished": true,
      "title": "string",
      "createdAt": "string",
      "updatedAt": "string",
      "isPromoted": true,
      "revision_default": true,
      "path": "string",
      "body": {
        "value": "string",
        "format": "string",
        "summary": "string"
      }
    },
    "relationships": {
      "contentType": {
        "data": {
          "type": "contentTypes",
          "id": "string"
        }
      },
      "owner": {
        "data": {
          "type": "users",
          "id": "string"
        }
      },
      "image": {
        "data": {
          "type": "images",
          "id": "string"
        }
      },
      "tags": {
        "data": [
          {
            "type": "tags",
            "id": "string"
          }
        ]
      }
    },
    "links": {
      "property1": {
        "href": "string",
        "meta": {}
      },
      "property2": {
        "href": "string",
        "meta": {}
      }
    },
    "meta": {}
  },
  "meta": {},
  "links": {
    "property1": {
      "href": "string",
      "meta": {}
    },
    "property2": {
      "href": "string",
      "meta": {}
    }
  },
  "jsonapi": {
    "version": "string",
    "meta": {}
  }
}
```
