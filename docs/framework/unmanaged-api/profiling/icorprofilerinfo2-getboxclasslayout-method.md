---
title: ICorProfilerInfo2::GetBoxClassLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 5f98c35f77fdb200be2e96364c9ac06c386faa62
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436025"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="ea525-102">ICorProfilerInfo2::GetBoxClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="ea525-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="ea525-103">Gets information about where the specified value type is located when it is boxed.</span><span class="sxs-lookup"><span data-stu-id="ea525-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea525-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea525-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea525-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea525-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ea525-106">[in] The ID of the class that describes the value type that is boxed.</span><span class="sxs-lookup"><span data-stu-id="ea525-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="ea525-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span><span class="sxs-lookup"><span data-stu-id="ea525-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea525-108">주의</span><span class="sxs-lookup"><span data-stu-id="ea525-108">Remarks</span></span>  
 <span data-ttu-id="ea525-109">The `pBufferOffset` value is the location of the value type within a box.</span><span class="sxs-lookup"><span data-stu-id="ea525-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="ea525-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span><span class="sxs-lookup"><span data-stu-id="ea525-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea525-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea525-111">Requirements</span></span>  
 <span data-ttu-id="ea525-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea525-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea525-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea525-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea525-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea525-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea525-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea525-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea525-116">참조</span><span class="sxs-lookup"><span data-stu-id="ea525-116">See also</span></span>

- [<span data-ttu-id="ea525-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea525-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="ea525-118">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea525-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
