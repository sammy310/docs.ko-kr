---
description: '자세히 알아보기: ICorProfilerInfo10 인터페이스'
title: ICorProfilerInfo10 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: fd24491cb1ca55ad48137522c63e78e6387d33e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753291"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="13b36-103">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13b36-103">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="13b36-104">함수 IL을 수정 하 고, 런타임에서 정보를 쿼리하고, 런타임을 일시 중단 하 고 다시 시작 하는 메서드를 제공 하는 [ICorProfilerInfo9](icorprofilerinfo9-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="13b36-104">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="13b36-105">메서드</span><span class="sxs-lookup"><span data-stu-id="13b36-105">Methods</span></span>  

| <span data-ttu-id="13b36-106">메서드</span><span class="sxs-lookup"><span data-stu-id="13b36-106">Method</span></span>|<span data-ttu-id="13b36-107">설명</span><span class="sxs-lookup"><span data-stu-id="13b36-107">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="13b36-108">EnumerateObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="13b36-108">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="13b36-109">ObjectID, callback 및 clientData가 지정 된 경우 각 개체 참조를 열거 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="13b36-109">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="13b36-110">IsFrozenObject 메서드</span><span class="sxs-lookup"><span data-stu-id="13b36-110">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="13b36-111">ObjectID가 지정 된 경우 개체가 읽기 전용 세그먼트에 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="13b36-111">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="13b36-112">GetLOHObjectSizeThreshold 메서드</span><span class="sxs-lookup"><span data-stu-id="13b36-112">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="13b36-113">구성 된 LOH 임계값의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13b36-113">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="13b36-114">RequestReJITWithInliners 메서드</span><span class="sxs-lookup"><span data-stu-id="13b36-114">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="13b36-115">요청 된 메서드 뿐 아니라 요청 된 메서드의 모든 inliners ReJITs 합니다.</span><span class="sxs-lookup"><span data-stu-id="13b36-115">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="13b36-116">SuspendRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="13b36-116">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="13b36-117">GC를 수행 하지 않고 런타임을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="13b36-117">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="13b36-118">ResumeRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="13b36-118">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="13b36-119">GC를 수행 하지 않고 런타임을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="13b36-119">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="13b36-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13b36-120">Requirements</span></span>  

<span data-ttu-id="13b36-121">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13b36-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="13b36-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13b36-122">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="13b36-123">**.Net 버전:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13b36-123">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="13b36-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13b36-124">See also</span></span>

- [<span data-ttu-id="13b36-125">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13b36-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
