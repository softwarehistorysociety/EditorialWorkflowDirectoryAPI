# Workflow Directory API
- [**Source**](http://editorial-app.appspot.com/workflows/api)
- [Postman Source](https://www.dropbox.com/s/t1rggvrro6hx9n0/Editorial%20Workflow%20API.postman_collection.json?dl=0)
- [Postman Published Documentation](https://documenter.getpostman.com/view/15808119/2s93Y2ThGt)
- [**Postman Collection URL**](https://www.postman.com/extratone/workspace/juegos/collection/15808119-2fc33c51-e5ec-4084-98fe-462b253f7bf3?action=share&creator=15808119) - `https://www.postman.com/extratone/workspace/juegos/collection/15808119-2fc33c51-e5ec-4084-98fe-462b253f7bf3?action=share&creator=15808119`

The workflow directory has a simple, JSON-based API that allows you to get information about shared workflows programmatically, for example using a Python script.

## Search
Example:
`http://editorial-app.appspot.com/workflows/search?format=json&q=evernote`

Returns a dictionary with a single `workflows` key that contains the search results. Each search result is a dictionary with the following keys:

- `title` – the workflow's title
- `url` – the URL of the workflow's preview page (append `?format=json` to the URL to get information about the workflow in JSON format)
- `description` – the plain-text description of the workflow

## Recent Workflows
Example:

`http://editorial-app.appspot.com/workflows/recent?format=json&limit=20`

Returns a dictionary with a single `workflows` key that contains an array of the most-recently added workflows in the directory. The optional `limit` parameter can be used to set the maximum number of workflows that should be returned ::(capped at 1000, defaults to 100)::.

Each entry in the `workflows` array is a dictionary with the following keys:

- `title` – the workflow's title
- `url` – the URL of the workflow's preview page. Append `?format=json` to the URL to get information about the workflow in JSON format.
- `description` – the plain-text description of the workflow
- `install_url` – a special editorial:// URL that can be used to add this workflow on a device that has Editorial installed. This will typically be quite long, because the URL itself contains all the workflow's data.
- `workflow_data` – the JSON-formatted data of the workflow, as it is stored in the workflow (.wkflw) file on the device. The exact format of this data is not documented, and may change between versions.

## Workflow Info
Example:
`http://editorial-app.appspot.com/workflow/5642556234792960/vJn-7Jsqklo?format=json`

Returns information about a specific workflow. The workflow can be public or unlisted (if you know the URL).

The workflow information is returned as a dictionary with the following keys:

- `title` – the workflow's title
- `url` – the URL of the workflow's preview page. Append `?format=json` to the URL to get information about the workflow in JSON format.
- `description` – the plain-text description of the workflow
- `install_url` – a special editorial:// URL that can be used to add this workflow on a device that has Editorial installed. This will typically be quite long, because the URL itself contains all the workflow's data.
- `workflow_data` – the JSON-formatted data of the workflow, as it is stored in the workflow (.wkflw) file on the device. The exact format of this data is not documented, and may change between versions.](http://editorial-app.appspot.com/workflows/api)
