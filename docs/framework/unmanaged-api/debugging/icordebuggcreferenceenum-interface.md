---
description: '자세히 알아보기: ICorDebugGCReferenceEnum 인터페이스'
title: ICorDebugGCReferenceEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: ad4a61cdc2b30fb4c8e2be500eae878327c6b449
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801295"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="954dc-103">ICorDebugGCReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="954dc-103">ICorDebugGCReferenceEnum Interface</span></span>

<span data-ttu-id="954dc-104">가비지 수집되는 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-104">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="954dc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="954dc-105">Methods</span></span>  
  
|<span data-ttu-id="954dc-106">메서드</span><span class="sxs-lookup"><span data-stu-id="954dc-106">Method</span></span>|<span data-ttu-id="954dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="954dc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="954dc-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="954dc-108">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="954dc-109">가비지 수집 되는 개체에 대 한 정보를 포함 하는 지정 된 수의 [COR_GC_REFERENCE](cor-gc-reference-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-109">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="954dc-110">설명</span><span class="sxs-lookup"><span data-stu-id="954dc-110">Remarks</span></span>  

 <span data-ttu-id="954dc-111">이 `ICorDebugGCReferenceEnum` 인터페이스는 "ICorDebugEnum" 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-111">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="954dc-112">`ICorDebugGCReferenceEnum` [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) 메서드를 호출 하 여 인스턴스가 [COR_GC_REFERENCE](cor-gc-reference-structure.md) 인스턴스로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-112">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="954dc-113">[ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) 메서드를 호출 하 여 [COR_GC_REFERENCE](cor-gc-reference-structure.md) 개체를 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-113">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="954dc-114">이 메서드로 채워진 컬렉션의 [COR_GC_REFERENCE](cor-gc-reference-structure.md) 개체는 다음과 같은 세 가지 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-114">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="954dc-115">모든 관리 되는 스택의 개체</span><span class="sxs-lookup"><span data-stu-id="954dc-115">Objects from all managed stacks.</span></span> <span data-ttu-id="954dc-116">여기에는 공용 언어 런타임에서 만든 개체 뿐만 아니라 관리 코드의 라이브 참조도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-116">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="954dc-117">핸들 테이블의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-117">Objects from the handle table.</span></span> <span data-ttu-id="954dc-118">여기에는 모듈의 강력한 참조 ( `HNDTYPE_STRONG` 및 `HNDTYPE_REFCOUNT` ) 및 정적 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-118">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="954dc-119">종료자 큐의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-119">Objects from the finalizer queue.</span></span> <span data-ttu-id="954dc-120">종료자는 종료 자가 실행 될 때까지 개체를 큐에 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="954dc-120">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="954dc-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="954dc-121">Requirements</span></span>  

 <span data-ttu-id="954dc-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="954dc-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="954dc-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="954dc-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="954dc-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="954dc-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="954dc-125">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="954dc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954dc-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="954dc-126">See also</span></span>

- [<span data-ttu-id="954dc-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="954dc-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
