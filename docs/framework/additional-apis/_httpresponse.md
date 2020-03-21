---
title: httpWebRequest._HttpResponse 필드
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
ms.openlocfilehash: 0c5bfc56299aa06dd59c2598588044e81a69933a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156248"
---
# <a name="httpwebrequest_httpresponse-field"></a><span data-ttu-id="00cee-102">HttpWebRequest. \_HttpResponse 필드</span><span class="sxs-lookup"><span data-stu-id="00cee-102">HttpWebRequest.\_HttpResponse Field</span></span>

<span data-ttu-id="00cee-103">`HttpWebRequest._HttpResponse`는 <xref:System.Net.HttpWebResponse> HTTP 요청의 HTTP 응답 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00cee-103">`HttpWebRequest._HttpResponse` is an <xref:System.Net.HttpWebResponse> containing HTTP response details from an HTTP request.</span></span> <span data-ttu-id="00cee-104">HTTP 응답이 수신될 때까지 가능합니다. `null`</span><span class="sxs-lookup"><span data-stu-id="00cee-104">It can be `null` until an HTTP response is received.</span></span>

## <a name="syntax"></a><span data-ttu-id="00cee-105">구문</span><span class="sxs-lookup"><span data-stu-id="00cee-105">Syntax</span></span>
  
```csharp  
internal HttpWebResponse _HttpResponse
```

> [!WARNING]
> <span data-ttu-id="00cee-106">필드는 `HttpWebRequest._HttpResponse` 내부이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00cee-106">The `HttpWebRequest._HttpResponse` field is internal and not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="00cee-107">Microsoft는 어떠한 상황에서도 프로덕션 응용 프로그램에서 이 필드의 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00cee-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="00cee-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00cee-108">Requirements</span></span>

<span data-ttu-id="00cee-109">**네임스페이스:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="00cee-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="00cee-110">**어셈블리:** 시스템(시스템.dll)</span><span class="sxs-lookup"><span data-stu-id="00cee-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="00cee-111">**.NET 프레임워크 버전:** 2.0 부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00cee-111">**.NET Framework versions:** Available since 2.0.</span></span>
