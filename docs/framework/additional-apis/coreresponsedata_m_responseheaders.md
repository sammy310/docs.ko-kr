---
title: CoreResponseData.m_ResponseHeaders 필드
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705976"
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="97c44-102">CoreResponseData.m\_ResponseHeaders 필드</span><span class="sxs-lookup"><span data-stu-id="97c44-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="97c44-103">`CoreResponseData.m_ResponseHeaders` 가 <xref:System.Net.WebHeaderCollection> 서버 응답과 관련 된 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="97c44-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="97c44-104">구문</span><span class="sxs-lookup"><span data-stu-id="97c44-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="97c44-105">코드에서 직접 사용할이 API는 사용 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="97c44-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="97c44-106">대신 사용 해야는 <xref:System.Diagnostics.DiagnosticSource> 네트워킹 코드를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="97c44-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="97c44-107">참조 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="97c44-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="97c44-108">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97c44-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="97c44-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97c44-109">Requirements</span></span>

<span data-ttu-id="97c44-110">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="97c44-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="97c44-111">**어셈블리:** 시스템 (에: System.dll)</span><span class="sxs-lookup"><span data-stu-id="97c44-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="97c44-112">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97c44-112">**.NET Framework versions:** Available since 2.0.</span></span>
