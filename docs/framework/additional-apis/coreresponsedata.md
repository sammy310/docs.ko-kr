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
ms.openlocfilehash: 640a925c3aec86b4743b1b2b62eb3793af1cc0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675418"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="27b9a-102">CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="27b9a-102">CoreResponseData Class</span></span>

<span data-ttu-id="27b9a-103">`CoreResponseData` HTTP 헤더 및 응답 본문의 구문 분석 하는 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="27b9a-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="27b9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="27b9a-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="27b9a-105">이 API는 내부 및 코드에서 직접 사용할 수 없습니다 것입니다.</span><span class="sxs-lookup"><span data-stu-id="27b9a-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="27b9a-106">대신 사용 해야는 <xref:System.Diagnostics.DiagnosticSource> 네트워킹 코드를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="27b9a-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="27b9a-107">참조 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27b9a-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="27b9a-108">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27b9a-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="27b9a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27b9a-109">Requirements</span></span>

<span data-ttu-id="27b9a-110">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="27b9a-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="27b9a-111">**어셈블리:** 시스템 (에: System.dll)</span><span class="sxs-lookup"><span data-stu-id="27b9a-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="27b9a-112">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27b9a-112">**.NET Framework versions:** Available since 2.0.</span></span>
