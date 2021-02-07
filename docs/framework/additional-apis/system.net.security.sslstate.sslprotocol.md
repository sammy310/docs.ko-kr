---
description: '자세한 정보: SslState. Sslstate 속성'
title: SslState. Sslstate 속성 (시스템 .Net. 보안)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: b0b9bebf23fcd8d643d06f1cff10c260c77a7c08
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699625"
---
# <a name="sslstatesslprotocol-property"></a><span data-ttu-id="8f54a-103">SslState. Sslstate 속성</span><span class="sxs-lookup"><span data-stu-id="8f54a-103">SslState.SslProtocol Property</span></span>

<span data-ttu-id="8f54a-104">SSL 프로토콜 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f54a-104">Gets the SSL protocol versions.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f54a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f54a-105">Syntax</span></span>

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a><span data-ttu-id="8f54a-106">속성 값</span><span class="sxs-lookup"><span data-stu-id="8f54a-106">Property value</span></span>

<xref:System.Security.Authentication.SslProtocols>  
<span data-ttu-id="8f54a-107">SSL 프로토콜 버전을 지정 하는 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="8f54a-107">A bitwise combination of the enumeration values that specify the SSL protocol versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f54a-108">설명</span><span class="sxs-lookup"><span data-stu-id="8f54a-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="8f54a-109">`SslState.SslProtocol`속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f54a-109">The `SslState.SslProtocol` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="8f54a-110">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f54a-110">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f54a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f54a-111">Requirements</span></span>

<span data-ttu-id="8f54a-112">**네임스페이스:** <xref:System.Net.Security></span><span class="sxs-lookup"><span data-stu-id="8f54a-112">**Namespace:** <xref:System.Net.Security></span></span>

<span data-ttu-id="8f54a-113">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="8f54a-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="8f54a-114">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f54a-114">**.NET Framework versions:** Available since 2.0.</span></span>
