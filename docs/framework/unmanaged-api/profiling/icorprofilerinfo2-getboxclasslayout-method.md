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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2943a70f563b82d3578ed7fbd98b981282a1dd5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472605"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="f4aa3-102">ICorProfilerInfo2::GetBoxClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="f4aa3-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="f4aa3-103">지정 된 값 형식 위치한 boxed 형식이 됩니다 하는 경우에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa3-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4aa3-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4aa3-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4aa3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f4aa3-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="f4aa3-106">[in] Boxed 값 형식을 설명 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa3-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="f4aa3-107">[out] 값 형식의 boxed 개체 ID 포인터에 상대적인 오프셋을 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa3-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4aa3-108">설명</span><span class="sxs-lookup"><span data-stu-id="f4aa3-108">Remarks</span></span>  
 <span data-ttu-id="f4aa3-109">`pBufferOffset` 값 상자 내에서 값 형식의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa3-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="f4aa3-110">후 `pBufferOffset` 적용 되는 boxed 개체에 값 형식의 클래스 레이아웃에 사용할 수 개체의 값을 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa3-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4aa3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4aa3-111">Requirements</span></span>  
 <span data-ttu-id="f4aa3-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f4aa3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4aa3-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4aa3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4aa3-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4aa3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4aa3-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4aa3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4aa3-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="f4aa3-116">See also</span></span>
- [<span data-ttu-id="f4aa3-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4aa3-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="f4aa3-118">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4aa3-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
