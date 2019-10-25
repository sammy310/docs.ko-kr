---
title: TlsStream 필드 (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.TlsStream.m_Worker
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: d335820d13e1e15e054e824a284615cdbf6c2094
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847243"
---
# <a name="tlsstreamm_worker-field"></a><span data-ttu-id="c3e29-102">TlsStream. m_Worker 필드</span><span class="sxs-lookup"><span data-stu-id="c3e29-102">TlsStream.m_Worker Field</span></span>

<span data-ttu-id="c3e29-103">SSL 스트림의 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3e29-103">Represents the state of the SSL stream.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3e29-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3e29-104">Syntax</span></span>

```csharp
private SslState m_Worker;
```

## <a name="field-value"></a><span data-ttu-id="c3e29-105">필드 값</span><span class="sxs-lookup"><span data-stu-id="c3e29-105">Field value</span></span>

`System.Net.Security.SslState`  
<span data-ttu-id="c3e29-106">SSL 스트림의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e29-106">The state of the SSL stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3e29-107">주의</span><span class="sxs-lookup"><span data-stu-id="c3e29-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c3e29-108">`TlsStream.m_Worker` 필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e29-108">The `TlsStream.m_Worker` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c3e29-109">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e29-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3e29-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3e29-110">Requirements</span></span>

<span data-ttu-id="c3e29-111">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="c3e29-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="c3e29-112">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="c3e29-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="c3e29-113">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e29-113">**.NET Framework versions:** Available since 2.0.</span></span>
