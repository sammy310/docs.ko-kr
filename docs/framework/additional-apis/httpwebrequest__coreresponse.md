---
title: HttpWebRequest._CoreResponse Field
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
ms.openlocfilehash: 3627c9bf0d72ccec3a0d6d9c7c89b62f83dcd4b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706067"
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="b3dd9-102">HttpWebRequest 합니다. \_CoreResponse 필드</span><span class="sxs-lookup"><span data-stu-id="b3dd9-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="b3dd9-103">`HttpWebRequest._CoreResponse` 개체 (중 하나를 [CoreResponseData](coreresponsedata.md) 요소나 <xref:System.Exception>) HTTP 응답을 구문 분석 결과 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3dd9-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3dd9-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3dd9-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="b3dd9-105">코드에서 직접 사용할이 API는 사용 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b3dd9-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="b3dd9-106">대신 사용 해야는 <xref:System.Diagnostics.DiagnosticSource> 네트워킹 코드를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3dd9-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="b3dd9-107">참조 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3dd9-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="b3dd9-108">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3dd9-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3dd9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3dd9-109">Requirements</span></span>

<span data-ttu-id="b3dd9-110">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b3dd9-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b3dd9-111">**어셈블리:** 시스템 (에: System.dll)</span><span class="sxs-lookup"><span data-stu-id="b3dd9-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="b3dd9-112">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3dd9-112">**.NET Framework versions:** Available since 2.0.</span></span>
