---
title: HttpWebRequest._HttpResponse 필드
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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ef746d4a2e6782fa295b7c27f32ce5dc117350a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675496"
---
# <a name="httpwebrequesthttpresponse-field"></a><span data-ttu-id="f19e8-102">HttpWebRequest 합니다. \_HttpResponse 필드</span><span class="sxs-lookup"><span data-stu-id="f19e8-102">HttpWebRequest.\_HttpResponse Field</span></span>

<span data-ttu-id="f19e8-103">`HttpWebRequest._HttpResponse` 가 <xref:System.Net.HttpWebResponse> HTTP 요청에서 HTTP 응답 세부 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19e8-103">`HttpWebRequest._HttpResponse` is an <xref:System.Net.HttpWebResponse> containing HTTP response details from an HTTP request.</span></span> <span data-ttu-id="f19e8-104">수 `null` HTTP 응답을 받을 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f19e8-104">It can be `null` until an HTTP response is received.</span></span>

## <a name="syntax"></a><span data-ttu-id="f19e8-105">구문</span><span class="sxs-lookup"><span data-stu-id="f19e8-105">Syntax</span></span>
  
```csharp  
internal HttpWebResponse _HttpResponse
```

> [!WARNING]
> <span data-ttu-id="f19e8-106">`HttpWebRequest._HttpResponse` 필드는 내부 전용 이며 코드에서 직접 사용할 업그레이드용은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f19e8-106">The `HttpWebRequest._HttpResponse` field is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="f19e8-107">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f19e8-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f19e8-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f19e8-108">Requirements</span></span>

<span data-ttu-id="f19e8-109">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f19e8-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f19e8-110">**어셈블리:** 시스템 (에: System.dll)</span><span class="sxs-lookup"><span data-stu-id="f19e8-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f19e8-111">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f19e8-111">**.NET Framework versions:** Available since 2.0.</span></span>
