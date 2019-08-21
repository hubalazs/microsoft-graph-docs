---
title: "user: checkMemberObjects"
description: "Check for membership in a list of group, directory role, or administrative unit objects for the specified user object."
localization_priority: Normal
author: "davidmu1"
ms.prod: "microsoft-identity-platform"
doc_type: "apiPageType"
---

# user: checkMemberObjects

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Check for membership in a list of group, directory role, or administrative unit objects for the specified user object. The check is transitive.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | User.ReadBasic.All and Group.Read.All, User.Read.All and Group.Read.All, User.ReadWrite.All and Group.Read.All, Directory.Read.All and Group.Read.All, User.ReadBasic.All and Group.ReadWrite.All, User.Read.All and Group.ReadWrite.All, User.ReadWrite.All and Group.ReadWrite.All, Directory.Read.All and Group.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | User.Read.All and Group.Read.All, User.ReadWrite.All and Group.Read.All, Directory.Read.All and Group.Read.All, User.Read.All and Group.ReadWrite.All, User.ReadWrite.All and Group.ReadWrite.All, Directory.Read.All and Group.ReadWrite.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /me/checkMemberObjects
POST /users/{id}/checkMemberObjects
```

## Request headers

| Name          | Description   |
|:--------------|:--------------|
| Authorization | Bearer {token} |
| Content-Type  | application/json |

## Request body

In the request body, provide a JSON object with the following parameters.

| Parameter    | Type        | Description |
|:-------------|:------------|:------------|
|ids|String collection|A collection that contains the object IDs of the groups, directory roles, or administrative units, in which to check membership. Up to 20 groups may be specified.|

## Response

If successful, this method returns a `200 OK` response code and a new String collection object in the response body.

## Examples

The following is an example of how to call this API.

### Request

The following is an example of the request.
<!-- {
  "blockType": "request",
  "name": "user_checkmemberobjects"
}-->

```http
POST https://graph.microsoft.com/beta/me/checkMemberObjects
Content-type: application/json

{
  "ids": [
    "ids-value"
  ]
}
```

### Response

The following is an example of the response.

> [!NOTE]
> The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "String",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json
{
  "value": [
    "String-value"
  ]
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "user: checkMemberObjects",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->