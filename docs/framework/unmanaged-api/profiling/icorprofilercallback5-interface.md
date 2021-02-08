---
description: '자세히 알아보기: ICorProfilerCallback5 인터페이스'
title: ICorProfilerCallback5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: b80b27dc994ad556381228370ece92935d89d293
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788659"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="3d94c-103">ICorProfilerCallback5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d94c-103">ICorProfilerCallback5 Interface</span></span>

<span data-ttu-id="3d94c-104">[ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) 또는 [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 메서드와 함께 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) 및 [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) 메서드와 함께 사용 되는 경우 프로파일러가 라이브 개체의 전체 클로저를 식별 하는 데 도움이 되는 정보를 보완 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94c-104">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="3d94c-105">관리되는 메모리 프로파일러가 `ICorProfilerCallback5`를 구현하여 종속 핸들과 관련된 알림을 구독해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94c-105">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d94c-106">설명</span><span class="sxs-lookup"><span data-stu-id="3d94c-106">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d94c-107">메서드</span><span class="sxs-lookup"><span data-stu-id="3d94c-107">Methods</span></span>  
  
|<span data-ttu-id="3d94c-108">메서드</span><span class="sxs-lookup"><span data-stu-id="3d94c-108">Method</span></span>|<span data-ttu-id="3d94c-109">설명</span><span class="sxs-lookup"><span data-stu-id="3d94c-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d94c-110">ConditionalWeakTableElementReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="3d94c-110">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="3d94c-111">직접 멤버 필드 참조와 `ConditionalWeakTable` 종속성을 모두 사용하여 루트를 통해 참조되는 개체의 전이적 Closure를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3d94c-111">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d94c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d94c-112">Requirements</span></span>  

 <span data-ttu-id="3d94c-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d94c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d94c-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d94c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d94c-115">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d94c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d94c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d94c-116">See also</span></span>

- [<span data-ttu-id="3d94c-117">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d94c-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3d94c-118">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d94c-118">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
