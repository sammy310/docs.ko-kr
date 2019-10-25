---
title: PooledStream. NetworkStream 속성 (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847231"
---
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="88ac1-102">PooledStream. NetworkStream 속성</span><span class="sxs-lookup"><span data-stu-id="88ac1-102">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="88ac1-103">`PooledStream` 소켓의 네트워크 스트림을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ac1-103">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="88ac1-104">구문</span><span class="sxs-lookup"><span data-stu-id="88ac1-104">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="88ac1-105">속성 값</span><span class="sxs-lookup"><span data-stu-id="88ac1-105">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="88ac1-106">`PooledStream` 소켓의 네트워크 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="88ac1-106">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="88ac1-107">주의</span><span class="sxs-lookup"><span data-stu-id="88ac1-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="88ac1-108">`PooledStream.NetworkStream` 속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88ac1-108">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="88ac1-109">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88ac1-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="88ac1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88ac1-110">Requirements</span></span>

<span data-ttu-id="88ac1-111">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="88ac1-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="88ac1-112">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="88ac1-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="88ac1-113">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ac1-113">**.NET Framework versions:** Available since 2.0.</span></span>
