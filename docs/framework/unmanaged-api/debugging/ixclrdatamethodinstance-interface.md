---
description: '자세히 알아보기: IXCLRDataMethodInstance 인터페이스'
title: IXCLRDataMethodInstance 인터페이스
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4e9ad57988420ff14b297c693c31c0dc5b3b181c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800788"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="89efc-103">IXCLRDataMethodInstance 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89efc-103">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="89efc-104">메서드 인스턴스에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89efc-104">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="89efc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="89efc-105">Methods</span></span>

| <span data-ttu-id="89efc-106">메서드</span><span class="sxs-lookup"><span data-stu-id="89efc-106">Method</span></span>                                                                                                                  | <span data-ttu-id="89efc-107">설명</span><span class="sxs-lookup"><span data-stu-id="89efc-107">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="89efc-108">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="89efc-108">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="89efc-109">매핑 정보를 처리 하는 IL을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89efc-109">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="89efc-110">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="89efc-110">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="89efc-111">메서드에 대 한 모든 가능한 진입점의 네이티브 컴파일에 대 한 가장 대표적인 진입점 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89efc-111">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="89efc-112">설명</span><span class="sxs-lookup"><span data-stu-id="89efc-112">Remarks</span></span>

<span data-ttu-id="89efc-113">이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89efc-113">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="89efc-114">그러나 `IUnknown` `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="89efc-114">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="89efc-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89efc-115">Requirements</span></span>

<span data-ttu-id="89efc-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89efc-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="89efc-117">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="89efc-117">**Header:** None</span></span>  
<span data-ttu-id="89efc-118">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="89efc-118">**Library:** None</span></span>  
<span data-ttu-id="89efc-119">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="89efc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="89efc-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89efc-120">See also</span></span>

- [<span data-ttu-id="89efc-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="89efc-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="89efc-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89efc-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
