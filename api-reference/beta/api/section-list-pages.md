---
title: "List pages"
description: "Retrieve a list of page objects from the specified section."
ms.localizationpriority: medium
author: "jewan-microsoft"
ms.subservice: "onenote"
doc_type: apiPageType
---

# List pages

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve a list of [page](../resources/onenotepage.md) objects from the specified section.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "section_list_pages" } -->
[!INCLUDE [permissions-table](../includes/permissions/section-list-pages-permissions.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /me/onenote/sections/{id}/pages
GET /users/{id | userPrincipalName}/onenote/sections/{id}/pages
GET /groups/{id}/onenote/sections/{id}/pages
GET /sites/{id}/onenote/sections/{id}/pages
```
## Optional query parameters
This method supports the [OData Query Parameters](/graph/query-parameters) to help customize the response.

The default query for pages returns the top 20 pages ordered by `lastModifiedTime desc`. If the default query returns more than 20 pages, the response contains an `@odata.nextLink` that you can use to page through the result set. The maximum number of pages returned for a `top` request is 100.

The default response expands `parentSection` and selects the section's `id`, `name`, and `self` properties. Valid `expand` values for pages are `parentNotebook` and `parentSection`.

## Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer {token}. Required. |
| Accept | string | `application/json` |

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [onenotePage](../resources/onenotepage.md) objects in the response body.
## Example
##### Request
Here's an example of the request.
<!-- { "blockType": "ignored" } -->
```http
GET https://graph.microsoft.com/beta/me/onenote/sections/{id}/pages
```
##### Response
Here's an example of the response. Note: The response object shown Here's truncated for brevity. All of the properties will be returned from an actual call.
<!-- { "blockType": "ignored" } -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": [
    {
      "title": "title-value",
      "createdByAppId": "createdByAppId-value",
      "links": {
        "oneNoteClientUrl": {
          "href": "href-value"
        },
        "oneNoteWebUrl": {
          "href": "href-value"
        }
      },
      "contentUrl": "contentUrl-value",
      "content": "content-value",
      "lastModifiedDateTime": "2016-10-19T10:37:00Z"
    }
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "List pages",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
