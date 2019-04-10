---
title: ICorProfilerObjectEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 221752b537cd3a890ad646290a64a7022692f625
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173942"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="786e7-102">ICorProfilerObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="786e7-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="786e7-103">시퀀스에서 열거자의 현재 위치부터 시작 하는 개체의 순차적 컬렉션에서 지정 된 개수의 연속 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="786e7-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="786e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="786e7-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="786e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="786e7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="786e7-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="786e7-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="786e7-107">[out] 배열을 `ObjectID` 값을 나타내는 개체를 검색된 합니다.</span><span class="sxs-lookup"><span data-stu-id="786e7-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="786e7-108">[out] `objects` 배열에 실제로 반환된 모듈 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="786e7-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="786e7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="786e7-109">Requirements</span></span>  
 <span data-ttu-id="786e7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="786e7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="786e7-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="786e7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="786e7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="786e7-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="786e7-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="786e7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="786e7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="786e7-114">See also</span></span>

- [<span data-ttu-id="786e7-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="786e7-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
