---
title: ICorDebugHeapSegmentEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138457"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="5d2ec-102">ICorDebugHeapSegmentEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d2ec-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="5d2ec-103">관리되는 힙 메모리 영역에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="5d2ec-104">이 인터페이스는 ICorDebugEnum 인터페이스의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d2ec-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5d2ec-105">Methods</span></span>  
  
|<span data-ttu-id="5d2ec-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5d2ec-106">Method</span></span>|<span data-ttu-id="5d2ec-107">설명</span><span class="sxs-lookup"><span data-stu-id="5d2ec-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d2ec-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="5d2ec-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="5d2ec-109">관리 되는 힙의 영역에 대 한 정보를 포함 하는 지정 된 수의 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d2ec-110">주의</span><span class="sxs-lookup"><span data-stu-id="5d2ec-110">Remarks</span></span>  
 <span data-ttu-id="5d2ec-111">`ICorDebugHeapSegmentEnum` 인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="5d2ec-112">`ICorDebugHeapSegmentEnum` 인스턴스는 [ICorDebugProcess5:: EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) 메서드를 호출 하 여 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 인스턴스로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="5d2ec-113">컬렉션의 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체는 [ICorDebugHeapSegmentEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) 메서드를 호출 하 여 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="5d2ec-114">`ICorDebugHeapSegmentEnum` collection 개체는 관리 되는 개체를 포함할 수 있는 모든 메모리 영역을 열거 하지만 관리 되는 개체가 해당 지역에 실제로 상주 하는 것을 보장 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="5d2ec-115">여기에는 비어 있거나 예약 된 메모리 영역에 대 한 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d2ec-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d2ec-116">Requirements</span></span>  
 <span data-ttu-id="5d2ec-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d2ec-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d2ec-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d2ec-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d2ec-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d2ec-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d2ec-120">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d2ec-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2ec-121">참조</span><span class="sxs-lookup"><span data-stu-id="5d2ec-121">See also</span></span>

- [<span data-ttu-id="5d2ec-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d2ec-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
