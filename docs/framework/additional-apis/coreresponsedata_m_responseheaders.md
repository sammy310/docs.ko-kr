---
title: M_ResponseHeaders CoreResponseData 필드
description: .NET의 m_ResponseHeaders CoreResponseData 필드를 이해 합니다. 이 필드는 서버 응답과 연결 된 헤더가 있는 WebHeaderCollection 형식입니다.
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 7c7b896193cb81e9fc9e3ec28110359003a36728
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989790"
---
# <a name="coreresponsedatam_responseheaders-field"></a>CoreResponseData \_ ResponseHeaders 필드

`CoreResponseData.m_ResponseHeaders`<xref:System.Net.WebHeaderCollection>서버 응답과 연결 된 헤더의입니다.

## <a name="syntax"></a>구문
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> 이 API는 코드에서 직접 사용할 수 없습니다. 대신를 사용 <xref:System.Diagnostics.DiagnosticSource> 하 여 네트워킹 코드를 후크 해야 합니다. [DiagnosticSource 사용자 가이드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)를 참조 하세요.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
