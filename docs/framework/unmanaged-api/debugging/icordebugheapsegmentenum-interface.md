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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73036d1c12c46cbfda8031073a005bc9b376040e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756214"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="51401-102">ICorDebugHeapSegmentEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51401-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="51401-103">관리되는 힙 메모리 영역에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51401-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="51401-104">이 인터페이스는 ICorDebugEnum 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="51401-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51401-105">메서드</span><span class="sxs-lookup"><span data-stu-id="51401-105">Methods</span></span>  
  
|<span data-ttu-id="51401-106">메서드</span><span class="sxs-lookup"><span data-stu-id="51401-106">Method</span></span>|<span data-ttu-id="51401-107">설명</span><span class="sxs-lookup"><span data-stu-id="51401-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51401-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="51401-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="51401-109">지정 된 개수를 가져옵니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 힙의 관리 되는 지역에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="51401-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51401-110">설명</span><span class="sxs-lookup"><span data-stu-id="51401-110">Remarks</span></span>  
 <span data-ttu-id="51401-111">`ICorDebugHeapSegmentEnum` ICorDebugEnum 인터페이스를 구현 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="51401-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="51401-112">`ICorDebugHeapSegmentEnum` 인스턴스 채워집니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 호출 하 여 인스턴스를 [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="51401-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="51401-113">합니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 를 호출 하 여 컬렉션의 개체를 열거할 수 있습니다 합니다 [icordebugheapsegmentenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="51401-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="51401-114">`ICorDebugHeapSegmentEnum` 컬렉션 개체는 관리 되는 개체를 포함할 수 있는 모든 메모리 영역을 열거 하지만 해당 지역에서 관리 되는 개체 실제로 있는 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51401-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="51401-115">비어 있거나 예약 된 메모리 영역에 대 한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51401-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51401-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51401-116">Requirements</span></span>  
 <span data-ttu-id="51401-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="51401-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51401-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51401-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51401-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51401-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51401-120">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51401-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51401-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="51401-121">See also</span></span>

- [<span data-ttu-id="51401-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51401-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
