---
title: "Delete Name"
ms.date: "2017-10-02"
ms.prod: "azure"
ms.service: "service-fabric"
ms.topic: "reference"
applies_to: 
  - "Azure"
  - "Windows Server 2012 R2"
  - "Windows Server 2016"
dev_langs: 
  - "rest-api"
helpviewer_keywords: 
  - "Service Fabric REST API Reference"
author: "rwike77"
ms.author: "ryanwi"
manager: "timlt"
translation.priority.mt: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pt-br"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
---
# Delete Name
Deletes a Service Fabric name.

Deletes the specified Service Fabric name. A name must be created before it can be deleted. Deleting a name with child properties will fail.

## Request
| Method | Request URI |
| ------ | ----------- |
| DELETE | `/Names/{nameId}?api-version=6.0&timeout={timeout}` |


## Parameters
| Name | Type | Required | Location |
| --- | --- | --- | --- |
| [nameId](#nameid) | string | Yes | Path |
| [api-version](#api-version) | string | Yes | Query |
| [timeout](#timeout) | integer (int64) | No | Query |

____
### nameId
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The Service Fabric name, without the 'fabric:' URI scheme.

____
### api-version
__Type__: string <br/>
__Required__: Yes<br/>
__Default__: 6.0 <br/>
<br/>
The version of the API. This is a required parameter and it's value must be "6.0".

____
### timeout
__Type__: integer (int64) <br/>
__Required__: No<br/>
__Default__: 60 <br/>
__InclusiveMaximum__: 4294967295 <br/>
__InclusiveMinimum__: 1 <br/>
<br/>
The server timeout for performing the operation in seconds. This specifies the time duration that the client is willing to wait for the requested operation to complete. The default value for this parameter is 60 seconds.

## Responses

| HTTP Status Code | Description | Response Schema |
| --- | --- | --- |
| 200 (OK) | A successful response means that the Service Fabric name has been deleted.<br/> |  |
| All other status codes | The detailed error response.<br/> | [FabricError](sfclient-v60-model-fabricerror.md) |