---
title: httpWebRequest._CoreResponse 필드
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
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155923"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest. \_코어응답 필드

`HttpWebRequest._CoreResponse`은 HTTP 응답 구문 분석 <xref:System.Exception>결과를 포함하는 개체(CoreResponseData 또는 a)입니다. [CoreResponseData](coreresponsedata.md)

## <a name="syntax"></a>구문
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> 이 API는 코드에서 직접 사용할 수 없습니다. 대신 에 를 <xref:System.Diagnostics.DiagnosticSource> 사용하여 네트워킹 코드를 연결해야 합니다. [진단 소스 사용자 가이드를](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)참조하십시오.
>
> Microsoft는 어떠한 상황에서도 프로덕션 응용 프로그램에서 이 클래스의 사용을 지원하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:**<xref:System.Net>

**어셈블리:** 시스템(시스템.dll)

**.NET 프레임워크 버전:** 2.0 부터 사용할 수 있습니다.
