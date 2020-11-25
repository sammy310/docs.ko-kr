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
ms.openlocfilehash: 312052fcd683acbccb9ca616992bd635490aa2a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724366"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="a1759-102">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1759-102">ICorDebugHeapEnum Interface</span></span>

<span data-ttu-id="a1759-103">관리되는 힙의 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1759-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="a1759-104">이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a1759-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1759-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a1759-105">Methods</span></span>  
  
|<span data-ttu-id="a1759-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a1759-106">Method</span></span>|<span data-ttu-id="a1759-107">설명</span><span class="sxs-lookup"><span data-stu-id="a1759-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1759-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="a1759-108">Next Method</span></span>](icordebugheapenum-next-method.md)|<span data-ttu-id="a1759-109">관리 되는 힙의 개체에 대 한 정보를 포함 하는 지정 된 수의 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1759-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1759-110">설명</span><span class="sxs-lookup"><span data-stu-id="a1759-110">Remarks</span></span>  

 <span data-ttu-id="a1759-111">`ICorDebugHeapEnum`인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1759-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="a1759-112">`ICorDebugHeapEnum` [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) 메서드를 호출 하 여 인스턴스가 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="a1759-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="a1759-113">컬렉션의 각 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스는 힙의 라이브 개체 또는 개체가 루 팅 되지 않았지만 가비지 수집기에서 아직 수집 되지 않은 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1759-113">Each [COR_HEAPOBJECT](cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="a1759-114">[ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) 메서드를 호출 하 여 컬렉션의 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체를 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1759-114">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1759-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1759-115">Requirements</span></span>  

 <span data-ttu-id="a1759-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1759-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1759-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1759-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1759-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1759-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1759-119">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1759-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1759-120">참조</span><span class="sxs-lookup"><span data-stu-id="a1759-120">See also</span></span>

- [<span data-ttu-id="a1759-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1759-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
