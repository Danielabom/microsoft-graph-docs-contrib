---
title: "organization resource type"
description: " create and delete are not supported. Inherits from directoryObject."
ms.localizationpriority: high
author: "suawat"
ms.reviewer: "alvarorahul, iamut"
ms.subservice: "entra-directory-management"
doc_type: resourcePageType
---

# organization resource type

Namespace: microsoft.graph

Represents the Microsoft Entra tenant that the user or application is signed in to. Only the read and update operations are supported on this resource; create and delete are not supported. Inherits from [directoryObject](directoryobject.md).

This resource lets you add your own data to custom properties using [extensions](/graph/extensibility-overview).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[List organizations](../api/organization-list.md) | [organization](organization.md) collection|Read properties and relationships of the organization object.|
|[Get organization](../api/organization-get.md) | [organization](organization.md) collection|Read properties and relationships of organization object.|
|[Update](../api/organization-update.md) |  None | Update an organization object.  |

## Properties

| Property | Type | Description |
|:-------- |:---- |:----------- |
| assignedPlans | [assignedPlan](assignedplan.md) collection | The collection of service plans associated with the tenant. Not nullable. |
| businessPhones | String collection | Telephone number for the organization. Although this is a string collection, only one number can be set for this property. |
| city | String | City name of the address for the organization. |
| country | String | Country/region name of the address for the organization. |
| countryLetterCode | String | Country or region abbreviation for the organization in ISO 3166-2 format. |
| createdDateTime | DateTimeOffset | Timestamp of when the organization was created. The value cannot be modified and is automatically populated when the organization is created. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only. |
| defaultUsageLocation | String | Two-letter ISO 3166 country code indicating the default service usage location of an organization. |
| deletedDateTime | DateTimeOffset | Represents date and time of when the Microsoft Entra tenant was deleted using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only. |
| displayName | String | The display name for the tenant. |
| id | String | The tenant ID, a unique identifier representing the organization (or tenant). Inherited from [directoryObject](directoryobject.md). Key. Not nullable. Read-only. |
| isMultipleDataLocationsForServicesEnabled | Boolean | `true` if organization is Multi-Geo enabled; **false** if organization is not Multi-Geo enabled; **null** (default). Read-only. For more information, see [OneDrive Online Multi-Geo](/sharepoint/dev/solution-guidance/multigeo-introduction). |
| marketingNotificationEmails | String collection | Not nullable. |
| onPremisesLastSyncDateTime | DateTimeOffset | The time and date at which the tenant was last synced with the on-premises directory. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only.|
| onPremisesSyncEnabled | Boolean | `true` if this object is synced from an on-premises directory; `false` if this object was originally synced from an on-premises directory but is no longer synced. Nullable. `null` if this object has never been synced from an on-premises directory (default). |
| partnerTenantType | partnerTenantType | The type of partnership this tenant has with Microsoft. The possible values are: `microsoftSupport`, `syndicatePartner`, `breadthPartner`, `breadthPartnerDelegatedAdmin`, `resellerPartnerDelegatedAdmin`, `valueAddedResellerPartnerDelegatedAdmin`, `unknownFutureValue`. Nullable. For more information about the possible types, see [partnerTenantType values](#partnertenanttype-values).|
| postalCode | String | Postal code of the address for the organization. |
| preferredLanguage | String | The preferred language for the organization. Should follow ISO 639-1 Code; for example, `en`. |
| privacyProfile | [privacyProfile](privacyprofile.md) | The privacy profile of an organization. |
| provisionedPlans | [ProvisionedPlan](provisionedplan.md) collection | Not nullable. |
| securityComplianceNotificationMails | String collection | Not nullable.|
| securityComplianceNotificationPhones | String collection| Not nullable.|
| state | String | State name of the address for the organization. |
| street | String | Street name of the address for organization. |
| technicalNotificationMails | String collection | Not nullable. |
| tenantType | String | Not nullable. The tenant type option that was selected when the tenant was created. The possible values are: <li> `AAD` - An enterprise identity access management (IAM) service that serves business-to-employee and business-to-business (B2B) scenarios. <li> `AAD B2C` A customer identity access management (CIAM) service that serves business-to-consumer (B2C) scenarios.  |
| verifiedDomains | [VerifiedDomain](verifieddomain.md) collection | The collection of domains associated with this tenant. Not nullable. |

### partnerTenantType values

| Member | Description |
|-----------------------------------------|----------------------------------------------------------------------------|
| microsoftSupport | Legacy support tenant of Microsoft that was used to provide administrative support to all customer tenants. |
| breadthPartner | The partner can provide administrative support for their customers. However, the partner is not allowed to resell to or request delegated admin permissions from customers. |
| breadthPartnerDelegatedAdmin | Similar to Breadth Partner except they can request for delegated admin permissions (DAP) from customer tenants. |
| syndicatePartner | The partner exclusively resells and manages Microsoft 365 and Intune for their customers. The customer cannot buy additional subscriptions directly or through other Microsoft partners. |
| resellerPartnerDelegatedAdmin | The partner that can resell and manage Microsoft 365 and Intune for their customers. There is no exclusivity clause like for syndication partners. The customer can buy additional direct subscriptions directly from Microsoft or through other Microsoft partners. |
| valueAddedResellerPartnerDelegatedAdmin | Are Tier 2 partners. They are Microsoft partners that have a relationship with another Microsoft partner such as a reseller. |
| unknownFutureValue | Evolvable enumeration sentinel value. Do not use. |

## Relationships
| Relationship | Type    |Description|
|:---------------|:--------|:----------|
|certificateBasedAuthConfiguration|[certificateBasedAuthConfiguration](certificatebasedauthconfiguration.md) collection| Navigation property to manage certificate-based authentication configuration. Only a single instance of certificateBasedAuthConfiguration can be created in the collection.  |
|extensions|[extension](extension.md) collection|The collection of open extensions defined for the organization. Read-only. Nullable.|
|branding|[organizationalBranding](organizationalbranding.md)| Branding for the organization. Nullable.|

## JSON representation

Here is a JSON representation of the resource.

<!--{
  "blockType": "resource",
  "openType": true,
  "optionalProperties": [
    "extensions"
  ],
  "keyProperty": "id",
  "baseType": "microsoft.graph.directoryObject",
  "@odata.type": "microsoft.graph.organization"
}-->

```json
{
  "assignedPlans": [{"@odata.type": "microsoft.graph.assignedPlan"}],
  "businessPhones": ["string"],
  "city": "string",
  "country": "string",
  "countryLetterCode": "string",
  "createdDateTime": "String (timestamp)",
  "defaultUsageLocation": "String",
  "deletedDateTime": "String (timestamp)",
  "displayName": "string",
  "id": "string (identifier)",
  "isMultipleDataLocationsForServicesEnabled": "boolean",
  "marketingNotificationEmails": ["string"],
  "onPremisesLastSyncDateTime": "String (timestamp)",
  "onPremisesSyncEnabled": true,
  "partnerTenantType": "String",
  "postalCode": "string",
  "preferredLanguage": "string",
  "privacyProfile": {"@odata.type": "microsoft.graph.privacyProfile"},
  "provisionedPlans": [{"@odata.type": "microsoft.graph.provisionedPlan"}],
  "securityComplianceNotificationMails": ["string"],
  "securityComplianceNotificationPhones": ["string"],
  "state": "string",
  "street": "string",
  "technicalNotificationMails": ["string"],
  "tenantType": "string",
  "verifiedDomains": [{"@odata.type": "microsoft.graph.verifiedDomain"}]
}
```

## Related content

- [Add custom data to resources using extensions](/graph/extensibility-overview)
- [Add custom data to users using open extensions](/graph/extensibility-open-users)
- [Add custom data to groups using schema extensions](/graph/extensibility-schema-groups)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "organization resource",
  "keywords": "",
  "section": "documentation",
  "suppressions": [
  ],
  "tocPath": ""
}-->
