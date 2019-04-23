---
title: ICorDebugHeapEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79ef77e52e14fede9949121e7ec4575d10b820c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135852"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="fe283-102">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe283-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="fe283-103">관리되는 힙의 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe283-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="fe283-104">이 인터페이스는 ICorDebugEnum 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe283-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe283-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fe283-105">Methods</span></span>  
  
|<span data-ttu-id="fe283-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fe283-106">Method</span></span>|<span data-ttu-id="fe283-107">설명</span><span class="sxs-lookup"><span data-stu-id="fe283-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe283-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="fe283-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="fe283-109">지정 된 개수를 가져옵니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="fe283-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe283-110">설명</span><span class="sxs-lookup"><span data-stu-id="fe283-110">Remarks</span></span>  
 <span data-ttu-id="fe283-111">`ICorDebugHeapEnum` ICorDebugEnum 인터페이스를 구현 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe283-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="fe283-112">`ICorDebugHeapEnum` 인스턴스 채워집니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 호출 하 여 인스턴스를 [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="fe283-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="fe283-113">각 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 힙에 대 한 활성 개체 또는 모든 개체에서 루 팅 되지 않지만 가비지 수집기에 의해 아직 수집 되지 않았습니다 하는 개체 컬렉션의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe283-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="fe283-114">합니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 를 호출 하 여 컬렉션의 개체를 열거할 수 있습니다 합니다 [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="fe283-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe283-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe283-115">Requirements</span></span>  
 <span data-ttu-id="fe283-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe283-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe283-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe283-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe283-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe283-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe283-119">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe283-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe283-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="fe283-120">See also</span></span>

- [<span data-ttu-id="fe283-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe283-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
