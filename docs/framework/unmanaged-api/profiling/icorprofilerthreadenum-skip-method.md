---
title: ICorProfilerThreadEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cce96e8c6d046beba9e45c7121bf68444fd51c95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173344"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="6c3eb-102">ICorProfilerThreadEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="6c3eb-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="6c3eb-103">지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3eb-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c3eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c3eb-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c3eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c3eb-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6c3eb-106">[in] 건너뛸 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3eb-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c3eb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6c3eb-107">Return Value</span></span>  
 <span data-ttu-id="6c3eb-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3eb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6c3eb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c3eb-109">HRESULT</span></span>|<span data-ttu-id="6c3eb-110">설명</span><span class="sxs-lookup"><span data-stu-id="6c3eb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c3eb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c3eb-111">S_OK</span></span>|<span data-ttu-id="6c3eb-112">`celt` 요소를 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3eb-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="6c3eb-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6c3eb-113">S_FALSE</span></span>|<span data-ttu-id="6c3eb-114">미만의 `celt` 요소가 더 이상 있는지를 나타내는 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="6c3eb-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c3eb-115">설명</span><span class="sxs-lookup"><span data-stu-id="6c3eb-115">Remarks</span></span>  
 <span data-ttu-id="6c3eb-116">이 열거자의이 커서의 새 위치는 (현재 위치) + `celt`합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3eb-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c3eb-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c3eb-117">Requirements</span></span>  
 <span data-ttu-id="6c3eb-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c3eb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c3eb-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c3eb-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c3eb-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c3eb-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c3eb-121">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c3eb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c3eb-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c3eb-122">See also</span></span>

- [<span data-ttu-id="6c3eb-123">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c3eb-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="6c3eb-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c3eb-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
