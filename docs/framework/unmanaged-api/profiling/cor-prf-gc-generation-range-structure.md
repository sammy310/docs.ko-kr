---
title: COR_PRF_GC_GENERATION_RANGE 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 646c4e37a7fab503a26557f9fdfc926b1186b17b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775058"
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="f5508-102">COR_PRF_GC_GENERATION_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="f5508-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="f5508-103">가비지 수집이 진행 중인 메모리 범위(블록)를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5508-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5508-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="f5508-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f5508-105">Members</span></span>  
  
|<span data-ttu-id="f5508-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f5508-106">Member</span></span>|<span data-ttu-id="f5508-107">설명</span><span class="sxs-lookup"><span data-stu-id="f5508-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="f5508-108">값을 [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) 속한 메모리 블록에는 세대를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="f5508-109">메모리 블록의 시작 위치를 지정 하는 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="f5508-110">사용 되는 부분 (즉, 블록 내에서 사용 된 메모리의 양) 메모리 블록의 크기를 지정 하는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="f5508-111">(즉, 블록에 대 한 예약 된 메모리 양) 메모리 블록의 크기를 지정 하는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5508-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5508-112">설명</span><span class="sxs-lookup"><span data-stu-id="f5508-112">Remarks</span></span>  
 <span data-ttu-id="f5508-113">`rangeLength` 값을 정확 하 게 보장은 경우에만 [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) 또는 [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)를 모두 사용 하는 `COR_PRF_GC_GENERATION_RANGE` 구조에에서 호출 되는 [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) 또는 [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f5508-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5508-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5508-114">Requirements</span></span>  
 <span data-ttu-id="f5508-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5508-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5508-116">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f5508-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f5508-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5508-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5508-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5508-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5508-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5508-119">See also</span></span>

- [<span data-ttu-id="f5508-120">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="f5508-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
