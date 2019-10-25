---
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
ms.openlocfilehash: 6983ac071dad29b240308031ecd0a3562a6856e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847249"
---
# <a name="sslstatesslprotocol-property"></a><span data-ttu-id="94830-102">SslState. Sslstate 속성</span><span class="sxs-lookup"><span data-stu-id="94830-102">SslState.SslProtocol Property</span></span>

<span data-ttu-id="94830-103">SSL 프로토콜 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="94830-103">Gets the SSL protocol versions.</span></span>

## <a name="syntax"></a><span data-ttu-id="94830-104">구문</span><span class="sxs-lookup"><span data-stu-id="94830-104">Syntax</span></span>

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a><span data-ttu-id="94830-105">속성 값</span><span class="sxs-lookup"><span data-stu-id="94830-105">Property value</span></span>

<xref:System.Security.Authentication.SslProtocols>  
<span data-ttu-id="94830-106">SSL 프로토콜 버전을 지정 하는 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="94830-106">A bitwise combination of the enumeration values that specify the SSL protocol versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="94830-107">주의</span><span class="sxs-lookup"><span data-stu-id="94830-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="94830-108">`SslState.SslProtocol` 속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94830-108">The `SslState.SslProtocol` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="94830-109">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94830-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="94830-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94830-110">Requirements</span></span>

<span data-ttu-id="94830-111">**네임스페이스:** <xref:System.Net.Security></span><span class="sxs-lookup"><span data-stu-id="94830-111">**Namespace:** <xref:System.Net.Security></span></span>

<span data-ttu-id="94830-112">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="94830-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="94830-113">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94830-113">**.NET Framework versions:** Available since 2.0.</span></span>
