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
ms.openlocfilehash: 39a14a3df5059cc47cd4879e4d4ba351cc7b655b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156118"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="5039b-102">CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="5039b-102">CoreResponseData Class</span></span>

<span data-ttu-id="5039b-103">클래스는 `CoreResponseData` HTTP 헤더와 응답 본문의 구문 분석입니다.</span><span class="sxs-lookup"><span data-stu-id="5039b-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="5039b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5039b-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="5039b-105">이 API는 내부이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5039b-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="5039b-106">대신 에 를 <xref:System.Diagnostics.DiagnosticSource> 사용하여 네트워킹 코드를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5039b-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="5039b-107">[진단 소스 사용자 가이드를](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5039b-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="5039b-108">Microsoft는 어떠한 상황에서도 프로덕션 응용 프로그램에서 이 클래스의 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5039b-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5039b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5039b-109">Requirements</span></span>

<span data-ttu-id="5039b-110">**네임스페이스:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="5039b-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="5039b-111">**어셈블리:** 시스템(시스템.dll)</span><span class="sxs-lookup"><span data-stu-id="5039b-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="5039b-112">**.NET 프레임워크 버전:** 2.0 부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5039b-112">**.NET Framework versions:** Available since 2.0.</span></span>
