---
title: "Get educationSubmittedSubmissionResource"
description: "Retrieve a submitted resource."
author: "Sureshpadimi88"
ms.localizationpriority: medium
ms.subservice: "education"
doc_type: apiPageType
---

# Get educationSubmittedSubmissionResource

Namespace: microsoft.graph

Retrieve a [submitted resource](../resources/educationsubmissionresource.md). Only teachers, students, and applications with application permissions can perform this operation.

Resources are available to a teacher or an application with application permissions after a student submits it, and are available to the student after the teacher returns the submission. Teachers can leave notes in some resources.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "educationsubmittedsubmissionresource_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/educationsubmittedsubmissionresource-get-permissions.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /education/classes/{id}/assignments/{id}/submissions/{id}/submittedResources/{id}
```

## Optional query parameters

This method supports the `$select` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).


## Request headers
| Header       | Value |
|:---------------|:--------|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body
Don't supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and an [educationSubmissionResource](../resources/educationsubmissionresource.md) object in the response body. Otherwise, returns a `404 Not found` response code.

## Example
### Request
Here's an example of the request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_educationsubmittedsubmissionresource"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/education/classes/f973bc68-2adb-4cf7-8b15-a57a1936b60c/assignments/8b890b42-a1df-478b-bff5-6814afb1afc2/submissions/6d71b348-898a-40cd-8e71-35127eed97f5/submittedResources/f2387c3b-ec39-4bf2-a399-d7242677f024
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-educationsubmittedsubmissionresource-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-educationsubmittedsubmissionresource-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-educationsubmittedsubmissionresource-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-educationsubmittedsubmissionresource-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-educationsubmittedsubmissionresource-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-educationsubmittedsubmissionresource-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-educationsubmittedsubmissionresource-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-educationsubmittedsubmissionresource-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
Here's an example of the response. 

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.educationResource"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "assignmentResourceUrl": "https://graph.microsoft.com/v1.0/drives/b!8-QjN2tsv0WyGnTv7vOvnQkmGHbbeMNLqYKONmHLVnvCVmBYIGpeT456457AdW9f/items/017NJZI25NOB5XZNLABF7646XAMDZTQQ6T",
  "id": "f2387c3b-ec39-4bf2-a399-d7242677f024",
  "resource": {
      "@odata.type": "#microsoft.graph.educationWordResource",
      "displayName": "Report.docx",
      "createdDateTime": "2017-10-21T07:52:53.9863696Z",
      "createdBy": {
          "application": null,
          "device": null,
          "user": {
              "id": "63cc91d2-59c7-4732-9594-35b91a26b340",
              "displayName": null
          }
      },
      "lastModifiedDateTime": "2017-10-21T07:52:53.9863696Z",
      "lastModifiedBy": {
          "application": null,
          "device": null,
          "user": {
              "id": "63cc91d2-59c7-4732-9594-35b91a26b340",
              "displayName": null
          }
      },
      "fileUrl": "https://graph.microsoft.com/v1.0/drives/b!8-QjN2tsv0WyGnTv7vOvnQkmGHbbeMNLqYKONmHLVnvCVmBYIGpeTZ_iul5AdW9f/items/017NJZI27BCN2QI2H7HJGLIVPXR6SD2DH6",
      "@odata.type": "microsoft.graph.educationResource"
  }
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Get educationSubmittedSubmissionResource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
