---
title: M_StatusCode CoreResponseData 필드
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_StatusCode
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 8abe619a57cc61fc3502807f60deccbbd578f382
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740996"
---
# <a name="coreresponsedatam_statuscode-field"></a>CoreResponseData\_StatusCode 필드

`CoreResponseData.m_StatusCode`은 응답의 상태를 포함 하는 <xref:System.Net.HttpStatusCode>입니다.

## <a name="syntax"></a>구문
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> 이 API는 코드에서 직접 사용할 수 없습니다. 대신 <xref:System.Diagnostics.DiagnosticSource>를 사용 하 여 네트워킹 코드를 후크 해야 합니다. [DiagnosticSource 사용자 가이드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)를 참조 하세요.
> 
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (system.string)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
