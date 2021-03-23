---
title: CoreResponseData 클래스
description: HTTP 헤더 및 응답 본문의 구문 분석을 나타내는 CoreResponseData 클래스를 이해 합니다. .NET의 System.Net 네임 스페이스에 있습니다.
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
ms.openlocfilehash: 0c787481a57abc755e6f61b1cc96d74b86458b62
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873928"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="fd567-104">CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="fd567-104">CoreResponseData Class</span></span>

<span data-ttu-id="fd567-105">`CoreResponseData`클래스는 HTTP 헤더 및 응답 본문의 구문 분석을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd567-105">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd567-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd567-106">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="fd567-107">이 API는 내부용 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd567-107">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="fd567-108">대신를 사용 <xref:System.Diagnostics.DiagnosticSource> 하 여 네트워킹 코드를 후크 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd567-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="fd567-109">[DiagnosticSource 사용자 가이드](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd567-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="fd567-110">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd567-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd567-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd567-111">Requirements</span></span>

<span data-ttu-id="fd567-112">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="fd567-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="fd567-113">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="fd567-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="fd567-114">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd567-114">**.NET Framework versions:** Available since 2.0.</span></span>
