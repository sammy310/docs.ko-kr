---
description: '자세히 알아보기: ICorDebugHeapEnum 인터페이스'
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
ms.openlocfilehash: c8a2f46bf412e2c4b2fe43d3eb50169191f40445
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660897"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="f36e5-103">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f36e5-103">ICorDebugHeapEnum Interface</span></span>

<span data-ttu-id="f36e5-104">관리되는 힙의 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f36e5-104">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="f36e5-105">이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f36e5-105">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f36e5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f36e5-106">Methods</span></span>  
  
|<span data-ttu-id="f36e5-107">메서드</span><span class="sxs-lookup"><span data-stu-id="f36e5-107">Method</span></span>|<span data-ttu-id="f36e5-108">설명</span><span class="sxs-lookup"><span data-stu-id="f36e5-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f36e5-109">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="f36e5-109">Next Method</span></span>](icordebugheapenum-next-method.md)|<span data-ttu-id="f36e5-110">관리 되는 힙의 개체에 대 한 정보를 포함 하는 지정 된 수의 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f36e5-110">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f36e5-111">설명</span><span class="sxs-lookup"><span data-stu-id="f36e5-111">Remarks</span></span>  

 <span data-ttu-id="f36e5-112">`ICorDebugHeapEnum`인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36e5-112">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="f36e5-113">`ICorDebugHeapEnum` [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) 메서드를 호출 하 여 인스턴스가 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="f36e5-113">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="f36e5-114">컬렉션의 각 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스는 힙의 라이브 개체 또는 개체가 루 팅 되지 않았지만 가비지 수집기에서 아직 수집 되지 않은 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f36e5-114">Each [COR_HEAPOBJECT](cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="f36e5-115">[ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) 메서드를 호출 하 여 컬렉션의 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체를 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36e5-115">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f36e5-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f36e5-116">Requirements</span></span>  

 <span data-ttu-id="f36e5-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f36e5-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f36e5-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f36e5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f36e5-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f36e5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f36e5-120">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f36e5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f36e5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f36e5-121">See also</span></span>

- [<span data-ttu-id="f36e5-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f36e5-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
