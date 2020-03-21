---
title: ICorProfilerInfo10 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175072"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="3719d-102">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3719d-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="3719d-103">함수 IL을 수정하고, 런타임에서 정보를 쿼리하고, 런타임을 일시 중단하고 다시 시작하려는 메서드를 제공하는 [ICorProfilerInfo9의](icorprofilerinfo9-interface.md) 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3719d-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="3719d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3719d-104">Methods</span></span>  

| <span data-ttu-id="3719d-105">방법</span><span class="sxs-lookup"><span data-stu-id="3719d-105">Method</span></span>|<span data-ttu-id="3719d-106">Description</span><span class="sxs-lookup"><span data-stu-id="3719d-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="3719d-107">EnumerateObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="3719d-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="3719d-108">ObjectID, 콜백 및 clientData가 주어지면 각 개체 참조(있는 경우)를 유거합니다.</span><span class="sxs-lookup"><span data-stu-id="3719d-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="3719d-109">IsFrozenObject 메서드</span><span class="sxs-lookup"><span data-stu-id="3719d-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="3719d-110">ObjectID가 주어지면 개체가 읽기 전용 세그먼트에 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3719d-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="3719d-111">GetLOHObjectSizeThreshold 메서드</span><span class="sxs-lookup"><span data-stu-id="3719d-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="3719d-112">구성된 LOH 임계값값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3719d-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="3719d-113">RequestReJITWithInliners 메서드</span><span class="sxs-lookup"><span data-stu-id="3719d-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="3719d-114">요청된 메서드와 요청된 메서드의 인라이너를 ReJIT합니다.</span><span class="sxs-lookup"><span data-stu-id="3719d-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="3719d-115">SuspendRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="3719d-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="3719d-116">GC를 수행하지 않고 런타임을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="3719d-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="3719d-117">ResumeRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="3719d-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="3719d-118">GC를 수행하지 않고 런타임을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3719d-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="3719d-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3719d-119">Requirements</span></span>  
<span data-ttu-id="3719d-120">**플랫폼:** [.NET Core 지원 운영 체제를](../../../core/install/dependencies.md?pivots=os-windows)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3719d-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="3719d-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3719d-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="3719d-122">**.NET 버전:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3719d-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3719d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3719d-123">See also</span></span>

- [<span data-ttu-id="3719d-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3719d-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
