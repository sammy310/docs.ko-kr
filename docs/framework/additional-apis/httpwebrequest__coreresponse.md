---
title: HttpWebRequest._CoreResponse Field
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740456"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest.\_CoreResponse 필드

`HttpWebRequest._CoreResponse`는 HTTP 응답 구문 분석의 결과를 포함 하는 개체 ( [CoreResponseData](coreresponsedata.md) 또는 <xref:System.Exception>)입니다.

## <a name="syntax"></a>구문
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> 이 API는 코드에서 직접 사용할 수 없습니다. 대신 <xref:System.Diagnostics.DiagnosticSource>를 사용 하 여 네트워킹 코드를 후크 해야 합니다. [DiagnosticSource 사용자 가이드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)를 참조 하세요.
> 
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (system.string)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
