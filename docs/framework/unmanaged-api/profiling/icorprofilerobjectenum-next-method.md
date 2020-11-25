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
ms.openlocfilehash: e0c10549ab9075c2e7604a9adb18cae8b9a3b32b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702370"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="53d55-102">ICorProfilerObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="53d55-102">ICorProfilerObjectEnum::Next Method</span></span>

<span data-ttu-id="53d55-103">시퀀스에서 열거자의 현재 위치부터 시작 하 여 순차적 개체 컬렉션에서 지정 된 개수의 연속 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="53d55-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d55-104">구문</span><span class="sxs-lookup"><span data-stu-id="53d55-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53d55-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="53d55-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="53d55-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="53d55-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="53d55-107">제한이 `ObjectID` 각각 검색 된 개체를 나타내는 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="53d55-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="53d55-108">[out] `objects` 배열에 실제로 반환된 모듈 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="53d55-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53d55-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53d55-109">Requirements</span></span>  

 <span data-ttu-id="53d55-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53d55-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53d55-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53d55-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53d55-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53d55-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53d55-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53d55-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d55-114">참조</span><span class="sxs-lookup"><span data-stu-id="53d55-114">See also</span></span>

- [<span data-ttu-id="53d55-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53d55-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
