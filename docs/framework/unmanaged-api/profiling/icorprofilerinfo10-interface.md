---
title: ICorProfilerInfo10 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 7e483bae9b7898e25c376fa92d0449fc49c6f9ee
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548688"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="64db9-102">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64db9-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="64db9-103">함수 IL을 수정 하 고, 런타임에서 정보를 쿼리하고, 런타임을 일시 중단 하 고 다시 시작 하는 메서드를 제공 하는 [ICorProfilerInfo9](icorprofilerinfo9-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="64db9-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="64db9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="64db9-104">Methods</span></span>  

| <span data-ttu-id="64db9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="64db9-105">Method</span></span>|<span data-ttu-id="64db9-106">Description</span><span class="sxs-lookup"><span data-stu-id="64db9-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="64db9-107">EnumerateObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="64db9-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="64db9-108">ObjectID, callback 및 clientData가 지정 된 경우 각 개체 참조를 열거 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="64db9-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="64db9-109">IsFrozenObject 메서드</span><span class="sxs-lookup"><span data-stu-id="64db9-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="64db9-110">ObjectID가 지정 된 경우 개체가 읽기 전용 세그먼트에 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="64db9-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="64db9-111">GetLOHObjectSizeThreshold 메서드</span><span class="sxs-lookup"><span data-stu-id="64db9-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="64db9-112">구성 된 LOH 임계값의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64db9-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="64db9-113">RequestReJITWithInliners 메서드</span><span class="sxs-lookup"><span data-stu-id="64db9-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="64db9-114">요청 된 메서드 뿐 아니라 요청 된 메서드의 모든 inliners ReJITs 합니다.</span><span class="sxs-lookup"><span data-stu-id="64db9-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="64db9-115">SuspendRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="64db9-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="64db9-116">GC를 수행 하지 않고 런타임을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="64db9-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="64db9-117">ResumeRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="64db9-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="64db9-118">GC를 수행 하지 않고 런타임을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="64db9-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="64db9-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64db9-119">Requirements</span></span>  
<span data-ttu-id="64db9-120">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64db9-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="64db9-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64db9-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="64db9-122">**.Net 버전:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64db9-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="64db9-123">참조</span><span class="sxs-lookup"><span data-stu-id="64db9-123">See also</span></span>

- [<span data-ttu-id="64db9-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64db9-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
