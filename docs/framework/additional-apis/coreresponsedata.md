---
title: CoreResponseData 클래스
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: fd0ffb982c22b0a8b6cb5dd677faafb9921bf5d9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741025"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="c01ae-102">CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="c01ae-102">CoreResponseData Class</span></span>

<span data-ttu-id="c01ae-103">`CoreResponseData` 클래스는 HTTP 헤더 및 응답 본문의 구문 분석을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c01ae-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="c01ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="c01ae-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="c01ae-105">이 API는 내부용 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c01ae-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="c01ae-106">대신 <xref:System.Diagnostics.DiagnosticSource>를 사용 하 여 네트워킹 코드를 후크 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01ae-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="c01ae-107">[DiagnosticSource 사용자 가이드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c01ae-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="c01ae-108">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c01ae-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c01ae-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c01ae-109">Requirements</span></span>

<span data-ttu-id="c01ae-110">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c01ae-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c01ae-111">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="c01ae-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c01ae-112">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c01ae-112">**.NET Framework versions:** Available since 2.0.</span></span>
