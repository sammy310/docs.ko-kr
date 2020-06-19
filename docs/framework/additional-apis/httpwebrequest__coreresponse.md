---
title: HttpWebRequest. _CoreResponse 필드
description: .NET의 HttpWebRequest. _CoreResponse 필드에 대해 읽어 보십시오. 이 필드는 HTTP 응답 구문 분석의 결과를 포함 하는 CoreResponseData 또는 Exception 개체입니다.
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
ms.openlocfilehash: 5093ec7ed2c3b94931dcd622ae9ccdb42feffa18
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989755"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="22d07-104">HttpWebRequest. \_ CoreResponse 필드</span><span class="sxs-lookup"><span data-stu-id="22d07-104">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="22d07-105">`HttpWebRequest._CoreResponse`는 [CoreResponseData](coreresponsedata.md) <xref:System.Exception> HTTP 응답 구문 분석의 결과를 포함 하는 개체 (CoreResponseData 또는)입니다.</span><span class="sxs-lookup"><span data-stu-id="22d07-105">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="22d07-106">구문</span><span class="sxs-lookup"><span data-stu-id="22d07-106">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="22d07-107">이 API는 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22d07-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="22d07-108">대신를 사용 <xref:System.Diagnostics.DiagnosticSource> 하 여 네트워킹 코드를 후크 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d07-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="22d07-109">[DiagnosticSource 사용자 가이드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22d07-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="22d07-110">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22d07-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="22d07-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22d07-111">Requirements</span></span>

<span data-ttu-id="22d07-112">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="22d07-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="22d07-113">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="22d07-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="22d07-114">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d07-114">**.NET Framework versions:** Available since 2.0.</span></span>
