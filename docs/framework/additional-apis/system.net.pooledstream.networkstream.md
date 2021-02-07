---
description: '자세한 정보: PooledStream. NetworkStream 속성'
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
ms.openlocfilehash: 8a4f1d6bd9297028e763ef73bf96f85cbbfdafd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699638"
---
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="71dff-103">PooledStream. NetworkStream 속성</span><span class="sxs-lookup"><span data-stu-id="71dff-103">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="71dff-104">소켓의 네트워크 스트림을 가져오거나 설정 합니다 `PooledStream` .</span><span class="sxs-lookup"><span data-stu-id="71dff-104">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="71dff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="71dff-105">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="71dff-106">속성 값</span><span class="sxs-lookup"><span data-stu-id="71dff-106">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="71dff-107">소켓의 네트워크 스트림입니다 `PooledStream` .</span><span class="sxs-lookup"><span data-stu-id="71dff-107">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="71dff-108">설명</span><span class="sxs-lookup"><span data-stu-id="71dff-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="71dff-109">`PooledStream.NetworkStream`속성은 내부 속성 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71dff-109">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="71dff-110">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 속성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71dff-110">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="71dff-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71dff-111">Requirements</span></span>

<span data-ttu-id="71dff-112">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="71dff-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="71dff-113">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="71dff-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="71dff-114">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71dff-114">**.NET Framework versions:** Available since 2.0.</span></span>
