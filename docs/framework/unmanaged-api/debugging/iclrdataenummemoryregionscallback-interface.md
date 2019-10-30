---
title: ICLRDataEnumMemoryRegionsCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: cf46133095d1345ffbe0356d3ab486c11ae6dbd6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122909"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="5cfb4-102">ICLRDataEnumMemoryRegionsCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cfb4-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="5cfb4-103">지정 된 메모리 영역을 열거 하려는 시도의 결과로 디버거에 보고 하는 [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 에 대 한 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb4-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5cfb4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5cfb4-104">Methods</span></span>  
  
|<span data-ttu-id="5cfb4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5cfb4-105">Method</span></span>|<span data-ttu-id="5cfb4-106">설명</span><span class="sxs-lookup"><span data-stu-id="5cfb4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5cfb4-107">EnumMemoryRegion 메서드</span><span class="sxs-lookup"><span data-stu-id="5cfb4-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="5cfb4-108">지정 된 메모리 영역을 열거 하려는 시도의 결과로 디버거에 보고 하기 위해 `ICLRDataEnumMemoryRegions::EnumMemoryRegions`에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cfb4-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5cfb4-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5cfb4-109">Requirements</span></span>  
 <span data-ttu-id="5cfb4-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cfb4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cfb4-111">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="5cfb4-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5cfb4-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cfb4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cfb4-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cfb4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cfb4-114">참조</span><span class="sxs-lookup"><span data-stu-id="5cfb4-114">See also</span></span>

- [<span data-ttu-id="5cfb4-115">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cfb4-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
