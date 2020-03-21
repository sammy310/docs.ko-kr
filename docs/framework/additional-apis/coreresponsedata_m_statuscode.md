---
title: 코어응답데이터.m_StatusCode 필드
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
ms.openlocfilehash: dfed9a748e959f0f751408566c7cbb4d2fa13e3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156075"
---
# <a name="coreresponsedatam_statuscode-field"></a><span data-ttu-id="40ece-102">코어응답데이터.m\_상태 코드 필드</span><span class="sxs-lookup"><span data-stu-id="40ece-102">CoreResponseData.m\_StatusCode Field</span></span>

<span data-ttu-id="40ece-103">`CoreResponseData.m_StatusCode`은 <xref:System.Net.HttpStatusCode> 응답 상태를 포함하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="40ece-103">`CoreResponseData.m_StatusCode` is an <xref:System.Net.HttpStatusCode> containing the status of the response.</span></span>

## <a name="syntax"></a><span data-ttu-id="40ece-104">구문</span><span class="sxs-lookup"><span data-stu-id="40ece-104">Syntax</span></span>
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> <span data-ttu-id="40ece-105">이 API는 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40ece-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="40ece-106">대신 에 를 <xref:System.Diagnostics.DiagnosticSource> 사용하여 네트워킹 코드를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40ece-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="40ece-107">[진단 소스 사용자 가이드를](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="40ece-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="40ece-108">Microsoft는 어떠한 상황에서도 프로덕션 응용 프로그램에서 이 클래스의 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40ece-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="40ece-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40ece-109">Requirements</span></span>

<span data-ttu-id="40ece-110">**네임스페이스:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="40ece-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="40ece-111">**어셈블리:** 시스템(시스템.dll)</span><span class="sxs-lookup"><span data-stu-id="40ece-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="40ece-112">**.NET 프레임워크 버전:** 2.0 부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40ece-112">**.NET Framework versions:** Available since 2.0.</span></span>
