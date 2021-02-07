---
description: '다음에 대 한 자세한 정보: TlsStream.m_Worker 필드'
title: TlsStream.m_Worker 필드 (System.Net)
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
ms.openlocfilehash: d929b0b1949bc1902425c016bfd770d4c66a3257
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699521"
---
# <a name="tlsstreamm_worker-field"></a><span data-ttu-id="59443-103">TlsStream.m_Worker 필드</span><span class="sxs-lookup"><span data-stu-id="59443-103">TlsStream.m_Worker Field</span></span>

<span data-ttu-id="59443-104">SSL 스트림의 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="59443-104">Represents the state of the SSL stream.</span></span>

## <a name="syntax"></a><span data-ttu-id="59443-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="59443-105">Syntax</span></span>

```csharp
private SslState m_Worker;
```

## <a name="field-value"></a><span data-ttu-id="59443-106">필드 값</span><span class="sxs-lookup"><span data-stu-id="59443-106">Field value</span></span>

`System.Net.Security.SslState`  
<span data-ttu-id="59443-107">SSL 스트림의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="59443-107">The state of the SSL stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="59443-108">설명</span><span class="sxs-lookup"><span data-stu-id="59443-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="59443-109">`TlsStream.m_Worker`필드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59443-109">The `TlsStream.m_Worker` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="59443-110">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59443-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="59443-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59443-111">Requirements</span></span>

<span data-ttu-id="59443-112">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="59443-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="59443-113">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="59443-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="59443-114">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59443-114">**.NET Framework versions:** Available since 2.0.</span></span>
