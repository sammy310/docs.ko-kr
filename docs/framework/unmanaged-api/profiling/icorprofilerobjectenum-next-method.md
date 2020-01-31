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
ms.openlocfilehash: 0c833416cca965f2655266152c5bdf5f11624d14
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861140"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="b718b-102">ICorProfilerObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="b718b-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="b718b-103">시퀀스에서 열거자의 현재 위치부터 시작 하 여 순차적 개체 컬렉션에서 지정 된 개수의 연속 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b718b-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b718b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b718b-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b718b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b718b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b718b-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b718b-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="b718b-107">제한이 각각 검색 된 개체를 나타내는 `ObjectID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b718b-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b718b-108">[out] `objects` 배열에 실제로 반환된 모듈 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b718b-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b718b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b718b-109">Requirements</span></span>  
 <span data-ttu-id="b718b-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b718b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b718b-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b718b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b718b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b718b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b718b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b718b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b718b-114">참조</span><span class="sxs-lookup"><span data-stu-id="b718b-114">See also</span></span>

- [<span data-ttu-id="b718b-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b718b-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
