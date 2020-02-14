---
title: HttpWebRequest. _HttpResponse 필드
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._HttpResponse
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: eab9b789-beb4-4c28-b2d8-78debc7ba129
ms.openlocfilehash: 236298921ecd286ddba4e74dbce1b63e96055412
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215107"
---
# <a name="httpwebrequest_httpresponse-field"></a><span data-ttu-id="81a84-102">HttpWebRequest.\_Httpresponse.cache 필드</span><span class="sxs-lookup"><span data-stu-id="81a84-102">HttpWebRequest.\_HttpResponse Field</span></span>

<span data-ttu-id="81a84-103">`HttpWebRequest._HttpResponse`는 HTTP 요청의 HTTP 응답 정보를 포함 하는 <xref:System.Net.HttpWebResponse>입니다.</span><span class="sxs-lookup"><span data-stu-id="81a84-103">`HttpWebRequest._HttpResponse` is an <xref:System.Net.HttpWebResponse> containing HTTP response details from an HTTP request.</span></span> <span data-ttu-id="81a84-104">HTTP 응답을 받을 때까지 `null` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81a84-104">It can be `null` until an HTTP response is received.</span></span>

## <a name="syntax"></a><span data-ttu-id="81a84-105">구문</span><span class="sxs-lookup"><span data-stu-id="81a84-105">Syntax</span></span>
  
```csharp  
internal HttpWebResponse _HttpResponse
```

> [!WARNING]
> <span data-ttu-id="81a84-106">`HttpWebRequest._HttpResponse` 필드는 내부적 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81a84-106">The `HttpWebRequest._HttpResponse` field is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="81a84-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81a84-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="81a84-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81a84-108">Requirements</span></span>

<span data-ttu-id="81a84-109">**네임 스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="81a84-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="81a84-110">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="81a84-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="81a84-111">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81a84-111">**.NET Framework versions:** Available since 2.0.</span></span>
